[Back to Table of Contents](TableOfContents.md)

## Assignment 2 ##

This assignment is in continuation of Assignment 1. You are expected to improve Assignment 1 by addressing the following requirements-

  * Create a business object called 'InventoryItems'. The object should have the following 4 parameters-

materialNumber (STRING);

materialDescription (STRING);

unitPrice (STRING);

quantity (STRING)


  * Replace the clerk request form created in Assignment 1 by a form that displays table/list of inventory items fetched from database.

Use the business object created- 'InventoryItems' to map the records fetched from database.

  * The clerk should now be able to see all the inventory items and should be able to select only 1 item from the displayed list and submit the selection.

  * The clerk selected item (in the previous step) should be displayed in the next human coach/user interface. The clerk should be able to change the quantity of the selected item in this human coach/user interface.
He should then submit this request to the manager.

  * The manager views the details of the request and can either approve the request or reject the request.

  * If the manager approves the request, the action should be saved to database.
Also, in the next step, the manager should be displayed with the details of the request that he just approved, by fetching the written record from the database.

**Note :** The record written to DB should be fetched from DB and shown to the manager.

  * If the manager rejects the request, the action should not be saved to database and the process should end at this stage.



## Use the following WSDL and its operations ##

WSDL:
https://bpm2.site.uottawa.ca:9443/teamworks/webservices/AWS/Assignments.tws?WSDL

Operations:

**getInventoryItems**

This operation will get list of items from the DB inventoryTB table.
The operation accepts no input. The output of the operation is a list of inventoryItems.


**writeApprovedRecordToDatabase**

This operation will write a record to DB table- purchasingTB.
The operation accepts requestorName, requestorEmailAddress, and list of inventoryItems as inputs. The output of the operation is not defined.


**fetchapprovedRecordFromDatabase**

This operation will fetch the record that is written to DB on manager's approval. The operation accepts requestorName, requestorEmailAddress and materialNumber as inputs. It outputs list of inventory items.


### Process Walkthrough ###
[Assignment 2 Process Walkthrough](assignment2_processwalkthrough.md)


### Deliverable ###
Kindly email the TA cc'ing professor the following details on completion of the assignment-
  * Group Number
  * Names of Group Members
  * Process App Name
  * Process Name



### Related tutorials ###

[Tutorial: Creating and Using Business Objects in a Business Process](TutorialBusinessObject.md)

[Tutorial: Using a Webservice (WSDL)](WebServiceIntegration.md)

[Tutorial: Create a list view on the coach from variables](ListView.md)

[Tutorial: Multiple Selection of Items](SingleAndMultiSelect.md)

[Tutorial: Decision Gateway](Tutorial_DecisionGateway.md)