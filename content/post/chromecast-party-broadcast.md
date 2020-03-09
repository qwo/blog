+++
date = 2016-12-11T14:37:26Z
description = ""
tags = ["hack"]
title = "Chromecast+TTS = Party: PA.js "

+++
I put this together in an afternoon hack session and was planning to extend it and clean up the code. However, its been months and the holidays are rolling around and it's yet to be published! I wanted to put out a small writeup how to harness your Chromecasts for home automation, scripting, and fun.

Back at my [previous job](https://thisisgrow.com), we had installed Chromecasts throughout the building hooked up to speakers and TVs. We used them during social functions to play music throughout the building and the deck. I've always been a fan of the Chromecast since the initial announcement and still own my v1. I was familiar with the network model how Chromecasts use [MultiCast for service discovery](http://www.dns-sd.org/). This is how all your wifi devices on the same router are able to see each other. I thought it would be really cool to broadcast announcements throughout the building.

But to have a resource play I needed to stream a resource accessible to the Chromecast like a public URL. At this point, I was looking at Text-to-Speech libraries and found sadly there are far few and between standalone free and open source projects. You could use [OSX Say](http://skipperkongen.dk/2011/12/04/saving-output-from-text-to-speech-to-file-on-mac-os-x/) to record a WAV to stream but it wouldn't work on other platforms and I would have to reupload to somewhere like s3 or a public server (too slow!).

However the useful marrying of using [Google Text-to-speech](http://stackoverflow.com/questions/9893175/google-text-to-speech-api) as public resources to translate `English to English`. Success! now a streamable URL could be pointed to the Chromecast and we could selectively blast all the Chromecasts in the building. Even Google Translate had an easter egg where you could make beatbox using german tones. However, this since has been removed videos still exist for posterity.

Have fun and Thanks for the wonderful work of [Mafintosh on Chromecast](https://github.com/mafintosh/chromecasts) to make this surprisingly easy. Source code attached, it takes in input and broadcasts it to all your Chromecasts in your building.

<script src="https://gist.github.com/stanzheng/2be2bb212066a67d8c5747d9a53a81b3.js"></script>

{{< youtube JAIHY0pb4xc >}}