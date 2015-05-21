#Project.

[Back to Table of Contents](TableOfContents.md)

# Project: Library System #


This project depicts a simple process for library management.

## Participants ##

  * STUDENT
  * LIBRARIAN
  * LIBRARY\_SYSTEM
  * UNIVERSITY\_ADMIN SYSTEM

Note: These determine the Swim lanes in the process.



## Process Modules ##

  * Borrow item(s)
    * (a)Borrow Academic item(s)
    * (b)Borrow Reference item(s)
  * Return item(s)
  * Calculate Fine
  * Block user account
  * Unblock user account
  * Send emails
    * (a)Confirmation email
    * (b)Blocked email
    * (c)Unblocked email

## Prerequisite ##

Create a business object with the name: LibraryItem

Let this business object contain the following 11 parameters:

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


## Provided: ##
Use the provided WSDL to design process modules.

### WSDL: ###
https://bpm.site.uottawa.ca:9443/teamworks/webservices/LIBMGT/LibraryManagement.tws?WSDL

The Webservice contains 15 operations:

  * ### getAvailableAcademicItems ###
This operation can be used to obtain all the available academic item(s).

  * ### getAvailableReferenceItems ###
This operation can be used to obtain all the available reference item(s).

  * ### getBorrowedItemsByUser ###
This operation gives all the item(s) borrowed by the current user.

  * ### getUserStatus ###
This operation returns the status of the user. It tells if the user account is blocked or unblocked.

  * ### blockOrUnblockUserAccount ###
This operation can be used to block user account. The same operation can also be used to unblock the blocked user account.

  * ### checkDueItemsBeforeBlockingUserAccount ###
This operation can be used to check if the user has any due item(s) before blocking his account.

  * ### sendConfirmationEmailAfterBorrow ###
This operation can be used to send an email to the borrower soon after he/she has borrowed item(s) of his/her interest.

  * ### sendEmailAfterBlockingTheUserAccount ###
This operation can be used to send an email to the user after blocking his account.

  * ### sendEmailAfterUnBlockingTheUserAccount ###
You may use this operation to send an email to the user, when his account is unblocked. If the user has returned all the due item(s) with the calculated fine amount, the blocked user account has to be unblocked. Once the user account is unblocked, he has to be notified with an unblocked email.

  * ### calculateFineonTheOverDueItems ###
This operation will calculate the fine on all the due item(s).

  * ### sendReminderEmail ###
This operation can be used to send reminder email to the user when his borrowed item(s)is/are reaching the due period.

  * ### setBorrowedItemsToBorrowed ###
This operation can be called soon after the user has borrowed item(s). This operation will set the status of the borrowed item(s) to 'Borrowed' in the DB trabsaction table. Thus these items will not be shown as 'Available' to other users.

  * ### setReturnedItemsToAvailable ###
This operation should be called soon after the user has returned the item(s). This will set the status of those returned item(s) to 'Available'. Thus these item(s) are made available for other users.

  * ### waitForGivenNumberOfSeconds ###
This operation is used to wait for given number of seconds before performing any next action.
You may use this to wait for 'n' seconds before blocking user account, before sending reminder email.

## User Story Walk Through with Screenshots ##
[Process WalkThrough & User Story](LibraryProject_ScreenShots.md)


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