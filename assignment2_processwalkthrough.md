#This page shows sample screenshots of assignment2 to-be solution.

[Back to Table of Contents](TableOfContents.md)

[Back to Assignment 2](assignment2.md)


### Prerequisite ###
Before building the solution model, create the needed business object (complex type data variable) as shown in the following screenshot-

![http://i.imgur.com/aVcUW3y.jpg](http://i.imgur.com/aVcUW3y.jpg)


**Step 1:**
The clerk will start the business process. On starting the process, inventory items are fetched from database and displayed to the clerk.

Use 'getInventoryItems' tofetch all the inventory items from DB.

So, the clerk will now see a form that contains list of inventory items. He is expected to select only one item from the list as shown in the following screenshot.

![http://i.imgur.com/ytt4Kag.jpg](http://i.imgur.com/ytt4Kag.jpg)

**Step 2:**
The selected item is alone displayed in the second screen of the clerk. The quantity field is now shown up. And this field should be editable (input text type). Also, the clerk should be able to fill in requestor Name and email address while submitting the request form to the manager. All the other fields should be non-editable fields (output text type).

The clerk can change the quantity for the item that he selected in the previous page and submit the request to manager.

![http://i.imgur.com/x5aFsx7.jpg](http://i.imgur.com/x5aFsx7.jpg)

**Step 3:**
The manager receives the form displaying the selected item and the altered quantity field element.

The manager can approve or reject this request.

![http://i.imgur.com/Di7KK8p.jpg](http://i.imgur.com/Di7KK8p.jpg)

**Step 3\_Manager approves request**
If the manager approves the request, the record needs to be written to DB.
Use 'writeApprovedRecordToDatabase' operation to write the approved record to DB.

In order to ensure the record is successfully written to DB, fetch the written record from DB and display it to the manager.
Use 'fetchapprovedRecordFromDatabase' operation to achieve this task.

The screenshot of the form showing the record fetched from DB is shown below-

![http://i.imgur.com/51r0n5B.jpg](http://i.imgur.com/51r0n5B.jpg)

**Step 3\_Manager rejects request**
If the manager rejects the request, the process should end at this stage.
Rejected record should not be saved to DB.
The following screenshot depicts the request being rejected.

![http://i.imgur.com/xnm2kwJ.jpg](http://i.imgur.com/xnm2kwJ.jpg)

### Sample Business Process Model ###

![http://i.imgur.com/9BhnEKn.jpg](http://i.imgur.com/9BhnEKn.jpg)