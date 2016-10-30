title: Mongo Cheatsheet
date: 2014-02-27 11:29:47
tags: mongo
---


Print out everything in a json result in mongo
```javascript
var myCursor =  db.ships.find();

myCursor.forEach(printjson);
```

Print out all the results of a single one

Multi Query
```javascript
var myCursor =  db.norfolk.find({name:"Ynot Pizza"});

myCursor.forEach(printjson);
```

Regex Fuzzy Field Search
```javascript

var myCursor =  db.norfolk.find({"name": /pizza/})
myCursor.forEach(printjson);
```
