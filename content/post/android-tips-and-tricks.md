+++
title="Tricks when Developing on Android with Java"
date="2014-01-14T16:34:36"
+++
---
+   Components of android
    *   Activities -email client
    *   Services -music player
    *   Content Providers - Note taking app or contacts
    *   Broadcast Receiver -The intent deliverer

Logcat filtering without eclipse.
```bash
adb logcat | grep --line-buffered "mysearch"
```

to pipe out to txt file
```bash
adb logcat | grep --line-buffered "mysearch" > mylog.txt

```


open and visit website via intent
```java
adb bash am start -a android.intent.action.VIEW -d http://www.stackoverflow.com
```
Build from commandline an android project (replace 'Hello with name of Project')

```bash
android update project --name Hello --path
```

Use Environment Variables versus a sample or config file
```bash
export VARIABLE_NAME="VALUE"
export MIRROR_DEMO_CLIENT_ID="your app's id"
export MIRROR_DEMO_CLIENT_SECRET="your app's secret"
export MIRROR_DEMO_REDIRECT_URL="your redirect url"
```

in your code
```javascript
var oauth2Client = new OAuth2Client(process.env.MIRROR_DEMO_CLIENT_ID,
    process.env.MIRROR_DEMO_CLIENT_SECRET, process.env.MIRROR_DEMO_REDIRECT_URL);
```


Run an application from adb
```bash

#example running setting
adb bash am start -a android.intent.action.Main -n com.android.settings/.Settings
```

Diagram
+ Intent Life Cycle
+ Services Life Cycle
+ Activity Life Cycle

Always Check the manifest for all related information

run the app, replace the latter with the activity you want to invoke
---
adb bash am start -n com.google.zxing.client.android/.CaptureActivity

Jars are just zips
-----
Use a utility like JD-GUI or Jad to unzip a jar and get the source. Perfect for when you lose the source or when you want to tinker.


``` bash

jar -xf YOURJAR.jar && find . -iname "*.class" | xargs ./jad -r
#cd into the directory and
mv *.jad *.java
```
Check out http://stackoverflow.com/questions/5107187/extract-source-code-from-jar-file/5107213#5107213


Having Camera Issues? Check Android manifest to make sure permissions are enabled
```xml
    <uses-permission android:name="android.permission.CAMERA" />

    <uses-feature android:name="android.hardware.camera" />
        android:minSdkVersion="15"
        android:targetSdkVersion="15" />
```
