#This tutorial explains how to create participant groups and how they can be assigned to swim lanes.

[Back to Table of Contents](TableOfContents.md)


# Introduction #

Activities in a business process are placed in swim lanes. Each swim lane is assigned to a participant group.

The activities of the swim lane can be performed by only those users who belong to the participant group of the swim lane.

The following steps illustrate how to create participant groups and associate them to the swim lanes-

## Steps to create participant groups/ teams/ user groups ##

**Step 1:** Click on '+' sign on the 'Teams' tab seen on the left hand side of the process designer (as shown in the screenshot below). Provide a name for the team and click on 'Finish'. This will create a new team.

![http://i.imgur.com/NsaEbDu.jpg](http://i.imgur.com/NsaEbDu.jpg)

**Step 2:** Navigate to this created team. Click on 'Add User' under Members tab. Select a user that you want to add to this team. In this example, since we created a 'student' team, we shall select 'student4' as the user for this team. The selected user will be successfully added to the list as shown in the below screenshot:

![http://i.imgur.com/6bjjFOA.jpg](http://i.imgur.com/6bjjFOA.jpg)

At this stage we have successfully created a participant group for 'student' role.

## Steps to associate created participant group to the swim lane ##

**Step 3:** We should next associate the above created 'student' participant group to student swim lane in a project.

Navigate to a process for which this participant group was created.
From the Process tab, select the process. The process will open in the designer successfully as shown in the below screenshot.

![http://i.imgur.com/zx5nAav.jpg](http://i.imgur.com/zx5nAav.jpg)

As seen in the above process, there is a student role involvement.

**Step 4:** Select the swim lane 'Student' as shown in the below screenshot.
In the 'Properties' tab of this selected swim lane, navigate to 'General' tab. Under the 'Behavior' section, click on 'Select' for the 'Default Lane Team' field. Select the previously created participant group 'Student' (as seen in the below screenshot). The selected participant group should now be associated successfully to the swim lane.

![http://i.imgur.com/zItiUTo.jpg](http://i.imgur.com/zItiUTo.jpg)

With this association of participant group to the student swim lane, all the activities in this swim lane are to be run only as student1. In other words, only student1 who belongs to this attached participant group can run all the tasks in this lane.