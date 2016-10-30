title: Run Java in Sublime
date: 2014-01-29 22:09:25
tags: Sublime 
---
This is for mac on sublime.

It makes it a bit easier to build and run java everytime you compile. Speeds up from moving to terminal each time. 

***using sublime or text editor is sometimes unmanagable for java but the anti-eclipse club is strong...***

``` java
//Build and run java, works on OSX 10.9 Mavericks and Sublime and up
{
	"cmd": ["javac \"$file_name\" && java \"$file_base_name\""],
  	"shell": true,
  	"file_regex": "^(...*?):([0-9]*):?([0-9]*)",
  	"selector": "source.java"
}
```
