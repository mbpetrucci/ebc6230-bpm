[Back To Assignment2\_Part2\_Linkedprocess](Assignment2_LinkedProcess.md)

#This page describes the business process walk through for Part(2) of Assignment(2), which demands the use of Linked process in designing the business flow.

**Prerequisite**

Create a business object as shown in the below screenshot and use the same throughout the process:

![http://i.imgur.com/8e1KGSp.jpg](http://i.imgur.com/8e1KGSp.jpg)


**User Identification**

**Step 1:** Business process begins by identifying the type of user. The user can be of two types: (a) the store clerk  or  (b) a customer.

The user has to select the type of user.


**Clerk**

**Step 1.1:**Assuming that the user is a clerk, the user needs to select user type as 'clerk' as shown in the screenshot.
Once the user has identified himself as a clerk, he will then be taken to clerk login page.

![http://i.imgur.com/wzVsZ5d.jpg](http://i.imgur.com/wzVsZ5d.jpg)

**Step a:** The clerk is prompted to provide his identity. He provides his email address and click on 'Identify Me' button.

![http://i.imgur.com/Osxh5zW.jpg](http://i.imgur.com/Osxh5zW.jpg)

If the provided email address matches any one of the entries in the 'clerkName' from the 'clerkTB', then he is recognized as a valid clerk user. He will then be allowed to browse the inventory items and request items. If the clerk email address is not a valid one or doesn't exist in the table, then he is not recognized as a valid user. The instance can end here.

**Step b:** Assuming the happy path, the clerk is recognized as a valid clerk user. He will now be provided a screen that displays all the items from the 'inventoryTB' table as seen in the screenshot.

![http://i.imgur.com/nPEFPxh.jpg](http://i.imgur.com/nPEFPxh.jpg)

The clerk needs to select one of the items that he thinks is running short and needs to be ordered for.

He can select the item by clicking on the radio button against one of the displayed items.

![http://i.imgur.com/d9eTrKZ.jpg](http://i.imgur.com/d9eTrKZ.jpg)

The clerk can click on 'Submit' button after selecting one of the items.

**Step c:** The clerk is then taken to another screen that displays only that item that he selected in the previous page. This is to confirm his selection.

He can select that displayed one item and click on 'Confirm Submit' button.

![http://i.imgur.com/hStj6Z6.jpg](http://i.imgur.com/hStj6Z6.jpg)

**Step d:** On confirming the selection, the clerk is next taken to a page where in he must be allowed to change the quantity of the item. The clerk can edit this field called 'Needed Quantity' and submit the order request to the manager for approval.

![http://i.imgur.com/ONL1cGY.jpg](http://i.imgur.com/ONL1cGY.jpg)

As seen in the above screenshot, the 'Needed Quantity' is updated to 100. This means, the clerk is ordering for 100 pieces of that selected item.

At this stage, the clerk is done with his job of browsing the inventory, identifying the item that is running short and logging a request for that selected item.


**Customer**

**Step 1.2:** **Assuming that the user is a customer, the user needs to select user type as 'customer' as shown in the screenshot.
Once the user has identified himself as a customer, he will then be taken to customer information page.**

![http://i.imgur.com/8u8BKHB.jpg](http://i.imgur.com/8u8BKHB.jpg)

**Step a:** The customer is prompted to provide his identity. He provides his full name and his email address and click on 'Submit' button.

![http://i.imgur.com/kJM3gT4.jpg](http://i.imgur.com/kJM3gT4.jpg)

Unlike clerk identity check, there is no identity check performed on the customer.
However, a customer fullname and emailaddress are to be made mandatory. On failing to provide these two field details, the instance should end.

Assuming the happy path that the customer has provided his full name and his email address,
**All the steps: stepb, stepc, stepd is the same for the customer too(Like the clerk tasks)**


**Manager**

**Step 5:** Once the clerk/customer has submitted the request, it will be received by the manager. The manager needs to review the request. He can approve or reject this request.

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

## Sample Business Process ##
You may choose to construct your business process as shown below:
![http://i.imgur.com/fp2i3Gd.jpg](http://i.imgur.com/fp2i3Gd.jpg)

The process used as a linked process for the clerk item request and customer item request can be designed as seen here:
![http://i.imgur.com/Ijpzn32.png](http://i.imgur.com/Ijpzn32.png)