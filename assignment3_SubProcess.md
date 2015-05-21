[Assignment 3](assignment3.md)

# Assignment(3) Part(1) Subprocess #

This part of assignment3 is an extension of assignment2.

## Question ##

The purpose of Part (1) is to use the concept of “Sub-process” to hide the granular details of the process.
The process has three main participants:
store clerk, the manager and the system.

The workflow of the business process:


  * The store clerk browses the list of items that are available in the inventory. (Items seen in inventoryTB should be displayed). The list should contain information about the material number, item description, unit price.
  * Then, he selects only 1 item from the list.
  * Next, he changes the quantity field value of the selected item only (in a separate browser) with information about the user: clerk name and email address.
  * The store clerk finally submits the request to the manager for approval.


### Note: ###
All the above summarized steps should be encapsulated in a single activity.

Use subprocess concepts to encapsulate-
(a) getting inventory items from DB.

(b) displaying the inventory items to the clerk.

(c) Clerk selecting an item from the displayed inventory items list.

(d) Clerk editing the selected item (quantity, adding requestor details) before submitting the request to manager.


  * Once the manager receives the request, he can either approve the order of the selected items or reject it.
  * If the order is approved, the details of the ordered materials are updated in the database. When the order is placed, the manager should be able to view the placed orders. So, the process should contain an activity to display the orders from the database.
  * If the order is not approved by the manager, the process should successfully terminate.


### Process Walkthrough ###
[Assignment3 SubProcess Process Walkthrough](assignment3_subprocess_processwalkthrough.md)


### Related Tutorials ###
[Sub-Processes ](TutorialSubprocesses.md)