+++
title = "RC 3: Applying to the Recurse Center"
description = ""
date = "2016-12-11T16:50:46-04:00"
tags = ["recurse"]
+++

Notes from past Recursers on applying to recurse helped me navigate the process and keep my sanity. [John Hergenroeder's](http://dev.jdherg.com/posts/2015/07/20/the-recurse-center-a-qa-for-past-me/) was especially insightful so I hope this can do the same and add another data point.

High-level timeline
===

This is my timeline, I wanted to join Winter 1 which started in November so I made sure to follow up as fast as possible.

Timeline
---
- October 7  - Started Application
- October 9  - Applied
- October 14 - Initial Callback
- October 15 - First Round interview
- October 17 - Notification for Second Round
- October 19 - Second Round interview
- October 23 - Admission Notice
- October 25 - Invited to RC Community Forum && Github Wiki
- November 7 - Day 1
- February 7 - Last day
<br/>
<br/>

Submit an Application
---
For the [initial application](https://www.recurse.com/apply/retreat), it asks you a few questions and asks you to submit a succinct code gist that doesn't use frameworks or require too much background knowledge to be understood by a reader. There are a few problems on the application pages you're encouraged to pick or to BYOC (Bring-Your-Own-Code).

I didn't have anything on hand, so that saturday I spent the afternoon coding Boggle in Python on the CLI.
I was nervous about choosing a right idea, looking for one that was not too simple to code but easy to understand. Making a game was sounded fine but many of the graphics libraries or rendering to browser would add more complexity so I paired down the program by just making it CLI based. At a point I was messing around with [ncurses](https://en.wikipedia.org/wiki/Ncurses) but after spending a few hours failing to make it bend to my will I decided `print` would do. After finishing my program and cleaning it up, the next part was the written application. I spent the rest of the night writing and revising the written application and exhaustinly submitted the following Sunday night. After this you get a confirmation from Recurse that'd you be contacted either way in the next few days. For my code sample I implemented [Boggle/Ruzzle in python in ~200 LOC](https://gist.github.com/stanzheng/d41bd3cada14c3b6310f33f0793e4ec2). In retrospect, it seems like it didnt't matter much what the idea was but having code that was understandable and can be elaborated later on is key.

A few days later ...
---

If you get called back, each of the subsequent interviews are scheduled through the Recurse site and take at most ~30 minutes. The interview are conducted over screen sharing and VOIP; We used Skype. You talk to two different admission officers; _Recurse Center_ admission officers are Recurse Alumni themselves and are the type of wonderful people you meet through the program. One handles the initial interview, the second handles the coding interview. The [Recurse Apply FAQ](https://www.recurse.com/faq) is extremely well detailed and accurate, so I won't duplicate any comments.

With my initial interview, I had it with David B. It was a very casual conversation about why I wanted to do Recurse. The interview is split into two portions, one where the interviewer asks questions and the interviewer asks questions. I felt like we were moving through a million thoughts a minute and very quickly the half hour was up. I left the interview feeling like there was more to be said and was unsure if what I wanted to communicate was conveyed in the conversation. There's not much preparation you can do for this interview besides making sure you're succinct and on topic. Having a few mental points that you want to convey or talk about isn't too bad but the interviewer has read your written application before so try not to regurgitate word for word specific points.

Two days later
---
I got an email @10PM on Monday for a follow-up interview. I was super relieved and excited to move on to the next stage of the process. When I went to sign up for a session there wasn't any timeslots. I was grateful that Recurse Admissions was able to find time to squeeze me in at night. I scheduled a follow up with Simon W. to do a thirty minute Wednesday night session. For the second interview, they ask you to pair with the interviewer. You can build something else on top of preexisting code you've written or picked one of the suggested problems. I ended up choosing the same gist of code for the sake of time and building scoring into the program. I was super nervous and the night before re-linted my code, added unit tests and changed development workflows so the interview would go smoother.

We once again did it over Skype, this session was at 9pm at night. We were both US east coast based but many recursers are from all over the world. You only get 30 minutes and they go by *fast*. I chose something relatively understandable for my game _Scoring_. But in Boggle/Ruzzle it also has [dynamic bonus word scoring](http://ruzzleonline.net/ruzzle-tips-to-improve-your-ruzzle-score/) based on length and letters so it made it an interesting problem to walk through. I was going to first do simple scoring just based on the length of the words and move into multipliers. I had only done pair programming in a traditional sense in one class in college and spent a day [brushing up on pairing techniques](https://www.google.com/search?q=pair+programming+tips).


 Sure enough like the first interview, 30 minutes quickly approached and we were still in the middle of refactoring, a little under half of where I'd expect I'd be at this point of the pairing session. We verbally talked about how we could attack the next portion and the session was over.

I felt confident I was able to eloquate myself clearly and communicate where we were going in the project. Simon W. had good feedback and was a fun navigator. He even taught me a factoid about [generator comprehensions which fed into sum](http://stackoverflow.com/questions/364802/generator-comprehension). I had done Python 2.7 for most of my previous job and had only used 3x for personal projects. The tone of the interview was also very informal and overall pleasant.


The Wait
---
At this point, I was at the end, either I was in or out. This was the most nerve racking part of the process. For four days I was super anxious whether or not I would be packing up my life and moving 300 miles up to NYC. I tried to keep everything in my mind. At this point, I had been going to conferences and code retreats to keep learning and stop stressing. I got the admission notice while I was at [All Things Open](/post/all-things-open/). I was extremely relieved and now anxious to know what came next.


How was it?
---
All in all the process was very short. From the time they received my application and my admission, it was 9 days. Even less if you discount time spent waiting inbetween interviews. I liken the process to the ideal college application process if it was actually sane and transparent. With Recurse admissions everything was communicated, the process was absolutely transparent and nothing was ambiguous. The process left me feeling confident going to Recurse would be a good fit and more excited about the future. I'm at the half way point of my batch and I feel more sure than ever that this was a good choice and I hope it encourages someone to apply and maybe even calm your nerves.

If you want to join the world's best programming community and become a better programmer consider [joining the Recurse Center](https://www.recurse.com/scout/click?t=710ee58e0b0ad8d9f443f9c9440137f1).

