#Blank Screen.

[Back to Table of Contents](TableOfContents.md)

## Process Designer Shows Blank Process Center Page ##

  * Go to the directory where Process Designer is installed (.\IBM\ProcessDesigner\v8.5\AppClient\java\jre\bin) and find the javaw.exe file.

  * Make a new copy of javaw.exe file and rename it to javawpd.exe. You will now have 2 copies of this file.

  * Go to (.\IBM\ProcessDesigner\v8.5) folder and open the eclipse.ini file.

  * Find the line ./AppClient/java/jre/bin/javaw.exe  and change it to ./AppClient/java/jre/bin/javawpd.exe

  * Restart Process Designer.