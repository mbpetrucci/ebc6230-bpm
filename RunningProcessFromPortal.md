#This tutorial explains how to make a business process available in Process Portal. It also briefs the steps involved in running a process from Process Portal

[Back to Table of Contents](TableOfContents.md)


# Introduction #

Process Portal is a interface for running process instances.
The process portal can be accessed though this URL-
http://bpm2.site.uottawa.ca:9081/ProcessPortal

## How to expose process to user group/participant group/team and how to run the process from portal ##

By exposing a process from designer to selected user/user group, you are making it available to that user/user group. So, the user/usergroup can start an instance of the process by running it in Process Portal.
The following steps explain how to expose process to a user-

**Step 1:** From the Process Designer, Open the process that you need to expose.

From the Process tab, select the process. The process will open in the designer successfully as shown in the below screenshot.

![http://i.imgur.com/zx5nAav.jpg](http://i.imgur.com/zx5nAav.jpg)

**Step 2:** From the Process Designer, Navigate to 'Overview' tab, seen on the top of the process designer screen. This will take you to Process Overview section that shows 5 major section- Common, Advanced, Work Schedule, Exposing, Team.

'Exposing' section is what we are interested in for now.
Expand 'Exposing' section. You will see a field called- 'Expose to Start' and it shows 'none' associated user. (Which means, no user is associated currently).

Click on Select and choose one of the user groups that you have created for the selected project. (Refer to [Participant Group Creation](CreatingParticipatingGroup.md) for more information). Save the selection, by clicking on 'Save' option seen on the top of the page.

These steps are illustrated in the below screenshot.

![http://i.imgur.com/wFuXJSR.jpg](http://i.imgur.com/wFuXJSR.jpg)

This way, you have now exposed this process to selected user group. Which means, the users in this attached user group can run the process and create it's instances.


**Note:** Select the user group that usually starts the process. i.e, select that user group whose action is first defined in a process.


**Step 3:** Log in to process portal as a user for which the process is exposed to. In out above example, we have exposed the process to user group 'Student'.

The group has student4 user only in it.
So, Logging into Process Portal as student4 should display this process available.

Navigate to this URL: http://bpm2.site.uottawa.ca:9081/ProcessPortal. Log in to process portal providing the username and password. You must see the exposed process on the right hand side of the portal screen as shown in the below screenshot.

![http://i.imgur.com/pdMnGLh.jpg](http://i.imgur.com/pdMnGLh.jpg)


**Step 4:** Click on the process to create an instance of the process. The first activity will now be displayed in the worklist as shown in the following screenshot.

Click on the activity to run it from portal. The interface associated with this activity will be loaded on the portal page, thus allowing the user to interact with the system through process portal

![http://i.imgur.com/ADc8P05.jpg](http://i.imgur.com/ADc8P05.jpg)

[Back to Table of Contents](TableOfContents.md)