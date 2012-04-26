This script deploys your application to Google AppEngine without user interaction needed. It does 
this by generating a script with your given parameters, executing it to upload your project and removing
the batch file.

PREREQUIREMENTS
===========================
* Tested with Nant 0.86 - [http://nant.sourceforge.net/]
* Google App Engine Java SDK - [https://developers.google.com/appengine/downloads]
* Nant setup correctly on your PATH

USAGE
===========================
```
  C:\projects\my-super-duper-project\releases\nant -buildfile:deploy-appengine.build.xml 
    -D:application-id={your-appid-in-appengine}
    -D:application-version=nightly-1.2.3 
    -D:appengine-username={google-username@gmail.com}
    -D:appengine-password={yourpassword}
    -D:uncompressed-project-war-path="C:\projects\my-super-duper-project\releases\my-super-duper-project-1.2.3\" 
    -D:gae-sdk-tools-path="C:\appengine-java-sdk\appengine-java-sdk-1.6.4.1"
```

SECURITY NOTE
===========================
Your password is saved to the batch file before execution and it is removed afterwards. If debugmode
is enabled the script will not be removed. Your password will not be echo'ed to the Console.Out
because multiple build servers capture the console output.

LICENSE
===========================
Original version by [Mark van Straten - Q42.nl](http://www.q42.nl/mark-van-straten)
Sourcecode located at [github.com](https://github.com/Q42/appengine-ci-scripts) - git@github.com:Q42/appengine-ci-scripts.git
This software is kindly granted to the community and licensed under GNU GPL-3.0 - see supplied LICENSE.TXT for details    

TODO
===========================
[ ] Make option for auto-publish this version as active version in appengine
[ ] Generate better replace rule for the version because AppEngine only allows letters,digits & hyphens
[ ] Figure out how we can delete the batchfile even if the deploy procedure failed.

REMARKS
===========================
* This script does nothing to prevent you from reaching the max-version (10) limit of Google AppEngine.