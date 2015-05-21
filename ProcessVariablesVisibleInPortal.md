#This page explains how to view business process variables in the portal

[Back to Table of Contents](TableOfContents.md)

# Introduction #

Business Process users interact with the system through human interfaces called coaches. User-specific interfaces are to be accessed from Process Portal.

Here is the URI to access portal:
https://bpm.site.uottawa.ca:9443/ProcessPortal/login.jsp

It is necessary to view some process variables' current value while the process is in execution. This can be achieved by controlling the visibility of needed variables in the process designer.

The following steps explain how process variable values can be made visible in the portal:
  * Step1:
Once the business process is constructed, choose the variables that needs to be visible in the process portal to the users.
In the below screenshot, I have considered a Rare Books Borrow Process to demonstrate this activity.
![http://i.imgur.com/M49shUy.jpg](http://i.imgur.com/M49shUy.jpg)

The variable at this process level is shown in the below screenshot. And I have selected userName to appear in the process portal.
So, select the 'userName' variable and check the checkbox 'Visible in Process Portal' under 'Business Data' option as shown below:
Also, provide a alias name. This name will be displayed in the process portal.
![http://i.imgur.com/A5d4XUl.jpg](http://i.imgur.com/A5d4XUl.jpg)

![http://i.imgur.com/yU9AkZ4.jpg](http://i.imgur.com/yU9AkZ4.jpg)


  * Step2:
Run the business process from the portal and view the changes.
![http://i.imgur.com/Wf5kfY9.jpg](http://i.imgur.com/Wf5kfY9.jpg)



Note:
  * If the variable is of complex business object type, desired component of the business object can be individually made visible on the portal.
  * If the variable is a list of complex business object type, then in order to have a desired component visible in the portal, a local variable can be used. The desired component's value needs to be mapped to this local variable. And the local variable can be exposed.
In the screenshot above, 'BorrowedRareBook' is a local variable which is mapped to first item of the LibraryItems list.
(i.e, tw.local.borrowedBook = tw.local.libraryItem \[0\] .Title;)

