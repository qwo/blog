+++
title = "RC 9: QDraw: Exploring Google's Hidden Character API"
description = ""
date = "2017-01-25T11:43:03-05:00"
tags = ["recurse"]
+++

QDraw was an RC project I worked on in December in the last week of my batch. I was inspired to build something similar to [QuickDraw](https://quickdraw.thinkwithgoogle.com), a thinkwithgoogle.com project, which allowed you to play Pictionary against the machine. I had been studying machine learning during my batch and thought it was an excellent fun project to try and make. I thought about how I could translate the canvas positions to lines but couldn't think of a way to generate enough tag data to make it work. I thought of hack solutions like using PostgreSQL with PostGIS and doing line matches against known loaded geojson shapes but that wouldn't be a machine learning project at that point. I was stuck and soon after I shelved the idea.


![Google Input Tools](https://lh3.googleusercontent.com/jLcobWjFlnhLvCgFfLDwMwRCgS924upeKx1kaB5724M7tehxt9ExNYsDAQ3gpzRiMM6XMttSdJvjfNQobxxiJFRBP71KkZbqc0bGektonNWCk63MpO_Dua9lHI3Ki4s1mzhBj7r6ahpnnzGDlHTSc_GIXQznfUMtmwGHxYXzH5Vw4sgs81tsdx0OWaRNALDBifOqx2eKftiNY93Xe2JS9wrctLtInaSmlsbWH4cxmvPB6fP3nkjUAK2_CtWcdbym0VS61oEgVPh7htlFJvzD0oK8zg9EKg1azOv8DL45pim7Q0jSXrwAVfelDIsbzhW66pCaeNWiyeChyax6CTmVuXc8YA_sqd0XxLSiFzOSxSptAH6EW2T8qQVckpW1Z0f7JEo36yM4uS2P417aa2_T3w4RAOkHh5ag-FXJL0W5vQ9dRuL0E1BSvZcFYtkwdI5LSPU-xEtrIeXslY3CYzxLAcj-e7L9SXX-Lah6YH-E36u8fCRFu9c_jiXcDNxOxJE9qhWaIO3k6F2nuvcA3Aqh6k-oF3iVAfIlE-zOdK56e_b5cCB7U00Q8Zgfr98QccT9ksjK36RllG8YXMHVF_kMN4dnaZFgui6H7IL9OrcO0PoIDkGQpRmpN283ab__m8H-Ce4NDqiPXCS2FKsHmGPghk4LkfGhgtj2tOSrntKuofY=w960-h662-no)
<div class="caption">_Similar input tool found in Google Docs_</div>

# Toggling Input
Later on, someone on Recurse Zulip was asking about internationalization tools for language input. It led me to stumble upon their [language input tools](https://www.google.com/inputtools/try/). A part of Google's internationalization efforts, they had open source implementations for both Android and Chrome for drawn input to support multiple languages hosted on [Github](https://github.com/googlei18n/google-input-tools). I was fascinated by Input Tools because it let you draw arbitrary Unicode symbols on canvas and it resolved into a close Unicode approximation. This is the same behavior they were using in Google Docs in the symbol drop down.

![Drawing pictures](https://lh3.googleusercontent.com/IXemo4aPy3kTR99brdttHuEIS8NxeO6IYz4TR2GQdnGawe5OqF4Akhra6jg1PdoWMhlnWiWUGbJYwAY-CDfewAodIsm8Xo1XrbX0uer2SWUKdb3d1IY_EW-515pRB0xRoycR71zt9DUPGY3LZhjjkrB3ZC3gpfuceZQgdRcUw4euUwRtkt0c2nVI8x5JrZTJbsx6e-7TuQuIH4c3QK_RP9AT-qy72ybml9VQ6VKMJkCcCzkUlX9QZNGiFt9fHN-w8V2J7mn-pVDpxIZKt9vIza2X6EeKSQHYRxr5FEfQ6lPcHnuIhDb-axifgwYOktJURX_IUgcbf7m_k6fBmFkkCZOiP9H7jx3xx6rwOIHiskEJnb8TdXyTiMEZ2fugpxQ0-XSXNRKB7aNauQQS5QZLaOpvOESutZpXCpjaE4oRNGC9vrKlptvOI3hp_ux5PBDfH1pggayzQHYivuTWHUfUbBAn5EQQU0t_f0y5QnACpALa5xaCPWpLb3HIE4_WP6pXqxeSQ7ubkVbM8qN4ULmCXKDf58H4sOMcc-ZIRLvIjnbWsATQnAAo4jmXKZuQ2jcMpnZBn5PGjeJTRwszxMoUh0n2pfi-IbAFg-uds8GVPRVGT__w9uiTbYy7WqqgA9QAwnN3fDz2jhr4XvO6woYzjr_SQ20AmXK_7ijQdnCmFmY=w960-h656-no)
<div class="caption">_Unicode Emoji Approximations_</div>

I wanted to find more, so I started to look into the payloads being sent back and forth between Google and the Try input page. I noticed they were translating canvas line positions into strokes and serializing them into a JavaScript array to be sent in the payload. I noticed in the open source google-input-tools, they didn't provide the source code the symbol -> canvas input API which made it difficult to approximate what I wanted.

At this point I wanted to use this to somehow reverse the Google Input tools and find out how they worked so I could build my own DrawSomething but with Emojis! The code that was on the live page was minified, google closure compiled code so it was hard to read but the canvas code was easy to spot. However, I was relatively unsuccessful and was frustrated after spending almost two days trying to capture how to translate the strokes correctly.

![Payloads](https://lh3.googleusercontent.com/CEOjsGQ7i5T0hqYPHts3ZEQ55cJ4n08TFqZzS3rl5cPGZgF7aCVBTG3mtMttR3LSiYhtssA4dBUhkAu_gNIAN9xX3x_CLFle366pG7y-v2QC15bTbZR_btWXqyxhaS-9d9agwY_fNYFZNGA8fuhfoISvGp9-v6di-bblG5eUnZnBnc7peVoT8dsWkR8w-SYqKwuPtwPqr_qp0Pd1CeUqZDenltGsP-QsVkoHO4i23F_ytQdCsCLe66tb-9rGR8R-IxuuZDjze5vLJcisBcZ9l1N1N5zEQuo_NsTRQigWqbg29v2pONBHlqDtP_0B-kGeGvTcB3EijWBcDlfqCUj3vb5xIeHo7OrcETn9ZYHtw7YVbE17gUi-2sr3e491WRzegluaWVmHOrfYlJhfVWPMjZgQYW-QH1-SjnwLdYGvD-zdyDo9M3UphAvAdQp66BdqM-ZBHvABTdivpP7Ii3Uomj-brCD5ScVfA43-j7rbrVkKEJtiO3MVn8bQeLv3a5BBBgDV9Ec1xWCD7Wba8WMKhe2g7wIF2S7airU8W6vYT15Tu3pZ-HwOAlRbgNLvjnmsYRahbOjU5on1glS36W461nNUgrBlEEPsnQD_gsRS84vIfomjmd9rZlx7dsL4zzumCZvi7CdFJhK5DU9PYb2dE-jsoKS7gAeU3IObSDAs584=w699-h344-no)
<div class="caption">_Canvas draw positions being serialized to JSON Arrays_</div>


# Github to the Rescue
After becoming frustrated, I searched on Github for one of the methods of the draw command and struck gold. A GitHub user, ChenYuHo, had created a project called [handwriting.js](https://github.com/ChenYuHo/handwriting.js) two years earlier to leverage Google's input tools canvas -> Chinese language. I was excited that I could then now move on and start replicating my own QuickDraw.

After hacking around the code, I realized I could replicate drawing Chinese and into Unicode approximations very easily, Success!


# Curious...
Another search result peaked my interest. The same API was being called within someone who was doing an actual analysis of QuickDraw so that they could mine the data from the system. It might have been pure coincidence, but in reality, I had found out Google released their experiment using the same API. Instead of training their model on tagged Chinese characters, they trained it on tagged doodle images. I was excited and skeptical if this was true, but when I looked at the network tab of [Quickdraw](https://quickdraw.thinkwithgoogle.com), I verified they were hitting the same API.
I was now confused but also in awe how Google was able to repurpose an internally trained API for something completely different so easily.

![Emojis](https://lh3.googleusercontent.com/1dy1UNoUXmF3aZRZl0w3MbNk1C8BXrTQ4crQzE9jDbMDxiqZvvYfSTm0pCcBcDH5LEtu2Si1aAKG6ITTb27gk4dI5UW3FVSQxB_Yrjkjec2ScGz1jBhDPHnNtldp4HDf8oUzvgt5d2XfUO90mcfJlB59ekiR9g-6G3-AStzF0VJyFkoh5jFzaD_E_hg6hhKahx9s5g25KTQgQSofMcSAETo3u2iptvn4mOA8xgqF5n23gbpGbY6svVcR-LO9SJNxQAvb8mFr12ZMeg_OEnzwEiow9nN0Xmr7dQDtasSFgYdzfbNsCtdNbRRyA41XZwYnMBKBaHHIunbjx9nJPuWQ_eQ2hwC4rT6Ct8ZcNOnYfuX5Dd1_dH88OYqLzYGRJNYIJrIlBww3OqsuCj40LF1N2y5vdBXnzyHB1tAkos69TaKnphf2_0SrPGO9rIm66KqyuiDTSUtMPIezT-bsZu453V9wjM7fAw88xFr0HM3kqHll8k_0kEFylEIxEbFdDTrse27ZFQP7fsXh411vxorWjvxbEyvbF356geFHnT5ki9DQnYEp1TFCJxdIU0c1rK9EatmVV6bs0YmpCL1Yfy4OZ_o7Ck3oiViPq91uo5DH0r8fGHyeJM6MsDBRpXp01Y8o5V5kufXpV2cV89ghixjoCqdSXghneBAgnHFwMOhBrS0=w960-h426-no)
<div class="caption">_Drawing Unicode characters work!_</div>


# Going further with QDraw
For my version of Quickdraw, I was now able to reroute to use the same APP language input that Google input and Quickdraw was using. At this point, I had reversed their API to build my own QuickDraw by building on top of their own APIs. It felt less satisfactory in general, although flashy, Google controlled all the services and data making it impossible for anyone to extend on top of it.

![Quickdraw](https://lh3.googleusercontent.com/tq-EoxggSQot0wrEXfD9qDJhWSv-pHwRNgyBGF7zPro4iQWL8I9He5XKyN0YHoi1QGx02VZHB84o6BTczvhfTyYVygVDEcIgxvL8EItWaugT9We68J7IWOPfYc04Ve5VIm25FzON6QqoB6ETxwVl8D7KJuWSCV2C_XeShXQP316WZ5NhnIDb3O1-KveNP1TVs3CM2HUTV996zCdeai_6-dsxM-48UsV_XTo_PkvOCsJ6XFUHvRr5VQvVZCrLlhbyeOvgXTnlVIltGqGHQYoBzMH7yjkNPrCj8hNpXkNrcZfvLeck2YhfQBd2uG-6te6_RKviTqqQWi0kc7Z7n6qxZlC66RKfEbEzHGdHquQgHe6ASJ3NljgU4DYANpXkzQRbS7NJpMSgLJNuQ0awfI4_gD6K_Yr3WDSyANGPHyhufLWSG804B3hxmkQNrw3dYLV61XNsxGPaMO-gimCl01ANvbcnnVdyqskPpAcJ4TyAB99fKAyFlOP65P--4HB-j2Jy8_znizWdm3t3OINEj_2sScv0wzR5xevvIjfb4RN5UzIZPPjhTxWGEGljUpWnCDZ9FI1fwK346Qp_fWMUnZJOW17yIU9vXvB3CE9NKcrZR_phWhKLfSNiM1mwRwH7L5z_Oq9DcMi2XW4fJtoNVA-mim0DdNvBYryOCln4ewL5n8I=w960-h454-no)
<div class="caption">_Lets make some funny doodles like Quickdraw_ </div>

# Digging Deep
I had fun digging around an unrelated tool for Google internationalization and accidentally stumbling into Google's secret sauce of how they made QuickDraw. The API is public, and besides the pixel translations, is incredibly simple to use. Thanks to open source for drawing and putting together the dots. My hacked together version can be found at [https://stanzhengdev.github.io/qdraw/](https://stanzhengdev.github.io/qdraw/). My biggest takeaway is dig deep, you might find some interesting hidden insights. In the future, I'll put together another post to better document the keyboard API Behavior.




