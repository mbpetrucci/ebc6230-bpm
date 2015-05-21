[Assignment2\_Part1\_Subprocess](Assignment2_SubProcess.md)

#This page describes the business process walk through for Part(1) of Assignment(2), which demands the use of subprocess in designing the business flow.

**Prerequisite**

Create a business object as shown in the below screenshot and use the same throughout the process:

![http://i.imgur.com/8e1KGSp.jpg](http://i.imgur.com/8e1KGSp.jpg)

**Clerk**

**Step 1:** When a process is first run by the clerk, he is prompted to provide his identity. He provides his email address and click on 'Identify Me' button.

![http://i.imgur.com/Osxh5zW.jpg](http://i.imgur.com/Osxh5zW.jpg)

If the provided email address matches any one of the entries in the 'clerkName' from the 'clerkTB', then he is recognized as a valid clerk user. He will then be allowed to browse the inventory items and request items. If the clerk email address is not a valid one or doesn't exist in the table, then he is not recognized as a valid user. The instance can end here.

**Step 2:** Assuming the happy path, the clerk is recognized as a valid clerk user. He will now be provided a screen that displays all the items from the 'inventoryTB' table as seen in the screenshot.

![http://i.imgur.com/nPEFPxh.jpg](http://i.imgur.com/nPEFPxh.jpg)

The clerk needs to select one of the items that he thinks is running short and needs to be ordered for.

He can select the item by clicking on the radio button against one of the displayed items.

![http://i.imgur.com/d9eTrKZ.jpg](http://i.imgur.com/d9eTrKZ.jpg)

The clerk can click on 'Submit' button after selecting one of the items.

**Step 3:** The clerk is then taken to another screen that displays only that item that he selected in the previous page. This is to confirm his selection.

He can select that displayed one item and click on 'Confirm Submit' button.

![http://i.imgur.com/hStj6Z6.jpg](http://i.imgur.com/hStj6Z6.jpg)

**Step 4:** On confirming the selection, the clerk is next taken to a page where in he must be allowed to change the quantity of the item. The clerk can edit this field called 'Needed Quantity' and submit the order request to the manager for approval.

![http://i.imgur.com/ONL1cGY.jpg](http://i.imgur.com/ONL1cGY.jpg)

As seen in the above screenshot, the 'Needed Quantity' is updated to 100. This means, the clerk is ordering for 100 pieces of that selected item.

At this stage, the clerk is done with his job of browsing the inventory, identifying the item that is running short and logging a request for that selected item.


**Manager**

**Step 5:** Once the clerk has submitted the request, it will be received by the manager. The manager needs to review the request. He can approve or reject this request.

  * Step 5.1:**If the manager wants to approve this request, he has to check 'Approve' radio button as seen in the screenshot below.
![http://i.imgur.com/kAGWZ3m.jpg](http://i.imgur.com/kAGWZ3m.jpg)**

On submitting this approval, the entry will be written to the DB table: 'requestItemsTB' successfully.

This can be verified by displaying the record written to database. The manager can be provided with another screen that displays what request was approved by him in the previous screen. This is depicted in the following screenshot:
![http://i.imgur.com/KV0m8Ed.jpg](http://i.imgur.com/KV0m8Ed.jpg)

By clicking on 'OK' the instance ends. The business process comes to an end at this point.

  * Step 5.2:**If the manager wants to reject this request, he needs to check 'Reject' option as seen in the screenshot and 'submit' the same:
![http://i.imgur.com/VB5Ys7I.jpg](http://i.imgur.com/VB5Ys7I.jpg)**

On submitting this rejection, the process ends. There is no need to write to DB table, when the request is rejected.


Note**We are tracking only approved requests.**

## Business Process Diagram(High Level Overview) ##
You may choose to design your business process as shown here:
![http://i.imgur.com/EsCsaAc.jpg](http://i.imgur.com/EsCsaAc.jpg)

Subprocess is encapsulating the activities involved in 'Requesting Items' by the clerk. The subprocess involves browsing inventory+Selecting Items+Submitting the request to manager
![http://i.imgur.com/picuJu2.jpg](http://i.imgur.com/picuJu2.jpg)