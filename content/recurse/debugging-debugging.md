+++
date = "2016-12-11T22:13:50-05:00"
title = "RC 4: Debugging debugging"
description = ""
+++

Debugging is easy, the answer is always _the the last place you look_.
Mastery of debugging I would argue is a more valuable skill than programming itself. Often the worst feelings are staring at your code hopelessly trying to understand where the logic is breaking down.


At Recurse, there are lots of ways to tap into help. We have [Zulip](https://zulip.org/) stream's dedicated to every programming language imaginable, `#pairing`, `#advice`, and even just plain `#help`. Having such a diverse community and many people in the same room it made it easy to reach out and find someone to work with within the space.


 When someone reaches a mental block, they often ask for help on Zulip and if you're lucky you'll be on the other end. At the past places I worked there was always at least one engineer you had in mind; if you ran into a long mental block, you knew you could work with them to help rubber duck through the problem. I aspired to one day to become the developer the team can rely on to help debug with them.

Coming into Recurse as a more seasoned developer, I had many opportunities to practice my pair debugging skill. I find pair debugging just as or if more rewarding than pairing. Here are some observations from anecdotes that I've picked up and learned from reading many of the great resources that can help an in person debugging session.

<br/>
Some Short Tips for Pair Debugging
===
1. Timeboxing your sessions.
2. Listen and observe the problem discounting bias.
3. Form a hypothesis and step through it.
3. It's probably something more obvious than you expect.
4. Cut down the problem by removing unrelated code.
5. Its ok to not know the answer.
6. Celebrate your successes.

<br/>
A Breakdown
===

Here are a few elaborations and andecdotes that back up the list. Its not the end all list, so let me know if there are additional tips I've missed that could help debugging sessions.

Timeboxing your sessions.
---
It's nice to continue until the end but what's worse than one confused developer is two! Timeboxing your session whether that's 15 or 30 minutes can help keep it fresh and if the session was close you can reschedule to revisit later to work on the problem again. It's likely hard to generate more insights spending more consecutive hours on the problem than stepping aside and letting maybe another developer join the fray. This tip in the Recurse wiki and brought up from Rose A.


Listen and observe the problem discounting bias.
---
What I mean is to not become too engrossed into what we know and come as an observant blank slate into the problem.  I was helping a fellow batching, Noah, debug their project one morning. The problem started with an undefined error of  `map is not a function that is allowed` when parsing some data from an AJAX call from the API. We started working through debug the AJAX call and set breakpoints within the React component. However the solution we arrived at could have been gleaned at if we looked at the data first using the network tab. It turned out we were returning an object instead of an array from the API. It's also sometimes can be categorized as the [XY-problem.](http://meta.stackexchange.com/questions/66377/what-is-the-xy-problem)



Form a hypothesis and step through it.
---
After hearing the problem, form a plausible solution but talk through with it with the pair. This can help adjust quick prove/unprove what going on and further understand the problem. On the first week, I was working able to work with Stephanie L on her hangman game using a [2d chart program](https://plot.ly/python/) and python. On execution of the program, it would draw all the parts of the body all at once instead of later. She mentioned if she put the draw calls from the dictionary in quotations and wrapped it to be evaluated later it would be fine. It leads me to hypothesize that from the instantiation in the dictionary, it was causing all the items to be drawn at once. From that we were able to test when we removed some of the calls it would draw less shapes. Thus we were able to solve the issue by wrapping each [call in a function](http://stackoverflow.com/questions/9205081/python-is-there-a-way-to-store-a-function-in-a-list-or-dictionary-so-that-when).


It's probably something more obvious than you expect.
---
Sometimes the issue is actually the library or the system but more likely than not and it's something more basic or obvious. I was working with Jon S. on debugging a python library issue. It was using an NLP python library and it worked and imported fine on my box. We were baffled why it would work on my system and not his. We were going through setting up virtual environments and looking at the differences for running the library on a Windows or Linux VM and OSX. It had a lot of dependencies and we were wondering if it was a space issue or maybe a different version of python.

It turned out the import issue was because the test stub was named the same as one of the library imports and it caused an import conflict. It's very easy to overlook the small issues and think it's something larger working against you.

In a similar vein, it can easily be the library is broken. I was working with Deniz K. on setting up using vagrant with an open source project. All signs and messages pointed to something wrong with the version of VirtualBox or vagrant but the error messaging was cryptic. In the end checking out the issue tracker led to the discovery that [the package curl in Vagrant was  broken.](https://github.com/mitchellh/vagrant/issues/7969) Sometime's it is the tools that are broken and so check the issue trackers!

Focus on the problem by removing unrelated code.
----
When debugging it goods to comment out unrelated code or better yet delete it. Keeping less in view gives fewer lines to debug and the code that exists, of course, isn't working. During a Code Dojo, Jon N. and I were working on a [Hacker Rank problem](https://gist.github.com/stanzheng/4e6c5ad80acc82612b4d5cfec347aa19) that involved dynamic programming with JavaScript. We were on the precipice of solving the problem after we understood it well but were running into a bug. We couldn't figure why the program would overshoot by one or short circuit. We were debugging the body of the program but what turned out to be the issue was we were reverse iterating instead of forward. It was left over code that I saved that ended giving us typical off-by-one error. That mistake cost us 10 minutes of being confused until we finally just deleted and rewrote the whole function body of code. It took only a few minutes and it ran on the first run.


Its ok to not know the answer.
---
Sometimes just being a rubber duck is immensely useful. But admitting that you, yourself don't know the answer also helps set expectations and makes the session go way smoother. Being open to learning and providing a different perspective can be invaluable for anyone in itself.


Celebrate your successes.
---
Sometimes it's a successful and very short session. When Daniel R. and Jen H. brought a question about Node, express and application data flow I knew 100% all the way down how to solve it since I had done it a million times before. Many of the 4/5 stories all happened one faithful Thursday and at the end of the day, it was great to have a short successful debugging/pairing session that you felt confident you knew through and through.

Another similar story was when Krace K., Jen. H and I spent an hour using browser tools to track down a bizare bug in Zulip. It exhibited the characteristics of an interesting bug, highly visible in occurrence but confusing in tracking down; if you typed someone's name such as `David` in the userslist, it would cause JavaScript errors until you typed their last name. It wasn't entirely transparent why it was just a handful of names like `David` so it became a fun bug hunt. We dove through Zulip's application data looking for differences in users identified. In the end, we tracked down the bug to a [case sensitivity issue]((https://github.com/zulip/zulip/issues/2492)) and were satisfied that we discovered whatwent wrong and how it could be fixed.



Wrapping up
===
Experience is just learned pain from debugging and writing more code; the best ways to get more is to just simply do more of it until problems seem familiar. I'm lucky to be able to share and work with lots of interesting people at the center. All in all, setting up a debugging plan with a few of the tips above can save time and make a pair debugging experience more fruitful and fulfilling.