#Project.

[Back to Table of Contents](TableOfContents.md)

# Project: Rare Books Collection #

Use the IBM Process Designer to design a business model for Borrow process from Rare Books Collection.

The process should involve 4 participating actors:
  * STUDENT
  * LIBRARIAN
  * CASHIER
  * LIBRARY SYSTEM
Note: These determine the Swim lanes in the process.

The business process requirements are as follows:
  1. The process that will be implemented should strictly be for borrowing a book from the rare books collection at the library.

> 2. A student can borrow a rare book for 2 minutes.  At any time student can borrow only one rare book and Once a rare book is borrowed, student cannot borrow a second rare book until the borrowed book is returned and all fine (if exists) is cleared.

> 3. If the rare book is not returned within 2 minutes there is a $10 fine and an email should be sent to the student informing the student that the rare book must be returned immediately, and the fine should be paid.

> 4. If the rare book is not returned within 1 minute of the email being sent, there is another $10 fine and another email should be sent to the student.

> 5. Step 4 should be repeated until the rare book is either returned or reported as lost to the librarian.

> 6. If a rare book is reported lost, there is one final fine of $1000. No need of email in this scenario.

> 7. The student must pay all money owed to the cashier only AFTER the book is returned or reported lost.

> 8.  If all money owed has been paid, and the rare book has been returned or reported lost, then the student is allowed to borrow another rare book (i.e. start over at step 2).



## Prerequisite ##

  1. Create a business object having 11 parameters.
Business Object: LibraryItem
Parameters:

![http://i.imgur.com/1Uwtrsl.jpg](http://i.imgur.com/1Uwtrsl.jpg)

> 2. Create another business object having 11 parameters:
Business Object: StudentDetails
Parameters:
![http://i.imgur.com/qwDxH9g.jpg](http://i.imgur.com/qwDxH9g.jpg)


## Provided: ##
Use the provided Webservice to design process modules.
The webservice has several needed operations that can be used to construct a business model for Rare Books Collection.

### WSDL: ###
https://bpm2.site.uottawa.ca:9443/teamworks/webservices/RBC/EBC6230Project_RareBookCollection.tws?WSDL


Use the following Webservice operations to construct the business process:
  * ### getStudentDetails ###
This WS operation accepts userName as input and returns all the details of the student matching the provided userName. So, the i/p is of String type, while the o/p will be of StudentDetails type list.

Note: You may pass in tw.system.user.fullName for the input of this service.
tw.system.user.fullName has the username of the user who has logged into BPM.

For Eg: If you have logged in as student4, tw.system.user.fullName variable has the value "student4" in it.

  * ### getAvailableRareBooks ###
This operation can be used to obtain all the available rare books.
This operation has no inputs. And the operation returns all the available rare books. The student can browse through this available list and choose one book for borrow. So, the o/p is of LibraryItem type list.

  * ### getStatusOfStudentAccount ###
This WS operation is used to check if the user account is blocked. So, the operation accepts username of string type as i/p and returns True if Blocked or False if not blocked. So, the o/p is of boolean type.

  * ### setBorrowedRareBookStatusToBorrowed ###
This operation can be called soon after the user has selected and submitted rare book for borrow. This operation will set the status of the borrowed book) to 'Borrowed' in the DB Lib\_Transaction table. And this book will not be shown as 'Available' to other students.
This operation also block the user for successfully performing the borrow transaction and there by avoiding the user to borrow another book without returning previously borrowed book.
This operation accepts student username(string) and selected rare book(LibraryItem, List) as input. The operation has no output returned.

  * ### getBorrowedRareBookOfStudent ###
This operation gives the rare book, borrowed by the current user.
The operation accepts userName of string type as input and returns list of borrowed rare books. So the o/p is of LibraryItem type list.

  * ### setReturnedRareBookStatusToAvailable ###
This operation should be called soon after the user has returned the borrowed book to the librarian. This will set the status of the returned rare book to 'Available'. And this item is then made available for other students.
So, this operation accepts username of string type and list of rare book(s) of LibraryItem type. And this operation returns nothing. So, no need of using o/p variable, when calling the service operation.

  * ### isBookNotReturned ###
This WS operation is used to check if the borrowed rare book is returned by the student.
So, this operation accepts username of string type as an input and returns true if the book is not returned yet.

  * ### sendEmailToStudentOnAddingFine ###
This operation can be used to send an email to the user whenever fine is added. This operation accepts userName of string type. And has no o/p.

  * ## updateOnReportLost ##
This operation should be called once the student has reported the book as lost.
The operation accepts userName of string type and a list libraryItems of complex type as inputs and returns no output.

  * ### allowUserToBorrowAgain ###
This webservice operation should be used to update the student account status to unBlocked. The student should be allowed to borrow another book after the previously borrowed book is returned and fine is completely cleared (if exists).

  * ### add10FineForBookDue ###
This operation should be called when $10 fine needs to be added to the student account for the borrowed book, if the book is not returned within deadline. The operation accepts userName of string type as input and returns student details(list) as output which displays the accumulated fine.

  * ### add1000FineForLostBook ###
This operation should be called when $1000 fine needs to be added to the student account when the student reports the borrowed book as lost. The operation accepts userName of string type as input and returns student details(list) as output which displays the accumulated fine.

  * ### setFineTo0 ###
This webservice operation needs to be called after the student makes fine payment to the cashier. This operation can be used to nullify the fine.
The operation accepts userName as input and returns student details(list) as output.




### Note ###
Above operations are the must-use operations, which means you should use all the above listed operations while building the required  'Borrow' business process solution for Rare Books Collection. However, the web service created has other operation(s) which you may/may not prefer to use for this project.


> ## User Story Walk Through with Screenshots ##
[Process WalkThrough & User Story](RareBooksCollectionProcessWalkthrough.md)


> ## What Web service operations to call when? ##

  * Browsing books- getAvailableRareBooks
  * Obtaining student details- getStudentDetails
  * To check if the user is blocked or unblocked - getUserStatus
  * After successful borrow of book, to mark the book as borrowed and also to block the user from borrowing another book- setBorrowedRareBookStatusToBorrowed
  * To obtain details of the borrowed book- getBorrowedRareBookOfStudent
  * On returning the book- setReturnedRareBookStatusToAvailable
  * On reporting the book as lost- updateOnReportLost
  * To add $1000 fine- add1000FineForLostBook
  * To add $10 fine- add10FineForBookDue
  * To unblock the user after the book is returned- allowUserToBorrowAgain
  * To set fine to 0- setFineTo0






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
  * [Tutorial: Making Process Variables' value visible in the Process Portal](ProcessVariablesVisibleInPortal.md)
  * [Tutorial: Timer Event](TimerEvent.md)