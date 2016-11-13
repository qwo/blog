+++
title = "DE Hackathon with Appcelerator"
date = "2014-02-11T23:53:51-04:00"
+++

Dominion Enterprises Hackathon
=====
<img width="300" height="300" src="https://lh4.googleusercontent.com/-5PpC1BjbVs8/Uv44fmNPDeI/AAAAAAAACXE/mCeMokuXAnc/w1484-h1090-no/20140206_092115_483.jpg" alt="Kick off, 7 Schools and 9 teams from Virginia">

A hackathon, also known as a hack day, hack fest or code fest, is an event in which computer programmers and others involved in software development, including graphic designers, interface designers, and project managers, collaborate intensively on software projects.

This was Dominion's Seventh hackathon and the second edition of HackU, a hackathon where schools were invited across Virginia. Paired with three coaches and given 24 hours, each team was read a challenge on gamification and set off to build something. None of the members of our team had more that a few hours of experience with titanium and almost none with Lanica.

The inspiration
======
The concept of the game came from looking off the 20th floor of Dominion Enterprises. We were using the windows as white boards, and one of our teammates suggested a game where you dodged obstacles and projectiles on a motorcycle. But then we thought it would be more fun to be the one chucking the obstacles.

We wanted to make a game where you are a person on a top of a building who is pelting moving vehicles below. It evolved when we wanted to make our mischievous egger into a hero; We made the objective to egg cars to protect and the egger, a grouchy grandma.

<img width="300" height="300" src="https://lh4.googleusercontent.com/-rfLUY1Fd8jE/Uv44fvkVwiI/AAAAAAAACW8/HoNxubjXnbw/w1484-h1090-no/20140206_101159_118.jpg" alt="the team">

<img width="300" height="300" src="https://lh4.googleusercontent.com/-MktpVd_FsJM/Uv44gH65sNI/AAAAAAAACXA/zBl6XFQuV5Q/w1484-h1090-no/20140206_094004_208.jpg" alt="Looking 20 floors down ">

Neighborhood Watch was thus hatched.
A pack of reckless motorists has invaded your neighborhood. Protect your neighbors as they cross the street by egging the cars before anyone gets hurt.

Playstore = https://play.google.com/store/apps/details?id=com.DWS.neighborhoodwatch
Github:  https://github.com/stanzheng/HackU2
</td>
</tr>
Day1:
====
At the beginning of that hackathon we decided early on we would utilize lanica. After we brainstormed and prototyped our idea out, we started with a lanica boiler project and started from there. (https://github.com/Lanica/Platform/tree/master/platino/Engine/CodestrongCar)

After we did some tinkering we had a working demo in 30 minutes. Two cars that drove opposite of each other on the street with a sprite background we made.

<img width="300" height="300" src="https://lh3.googleusercontent.com/-KGErmhCfl-0/Uv44lFbs5sI/AAAAAAAACYE/NVN8K45N2Pk/w1916-h1078-no/thing.png" alt="Cars moving ">

We then inserted more sprites that our graphic artists created. Boom!
<img width="300" height="300" src="https://lh6.googleusercontent.com/-ALh4X2hZCQw/Uv5IIwlYJOI/AAAAAAAACZM/860IN8eKd_A/w1860-h1090-no/Screenshot_2014-02-06-22-19-50.png" alt="Motorcycle parade">

We then inserted more sprites that our graphic artists created. Boom!
<img width="300" height="300" src="https://lh6.googleusercontent.com/-KpQ6lqEPn6M/Uv44iMVHPeI/AAAAAAAACXY/UZeo-OLSaH0/w1484-h1090-no/20140206_160944_959.jpg" alt="crazy town">

After a bit of sloshing we got collisions working; in the context of the app we could crash two cars together and they would disappear.

Using this mechanic, we started adding pedestrians into the mix.
<img width="300" height="300" src="https://lh5.googleusercontent.com/-qFfZVyj-9o4/Uv5IJTvKQMI/AAAAAAAACZQ/xm7ja2Oszhg/w1198-h674-no/Bf1WYRkCMAAs-ZQ.png" alt="Pedestrians ">



At this end of the night we had core mechanics working, day two would be about polish and presentation. It was nice how fast it was to prototype all our ideas out and then bring it together in **Lanica**.

+ Sprite movement
+ vehicle and person collision
+ Project Collisions


Day2:
====
End of the day, we polished our app. We added a couple of screen transitions and finalized the UI. We were really excited to show everyone our game and were nervous about everything working  out correctly.

|short video of all the mechanics working|
---
https://www.facebook.com/photo.php?v=10203082376161824&set=vb.1278603133&type=2&theater


<img width="300" height="300" src="https://lh4.googleusercontent.com/S27wbduMre9MCwD0QIsRrBJ9K_h2o1HNcPvKdV-I8DM=w698-h1090-no" alt="Load Screen Pan ">

<img width="300" height="300" src="https://lh3.googleusercontent.com/SCH3X7wiI5RNS12S5oQa8K8STSj5RneUj3UXz8xxamw=w662-h414-p-no" alt="our start screen">

<img width="300" height="300" src="https://lh3.googleusercontent.com/vjoyIv7isAjjRg9OSK2FYwJ1nHDJDVuX51EejU4vwZ8=w640-h400-p-no" alt="end score screen ">


End of this day
+ Display UI
+ Screen transitions
+ deployed to the app store

Presentation
=====
The presentation hall was packed and 9 teams would be showing what they accomplished in 24 hours.

<img width="300" height="300" src="https://lh4.googleusercontent.com/-wpJ66W4pmBI/Uv44kf2sbPI/AAAAAAAACXw/-1Itq2Nq4To/w1484-h1090-no/20140207_150501_661.jpg" alt="presentation time ">

We performed our presentation with an **Ouyva**, an android powered video game console. Due to the controller not working, we utilized a mouse to present.

Overall we took first place and **Best in Show** for use of Appcelerator/Lanica and the Dominion Enterprises APIs.

<img width="500" height="500" src="https://pbs.twimg.com/media/Bf63cW3IAAASfMT.jpg:large" alt="win! ">


If you're still interested take a look at the source code and look below.


Some other notes and some of the Cool Stuff From Platino
======
Here are some of the notable ways we used parts of the game engine; The game engine did much of the heavy lifting and kept the game in the development zone. Writing in a familiar codebase of javascript, it was easier to produce. We did run into a few hic-cups and nuances in **Appcelerator** and **Platino** that the team had to work through.


Sprite Collisions
---
- The sprites along with being really easy to import also inherited collision. This made it easy to do create listeners and events for when vehicles hit pedestrians or when the eggs hit the cars.

Camera Pan
---
- The beginning animation was created using a sprite image and a pan. Super easy to create a pseudo-animated home screen. In addition, both of the home and end screens were created by sprites that we hoped to create animated span screens.


Transforms
----
- The vehicle sprites were created with vehicle view sprites that we then rotated. This way we only needed a single sprite that we then could animate.
- Jossling was also a feature we utilized to make the sprites seem less linear. It multiplied the sprites with a coefficient to of random bounciness, which made our assets come <alive class=""></alive>


Platino
-----
- The animations of Grandma tossing the eggs were created using transform along with Platino constants. This made it easy for to say,       go from point A toB but in a curved way or in a zig zag.
- Generally, **Platino** being built off of **Appcelerator** opened up a lot of common tasks in the framework.In our app, we were able to render full HTML pages for about and planned to create a UI for settings using titanium UI windows.



Created with love by The Grumpies
====
Stanley Zheng @stanzheng http://github.com/stanzheng
Jose Mateo @jmate003 http://github.com/jmate003
Onapha Rattana @cosmicmeow http://github.com/cosmicmeow
Trisha Tobias @aureately http://github.com/aureately
Anthony Bittle @guywithnose http://github.com/guywithnose
Chris Ryan @chrisryan http://github.com/chrisryan
Brandon Beigay
Krishna