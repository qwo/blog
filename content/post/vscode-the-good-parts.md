+++
title = "Visual Studio Code: Up and Running"
description = ""
date = "2016-03-12T17:28:12-04:00"

+++


Try it! You might just like it!
---
Visual Studio Code is Microsoft’s cross-platform text editor that was announced in April of 2015 and open sourced on Github in November. It has a similar look and feel to Sublime and Atom and is a quick responsive basic editor with polished tooling.
When I started web development, I started using Sublime Text 2/3 in 2012; but as time passed, it seemed sublime was stagnating with the product with fewer releases and interesting features. After Github announced Atom, I jumped on it as soon I got an invite. It was an exciting editor built on the tooling on the web that we all knew and loved. The community was very excited and the ecosystem on APM rapidly became 1:1 complete with all the plugins on Sublime.



As Time Goes On
---
Professionally, I ended up using more editors for development, from the JetBrains family of IDE to the minimalistic VIM editor. These were far ends of the spectrum between what Atom traditionally offers and was very refreshing.
With Atom, I started running into limitations. Originally files larger than 4mb would crash your editor. To get where I liked it, lots of tweaking and plugins installation and increased startup time. Stepping through code was something you did on your own and you had set up your own tool chains for that.


---

1. Add a jsconfig.json file
---
Visual Studio is known for Intellisense, Microsoft's smart auto competition tool that lets your brain memorize less. It uses typescript definitions to give you type definitions for any library defined by using typings, a tool to install typescript definitions. Most popular libraries already have a .ts definition file (React, Lodash, Express..) etc. Add the file to your project or in your .vscode directory if you do not want to commit it.

```
{
    "compilerOptions": {
        "target": "ES6",
        "module": "commonjs"
    },
    "exclude": [
        "node_modules",
        "wwwroot"
    ]
}
```

Visual Studio Code is built in typescript but also offers a bunch of great autocomplete options for well-used libraries. Even if you're not using typescript or flow, you can benefit from the IntelliSense completion. As of 1.6, I believe they've added typings by default to the editor.



2. Use Tasks in your Command Palate
---
VSCode can read common task runner tools like Gulp and Grunt. VSCode adds these tasks to your command palate so you can easily use `CTR+P` and look for the tasks that are in in your gulp file. If your project already has grunt or gulp added, no additional configuration is required. You can also define your own if you use NPM or another tool as your primary task runner.


3. Use the Debugger Tools
---
Microsoft has provided debugging tools for JavaScript, TypeScript, Go and Python and the community are adding much more. They let you step through line by line and set manual break points. This gives the full stack editor feel while still keeping it minimum.


4. Alias VSCode in Your Terminal
---
At least with the OSX DMG installation, it does not link vscode in your user apps path like Atom. You can easily correct this with an alias.

```
function vscode { open -a “Visual Studio Code” $1}
```
and run it as vscode in your terminal.



Much much more
---
This is a work in progress .. I’ll continue adding tips as I come along them while using it. Happy Coding.
Conclusion
Try out VSCode again, it's gotten much better since the original release and getting better all the time. It's not reach critical adoption yet and there are small quirks (no tab navigation), it is definitely a worthy option to try.