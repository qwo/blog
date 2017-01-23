+++
title = "RC 9: QDraw: Reverse Engineering Google's Doodle API"
description = ""
date = "2017-01-12T11:43:03-05:00"
tags = ["recurse"]
+++

QDraw was an RC project I worked on in December in the last week of my batch. I was inspired to build something similar to [QuickDraw](https://quickdraw.thinkwithgoogle.com), a thinkwithgoogle.com project, which allowed you to play Pictionary against the machine. I had been studying machine learning during my batch and thought it was an excellent fun project to try and make. I thought about how I could translate the canvas positions to lines but couldn't think of a way to generate enough tag data to make it work. I thought of hack solutions like using PostgreSQL with PostGIS and doing line matches against known loaded geojson shapes but that wouldn't be a machine learning project at that point. I was stuck and soon after I shelved the idea.


#Toggling Input
Later on, someone on Recurse Zulip was asking about internationalization tools for language input. It led me to stumble upon their [language input tools](https://www.google.com/inputtools/try/). A part of Google's internationalization efforts, they had open source implementations for both Android and Chrome for drawn input to support multiple languages hosted on [Github](https://github.com/googlei18n/google-input-tools). I was fascinated by Input Tools because it let you draw arbitrary Unicode symbols on canvas and it resolved into a close Unicode approximation. This is the same behavior they were using in Google Docs in the symbol drop down.


I wanted to find more, so I started to look into the payloads being sent back and forth between Google and the Try input page. I noticed they were translating canvas line positions into strokes and serializing them into a JavaScript array to be sent in the payload. I noticed in the open source google-input-tools, they didn't provide the source code the symbol -> canvas input API which made it difficult to approximate what I wanted.

At this point I wanted to use this to somehow reverse the Google Input tools and find out how they worked so I could build my own DrawSomething but with Emojis! The code that was on the live page was minified, google closure compiled code so it was hard to read but the canvas code was easy to spot. However, I was relatively unsuccessful and was frustrated after spending almost two days trying to capture how to translate the strokes correctly.



#Github to the Rescue
After becoming frustrated, I searched on Github for one of the methods of the draw command and struck gold. A GitHub user, ChenYuHo, had created a project called [handwriting.js](https://github.com/ChenYuHo/handwriting.js) two years earlier to leverage Google's input tools canvas -> Chinese language. I was excited that I could then now move on and start replicating my own QuickDraw.

After hacking around the code, I realized I could replicate drawing Chinese and into unicode approximations very easily, Success!


#Curiosity
Another search result peaked my interest. The same API was being called within someone who was doing an actual analysis of QuickDraw so that they could mine the data from the system. It might have been pure coincidence, but in reality, I had found out Google released their experiment using the same API. Instead of training their model on tagged Chinese characters, they trained it on tagged doodle images. I was excited and skeptical if this was true, but when I looked at the network tab of [Quickdraw](https://quickdraw.thinkwithgoogle.com), I verified they were hitting the same API.
I was now confused but also in awe how Google was able to repurpose an internally trained API for something completely different so easily.


#Going further with QDraw
For my version of Quickdraw, I was now able to reroute to use the same APP language input that Google input and Quickdraw was using. At this point, I had reversed their API to build my own QuickDraw by building on top of their own APIs. It felt less satisfactory in general, although flashy, Google controlled all the services and data making it impossible for anyone to extend on top of it.


#Digging Deep
I had fun digging around an unrelated tool for Google internationalization and accidentally stumbling into Google's secret sauce of how they made QuickDraw. The API is public, and besides the pixel translations, is incredibly simple to use. Thanks to open source for drawing and putting together the dots. My own silly version can be found at [https://stanzhengdev.github.io/qdraw/](https://stanzhengdev.github.io/qdraw/).




