[Assignment 2](Assignment2.md)

#summary One-sentence summary of this page.

# Assignment(2) Part(1) Subprocess #

## Question ##
Part (1) involves ordering the material item once it is approved by the store manager. The purpose of Part (1) is to use the concept of “Sub-process” to hide the granular details of the process.
The process has three main participants: the store clerk, the manager and the system.
The workflow of the business process:

  * The store clerk can login by typing his email to verify his identity. Use one of the records seen in the clerkTB database table.
  * The store clerk browses the list of items that are available in the inventory. (Items seen in inventoryTB should be displayed). The list should contain information about the material number, item description, unit price, current quantity.
  * Then, he selects 1(or more) item(s) from the list.
  * Next, he adds the new quantities of the selected items only (in a separate browser) with information about the user: clerk name and email address.
  * The store clerk finally submits a request to the manager for approval.
  * Once the manager receives the request, he can either approve the order of the selected items or reject it.
  * If the order is approved, the details of the ordered materials are updated in the database (see the database details below). When the order is placed, the manager should be able to view the placed orders. So, the process should contain an activity to display the orders that are placed by the manager.
  * If the order is not approved by the manager, the process should successfully terminate.
  * Use the sub-process concept to encapsulate the Browsing and Selection processes performed by the clerk.

## Process Walkthrough ##
[Screenshots describing the process flow](Assignment2_SubProcess_ScreenShots.md)

## Prerequisites ##
  * Create a Business Object called: InventoryItems
Add the following parameters to this complex data:
  * materialNumber(INTEGER)
  * descrip (STRING)
  * unitPrice (DECIMAL)
  * qty (INTEGER)

## Provided ##

You may use the given webservice WSDl to develop the assignment solution.

WSDL:
https://bpm2.site.uottawa.ca:9443/teamworks/webservices/ASGN2/Assignment2_SubProcess.tws?WSDL

Operations:
  * clerkUserNameVerification
This operation accepts clerk email address as input. It checks in the DB if the clerk exists with the provided email address.

  * getInventoryItemsFromDataBaseTable
This operation fetches all the records from the inventory table. You may use the result of this operation to display to the clerk, who will select an item that is running short in the inventory.

  * removeUnSelectedItems
This operation can be used to eliminate unselected items from the list of all the displayed items. The clerk can choose one item from the list of all inventory items and the remaining items are to be removed from the list.

  * writeRecordToDataBase
You should use this operation to write the record that is approved by the manager.

  * getWrittenRecordFromDataBase
This operation should be used to display the record that is written to the database successfully using the previous operation.

## Sample DB table values with header is provided here ##
  * Data Source: jdbc/EBC\_6230\_BPMCourse
  * Database: EBC\_6230\_BPMCourse
  * Table1: inventoryTB
  * Description: The table displays all the items in the inventory
  * Table1 columns:  materialNumber(VARCHAR), descrip(VARCHAR), unitPrice(DECIMAL), qty(INTEGER)

![http://i.imgur.com/7qZJbQP.png](http://i.imgur.com/7qZJbQP.png)

  * Table2: clerkTB
  * description: The table displays the store clerk details in the store. The store has 4 major clerks belonging to 4 different departments.
  * Table2 columns: clerkName(VARCHAR), clerkEmailAddress(VARCHAR), clerkDepartment(VARCHAR)

![http://i.imgur.com/vWlHxqt.png](http://i.imgur.com/vWlHxqt.png)

  * Table3: requestItemsTB
  * Description: The table contains the records that are approved by the manager. This table logs all the materials that are requested by the clerk/customer and that are approved by the manager.
  * Table3 Columns: requestorName(VARCHAR), requestorEmailAddress(VARCHAR), materialNumber(VARCHAR), descrip(VARCHAR), unitPrice(DECIMAL), qty(INTEGER)

![http://i.imgur.com/0x4JgBe.jpg](http://i.imgur.com/0x4JgBe.jpg)


## Related Tutorials ##
  * [Sub-Processes ](TutorialSubprocesses.md)

  * [Tutorial: Using Calculator Webservice](WebServiceIntegration.md)

  * [Tutorial: Creating and Using Business Objects in a Business Process](TutorialBusinessObject.md)