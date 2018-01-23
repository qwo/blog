+++
title = "AWS Lambda with Python"
description = "Scraping Data Feeds"
date = "2018-01-23T12:06:44-05:00"
tags = ["AWS","Python"]
+++


### Intro
[AWS Lambda](https://aws.amazon.com/lambda/) is a hosted platform for running code in the amazon ecosystem. It supports multiple runtimes including Python! I found that although writing the logic code is easy, there are some unintuitive things that I've stumblbed over.

There are three ways you can get your code to amazon lambda. 

1)  their inline editor 
2)  S3://Bucket
3)  Zipped up

The below repo has a preconfigured way to clone a repo, and demonstrate adding packages to run on AWS Lambda quickly.

1) Setup an AWS Account and CLI on machine
2) Provision an AWS Lambda with role `AWSLambdaFullAccess`
2) Create your function with a unique name from the interface

Use the starting point of https://github.com/4projects/python-lambda-template and update `App.py`


### UPDATE CODE 
```
zip -g App.zip App.py
aws lambda update-function-code --function-name $FUNCTION_NAME --zip-file fileb://App.zip
```


**Note** Also update your app handler from `Main.handler` to something like `App.handler`.


## Detailed Writeup



## Building the bundle

This is how the bundle was built and can be rebuilt. Additional packages can be added onto it. 

### Packaging and uploading your bundle

You need to package third party dependencies. The least painful way is to setup a virtualenv. `pyenv` comes packaged with python3 so after you create a new directory you can do that with:

```
mkdir APP_NAME && cd APP_NAME
python3 -m venv .
```

Then you have to activate your virtual environment. Depending on your terminal pick the appropriate extension.To activate your virtual environment   you would use `bin/activate`. If you're using fish shell, you can use `bin/activate.fish`.

after your `APP_NAME` directory should look like:

```
ls . 
> bin        include    lib        pyvenv.cfg
```

Now install packages to your heart's content. creating a few dependencies or common libs you rely on is wise.

`pip install requests`

Then changing directory to the `site-packages` in your `lib` folder. My directory path happens to be `  $VIRTUAL_ENV/lib/python3.6/site-packages`.



Zip it up `zip -r9 App.zip $VIRTUAL_ENV/lib/python3.6/site-packages`.

