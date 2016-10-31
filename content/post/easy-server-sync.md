+++
title = "Easy Server Sync"
description = "don't need browsersync to be fancy"
date = "2016-09-20T01:23:49-04:00"
publish = "true"
+++

You can setup some great tools like browsersync or built in editor features to keep your comptuer synced with a remote server. This can add some benefits such as being able to have a staging/live server and demo in real time to a sharable remote. However setting up all those tools isn't always fun for small tasks.

In OSX/Linux there are some basic unix tools that you can use in combination to simulate the same effects.
We will be using fswatch and also rsync to simulate a file watcher and uploader.

Setup the below gist and you're off and running. Any file changes will trigger an rsync. Hopefully with the options, specified only diffs will be rsynced.


<script src="https://gist.github.com/stanzheng/c002bfc60fadef4a8dd53db5a0d6a4a7.js"></script>