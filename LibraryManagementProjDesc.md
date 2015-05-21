#Project.

[Back to Table of Contents](TableOfContents.md)

# Project: University Library System #

Use the IBM Process Designer to design a business process for university library management. The business process requirements are as follows:

The process should involve 4 participating actors:
  * STUDENT
  * LIBRARIAN
  * FINANCIER
  * LIBRARY SYSTEM

Note: These determine the Swim lanes in the process.

The process should have the following unit:
  * Borrow item(s)
  * Return item(s)
  * Compute fine
  * Collect fine
  * Check for Over Due amount (100 and above)
  * User Account Status change
  * Blocked emails after blocking user accounts
  * Update paid fine and recalculate overdue

## Prerequisite ##

Create a business object having 11 parameters.
Business Object: LibraryItem
Parameters:

  * TitleID (INTEGER)
  * Title (STRING)
  * Type (STRING)
  * PublisherName (STRING)
  * AuthorName (STRING)
  * ItemStatus (STRING)
  * fine (DECIMAL)
  * borrowedDateTS (DATE)
  * returnedDateTS (DATE)
  * dueDateTS ( DATE)
  * ItemCost (DECIMAL)

Create another business object having 11 parameters:
Business Object: StudentDetails
Parameters:
  * UserID (INTEGER)
  * StudentNumber (Integer)
  * FirstName (STRING)
  * LastName (String)
  * Department (STRING)
  * EmailId (STRING)
  * UserName (STRING)
  * UserStatus (STRING)
  * IsBlocked (Boolean)
  * TotalFine (INTEGER)


## Provided: ##
Use the provided Webservice to design process modules.
The webservice has several needed operations that can be used to construct a business model for library management.

### WSDL: ###
https://bpm.site.uottawa.ca:9443/teamworks/webservices/LIBMGT/LibraryManagementNew.tws?WSDL

Use the following Webservice operations to construct the business process:

  * ### getStudentDetails ###
This WS operation accepts userName as input and returns all the details of the student matching the provided userName. So, the i/p is of String type, while the o/p will be of StudentDetails type list.

  * ### getAvailableAcademicItems ###
This operation can be used to obtain all the available academic item(s).
This operation has no inputs. And the operation returns all the available academic items. So, the o/p is of LibraryItem type list.

  * ### getAvailableReferenceItems ###
This operation can be used to obtain all the available reference item(s).
This operation has no inputs but returns all the available reference items. The o/p is of LibraryItem type list.

  * ### getUserAccountStatus ###
This WS operation is used to check if the user account is blocked or not. So, the operation accepts username of string type as i/p and returns True if Blocked or False if not blocked. So, the o/p is of boolean type.

  * ### setBorrowedItemsToBorrowed ###
This operation can be called soon after the user has selected and submitted item(s) for borrow. This operation will set the status of the borrowed item(s) to 'Borrowed' in the DB Lib\_Transaction table. Thus these items will not be shown as 'Available' to other users.
This operation accepts student username(string) and selected library Items(LibraryItem, List) as input. The operation has no output returned.

  * ### getBorrowedItemsByUser ###
This operation gives all the item(s) borrowed by the current user.
The operation accepts userName of string type as input and returns list of borrowed items. So the o/p is of LibraryItem type list.

  * ### setReturnedItemsToAvailable ###
This operation should be called soon after the user has returned the item(s) to the librarian. This will set the status of those returned item(s) to 'Available'. Thus these item(s) are made available for other users.
So, this operation accepts username of string type and list of all the returned items of LibraryItem type. And this operation returns nothing. So, no need of using o/p variable, when calling the service operation.

  * ### isOverDueExist ###
This WS operation is used to check if any overdue exists the items that are borrowed by a user.
So, this operation accepts username of string type as an input and returns Yes/No string type o/p.

  * ### computeOverDueAmount ###
This operation is called if isOverDieExist o/p is yes. This operation will compute the overdue amount for a particular user based on the borrowed date and expected return date and updates the due amount for all the borrowed items.
So, the operation accepts userName of string type as an i/p and returns o/p in the form of list of StudentDetails.

  * ### setUserStatusToBlocked ###
This operation is used to block the user account. This operation will set the status column of the Lib\_User table to 'Blocked' for the given userName. If the total fine on all the borrowed items is equal to or  crossed over due amount 100, then the user account status should be changed to Blocked.
So, the i/p to this operation is userName of string type. While the operation returns list of StudentDetails.

  * ### setUserStatusToOwing ###
This operation will set the status column of the Lib\_User table to 'Owing' for the given userName. If fine is accumulated on the user account but has not reached overdue of 100, then the status is changed to 'Owing'.
So, the i/p to this operation is userName of string type. While the operation returns list of StudentDetails.

  * ### setUserStatusToOK ###
This operation will be called to reset the user status to OK, when there exists no accumulated fine on the user.
So, the i/p to this operation is userName of string type. While the operation returns list of StudentDetails.

  * ### sendBlockedEmailToUsers ###
This operation can be used to send an email to the user after blocking his account. So, once the account status is changed to 'Blocked' the student should receive an email about his blocked account status.
This operation accepts userName of string type. And has no o/p.

  * ### updateDueAmount ###
This webservice operation should be used to update the fine amount. Whenever the student pays fine, the paid amount should be deducted from the current fine amount. The student can pay complete/partial fines.
But the account will remain blocked until the student completely settles the over due amount (100 or above).
This operation accepts userName of string type and collected fine amount of Integer type as inputs. And returns StudentDetails type result as an o/p.


### Note ###
Above operations are the must-use operations, which means you should use all the above listed operations while building a business process solution for library project. However, the webservice created has other operations which you may/may not prefer be use for this project.



> ## User Story Walk Through with Screenshots ##
[Process WalkThrough & User Story](librarymanagementWalkThrough.md)


## Related Tutorials ##

  * [Tutorial: A Simple Human Service Coach](SimpleCoach.md)
  * [Tutorial: Binding Variables to coach components](VariableBinding.md)
  * [Tutorial: Decision Gateway](Tutorial_DecisionGateway.md)
  * [Tutorial: Using Calculator Webservice](WebServiceIntegration.md)
  * [Tutorial: Using the created Data Source in Process Designer](Using_DataSource_In_IBM_BPM_Process_Designer.md)
  * [Tutorial: Creating and Using Business Objects in a Business Process](TutorialBusinessObject.md)
  * [Tutorial: Create a list view on the coach from variables](ListView.md)
  * [Tutorial: Sub-Process](TutorialSubprocesses.md)
  * [Tutorial: Linked Process](TutorialLinkedProcess.md)
  * [Tutorial: Time Elapsed UCA](TimeElapsed_UCA.md)