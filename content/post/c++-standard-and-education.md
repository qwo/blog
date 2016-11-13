+++
title= "C++ Standards in Education"
date= "2014-03-08T19:23:50"
+++

I learned mostly C++99 standards throughout my time at my CS Course program. Actually scratch that, it wasn't even explained the different in standards. Even from traditional C, or C99, its funny how institutions focus on learning but give only a breadth first generalistic approach to most education.

Another argument is if C++ is the best language to be taught in intro programming courses compared to Java or even C# (or the ideal _Python_). I started using `C++11` for my later assignments on my final years of my courses but I was also using Sublime text. Here were some common untils that helpeed me compile my code using this workflow.

Compiling with C+11
```bash
clang++ -std=c++11 -stdlib=libc++ -Weverything prog6.cpp -o prog6
```

Suppressing compile with C+99 errors
```

```bash
clang++ -std=c++11 -stdlib=libc++ -w -Weverything prog6.cpp -o prog6
```

ignore C++99
```bash
clang++ -w -std=c++11 -stdlib=libc++ -w -Weverything prog6.cpp -o prog6
```
See this gist for more info on how to integrate into sublime text 2/3 for your build system file.

<script src="https://gist.github.com/stanzheng/9441259.js"></script>
