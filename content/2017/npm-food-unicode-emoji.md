+++
title = "NPM Food - Emojis + NPM Packaging"
description = ""
date = "2017-03-11T12:06:44-05:00"
tags = ["javascript"]
+++

# `npm install -g food`

If we installed this package from [NPM](https://npmjs.com), what do we expect this to do? What kind of interface would we expect this to implement? I'm not quite sure; This was one of those ideas that I had a spark of an idea and started four years ago. Watching the package go stale and be empty for years reminded me I should try and provide another valuable node package to the world.

## Original Intent

When I started out in 2013, I had an idea of creating a module that generated data for apps. When we created JavaScript apps, we want to populate our views with data but also check the boundaries of our app. I had no idea four years ago that the technical term was [fuzzing](https://en.wikipedia.org/wiki/Fuzzing) and something like [faker](https://www.npmjs.com/package/faker) was what I was hoping to create. Later on I learned [big list of naughty strings](https://github.com/minimaxir/big-list-of-naughty-strings) and I wanted to incorporate it with an easy way to test these strings. (Yay more food!)

## What Now
After first learning how to publish npm packages way back when. (It's as simple as [npm publish](https://docs.npmjs.com/getting-started/publishing-npm-packages)!) it was still empty. I wanted to brush up on creating packages and was recently inspired by Jon New's post on [Unicode in Javascript](blog.jonnew.com/posts/poo-dot-length-equals-two) to create a fun easy way to work with it.


## Data

The Unicode Consortium hosts a repo of all the emojis possible in this [file directory](http://unicode.org/Public/emoji/4.0/). I grabbed the `emoji-test.txt` and wrote a python parser to scrape and categorize all the emojis into json.

### Beware Hacky Python Below!
``` python
"""
Stanley Zheng
March 11, 2017
Parses http://unicode.org/Public/emoji/4.0/emoji-test.txt
"""

import os
from collections import defaultdict, namedtuple

emojis = defaultdict(list)

emoji = namedtuple("emoji", ['unicode', "display", "category", "description"])

def parse_line(l, category):
    """
    Example of a line being parsed ...

        1F601  ; fully-qualified     # 😁 grinning face with smiling eyes
    """
    if len(l.split(';')) < 2:
        return None
    left, right = l.split(';')  # split on ;
    unicode = left.strip()
    if unicode == "0023 FE0F 20E3":
        display = "#"
        descript = "keycap: #" # special exception for # character
    else:
        right = right.split("#")[1] # more clean up
        display = right.split(' ')[1]
        descript = right[3:].strip('\n ')
    return emoji(unicode, display, category, descript)._asdict()



with open("data/emoji-test.txt", "r") as f:
         namespace = ""
         start = False
         for line in f.readlines():
            if "# subgroup: " in line[:12]:
                namespace = line[12:].strip('\n')
            elif start and len(line) > 1:
                emojis[namespace].append(parse_line(line, namespace))
            if "# group: Smileys & People" in line  :
                start = True

emojis.keys()
```


### Post Processing

After this beautiful processing, we're left with an keyed dictionary all the individual emojis with their plain text representation. I ran into issues serializing it into JSON because of the way python represents Unicode is different from Javascript.

For an Unicode character like "👋", in Python I would get something like `"\\1F44B\\1F3FC"` but the interpretation in JavaScript would need to look something like `"\u{1F44B}"`.
So I wrote my own pretty printer and went to town with good ole copy paste.

``` python
from pprint import pprint

for _, cat in emojis.items():
    for e in cat:
        if e is None:
            continue
        print("""{{
          "unicode": "{unicode}",
          "display": "{display}",
          "description": "{description}",
          "category": "{category}"
        }},""".format(**e))
```

The finished product can be found on github [here](https://github.com/stanzhengdev/npm-food/blob/master/data/emoji.json).


# Packaging for NPM


Having not written a package in a while, I checked out one of my prolific goto people to see a good architecture to setup my package. [Sindresorhus](https://github.com/sindresorhus/node-module-boilerplate) has some good defaults that I'm glad I was able to start from. Including setting up text fixtures using `Ava` test runner and linting using `Xo`. I put together a Readme on my project and hit publish. (one or more times).

Npm enforcement of semver meant everytime you wanted to publish a small change to your package, its recommended you publish a MAJOR/MINOR/PATCH scheme. See [SemVer](https://semver.org) to learn a little bit more about this.



# Summing up

Well, I released `food` [to the world](https://www.npmjs.com/package/food) 🎉. Anyone with `npm` installed now can access my creation with `npm install -g food`. I'm still not sure where I want to take this next, so if you have a fun direction to take or add to this interface file an issue!
This was a fun break from interview prep and reviewing if I remember anything about node modules and packaging. It's like riding a bike and I always appreciate how easy it is for anyone to contribute and add their code to the world.


To end
```
➜  blog git:(master) ✗ food wave-hand-bye
[ { unicode: '1F44B 1F3FC',
    display: '👋🏼',
    description: 'waving hand: medium-light skin tone',
    category: 'body' },
  { unicode: '1F44B 1F3FD',
    display: '👋🏽',
    description: 'waving hand: medium skin tone',
    category: 'body' },
  { unicode: '1F44B 1F3FE',
    display: '👋🏾',
    description: 'waving hand: medium-dark skin tone',
    category: 'body' },
  { unicode: '1F919 1F3FC',
    display: '🤙🏼',
    description: 'call me hand: medium-light skin tone',
    category: 'body' },
  { unicode: '1F919 1F3FD',
    display: '🤙🏽',
    description: 'call me hand: medium skin tone',
    category: 'body' } ]
```

