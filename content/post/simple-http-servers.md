+++
title = "Quick Serve it!"
date = "2014-01-31T11:38:12"
+++

Sometimes you need to serve a directory to a group in a small room.

Using Node
``` bash

npm install http-server -g
http-server
# another port
# http-server -p 9080
```

Want to run it forever in production? Run it forever
``` bash
 forever start ../node_modules/http-server/bin/http-server
 # path the last argument to http-server and path it to where you want
```

Using Python
```bash

python -m SimpleHTTPServer
# specify port number via python -m SimpleHTTPServer 8080
```
Using Php
``` bash

php -S 8080
# works for php 5.4 and up, php has its own package
#or stick something on your /var/www bin and profit.

```


Want to share some files? use wget or curl
Localhost is your website.

a specific file

Using Curl
``` bash
curl -O http://localhost:port/FILE.TXT
curl -O http://localhost:port/PIC.PNG

```

Using Wget
Always works for me, included no parent and recursive to only get the desired directory.
``` bash
 wget --no-parent -r  http://localhost:port/DIRECTORY
```
