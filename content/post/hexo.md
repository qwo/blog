title: Debugging Hexo
date: 2014-01-15 01:07:22
tags: hexo
---
Here is a quick reference to debugging hexo:

+ huge stack error - check if all your configs are not null
+ missing resources error - I had to edit my *.styl files to have some of the css and assets located correctly
+ hexo server deploy wrong fork - I had a huge issue with having it push to the right fork. deleting didn't work and destoying didn't either
+ hacking on hexo and saving it in the same directory is probably not a good idea, the project is still being updated currently
+ use the HEXO-CNAME-GENERATOR package plugin to handle some of the errors with creating CNAME
