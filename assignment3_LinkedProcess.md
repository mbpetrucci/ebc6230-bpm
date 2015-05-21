# Assignment3 Linked Process

[Back to Table of Contents](TableOfContents.md)

[Back to Assignment 3](assignment3.md)


# Assignment(3) Part(2) Linked Process #

## Question ##
Part (2) of Assignment(3) involves the use of Linked Process in designing a business process.


Alter Assignment 3 (Part1) to have both the store clerk and the customer request for an unavailable item. The requests should be then verified by the manager. The manager can approve or reject the requested item.

The process should have four main participants:

(a)the store clerk,

(b)the customer,

(c)the manager and

(d)the system.

The workflow of the business process is as follows:

  * The process is started by the store clerk.
  * The store clerk can select type of user who is submitting the request.
  * The request can be logged by store clerk or the customer can log the request taking clerk's help.
  * Select the user type, whether a store clerk or a customer (use Radio button)


**_User type: store clerk_**

  * The clerk browses the list of items that are available in the inventory. (Items seen in inventoryTB should be displayed).  The list should contain information about the material number, item description, unit price, current quantity.

  * Then, he selects only 1 item from the list.

  * Next, he changes the quantity of the selected item only (in a separate browser) with information about the user: clerk name and email address.

  * The store clerk finally submits a request to the manager for approval.


**_User type: customer_**

  * Similar to the store clerk, he should also be able to browse and edit the items in the inventory.

  * Then, he selects only 1 item from the list.

  * Next, he changes the quantity of the selected item only (in a separate browser) with information about the user: clerk name and email address and submits the request to the manager.


_**User type: Manager**_

  * Once the manager receives the request from the clerk/customer, he can either approve the request or reject the request.

  * If the request is approved, the details of the approval must be updated in the database. The process should contain an activity to display the approved record from the database to ensure the approval is successfully written to the DB.

  * If the request is not approved by the manager, the process should successfully terminate. Do not record the rejected record to database table.

  * Use the Linked process concept to capture the tasks commonly performed by the clerk and the customer (Get Inventory Items + Browse inventory + Request for the unavailable item)


### Process Walkthrough ###

Screenshots of business process flow can be seen here:

[Assignment3 Linked-Process Walkthrough](assignment3_linkedProcess_processwalkthrough.md)


### Related tutorials ###
[Linked Processes](TutorialLinkedProcess.md)