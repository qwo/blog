+++
title = "Prepping for a Technical Interview"
date = "2014-03-18T18:43:11"
+++

Intro
===
I gave a talk at my local ACM about how to prepare for technical interviews. It's a topic not emphasized  on much at my school and I wanted to give students some advice about starting and what helped me.


Algorithms
===
- Learn about [Big O notation](http://bigocheatsheet.com/) and try being able to recognize their O(time).
- Perform two sortings. O(nLog(n)) QuickSort & Merge Sort maybe familiar yourself with others
    - Tree Traversals
    - in, post, pre
    - order,
    - breadth/level
    - depth
- tree structures, binary, trinary, heap trees, AVL
- Graph problems... Dijkstra, A, common n = np problems. Know Edges and Vertices.
- Learn about what  [n = np problems](https://en.wikipedia.org/wiki/P_versus_NP_problem). and what makes it a n=np problem.


Links
===
General Review and Tutorials
- http://community.topcoder.com/tc?module=Static&d1=tutorials&d2=alg_index

Videos
---
- Open Source CourseWare MIT http://www.youtube.com/user/MIT
- Harvard CS50 http://www.youtube.com/user/cs50tv
- http://cs.stanford.edu/people/eroberts/courses/cs106b/chapters/13-trees.pdf

<br/>

Google Recruiter Suggested Tips
---
I got these really helpful tips from a recruiter from Google. They sent me this email for the new interview round info.
- https://gist.github.com/stanzheng/9631465
- http://community.topcoder.com/tc?module=Static&d1=tutorials&d2=alg_index
- http://cs.stanford.edu/people/eroberts/courses/cs106b/chapters/13-trees.pdf

StackOverflow Questions
---
- http://stackoverflow.com/questions/210829/what-is-an-np-complete-problem
- http://stackoverflow.com/questions/111307/whats-p-np-and-why-is-it-such-a-famous-question
- Quick vs Merge http://stackoverflow.com/questions/7878768/when-to-use-merge-sort-and-when-to-use-quick-sort
- http://stackoverflow.com/questions/4421706/operator-overloading


Notes
---
- Use quick if you can but doesn't always guarantee nlog(n) and can become O(n^2)
- Merge sort is the best alternative when no Random Access (Stack, Queue, list) of the structure
- Heap sort is also in there if quicksort starts degenerates