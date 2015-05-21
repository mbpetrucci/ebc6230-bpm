#This page explains how to create and use timer events

[Back to Table of Contents](TableOfContents.md)


# Introduction #

Intermediate Timer Event specify a time interval in a process after or before which an activity needs to start.

After the specified time is elapsed, the process flows along the sequence line.


A time interval can be provided in the following two ways:

  * By selecting the number of days, hours, and minutes that should elapse before the Timer is executed.
  * By specifying a Custom date using JavaScript. This approach must return a JavaScript date object specifying when the Timer is to be executed.

## Tutorial to create and use timer event ##
Let us assume a scenario, where in the student fills in a form and submits it to the department for review.

we will alter this process to put a wait between the student submitting the form and faculty receiving the form. In other words, the process is now going to be lie this-

> (a) Student fills a form and submits
> (b) The timer begin, which will tick for 10 minutes. Once the 10 minutes is complete, the filled form is made available to the faculty.
> (c) The faculty receives the submitted form after 10 minutes of submission and views the details.



Step 1: Create a user interface/human coach for the student as seen in the below screenshot:
![http://i.imgur.com/HzEhyOq.jpg](http://i.imgur.com/HzEhyOq.jpg)

Step 2: Create a user interface/human coach for the faculty as shown in the screenshot
![http://i.imgur.com/65dRMIb.jpg](http://i.imgur.com/65dRMIb.jpg)

Step 3: Create a Business model as shown in the following screenshot
![http://i.imgur.com/M3qtoKd.jpg](http://i.imgur.com/M3qtoKd.jpg)

add an activity in the student lane and attach the human service created in Step1.

add an activity in the Faculty lane and attach the human service created in step2.

Drag and drop intermediate activity from the palette seen on the right hand side of the process screen.
In the 'Implementation' section of this intermediate activity, Change the type to 'Timer Event'.

set the timer properties.
as seen in the below screenshot, I'm saying the timer is going to start after the submitDetails activity and runs for a minute.
[.md](.md)