#SOA Documentation


[Table Of Contents](TableOfContents.md)


Following are the list of services that can be used in building Library Management business process-


  * Service Name: **EBC6230Project\_RareBookCollection
  * WSDL:** https://bpm2.site.uottawa.ca:9443/teamworks/webservices/RBC/EBC6230Project_RareBookCollection.tws?WSDL

**Operations:**

### getStudentDetails ###
  * Description: This operation fetches the details of a student.
  * Input: username (STRING)
    * Eg: student4
  * Output: studentDetails (Business Object: StudentDetails; Is List: No)
    * Eg: student4|Kavya|Mallur|Computer Science|AccountBlocked

### getStatusofStudentAccount ###
  * Description: This operation returns the status of student account (blocked/unblocked)
  * Input: username (STRING)
    * Eg: student4
**Output: isBlocked (BOOLEAN)
    * Eg: true (This indicates that the student4 user’s account is blocked).**

### getavailableRareBooks ###
  * Description: This operation fetches all the available books from Lib\_Item database.
  * Input: No Input
  * Output: libraryItems (Business Object: LibraryItem; Is List: Yes)
    * Eg: 1|BPM|book||McArthur|Author1|Available|null|null|null|null|200.20|
> > > 6|I love Java|cd|McArthur|Author2|Available|null|null|null|null|320.20|


### setBorrowedBooktoBorrowed ###
  * Description: This operation marks the borrowed item to ‘Borrowed’. This operation is used to change the status of the item in Lib\_Item table.
The operation also blocks the user account. i.e, it changes the IsBlocked status in Lib\_User to true, when the user has borrowed a book.
In addition, the operation also creates an entry in Lib\_Transaction on successful borrow.
  * Inputs:
    * Input1: username (STRING)
      * Eg: student4
    * Input2: libraryItems (Business Object: LibraryItem;  Is List: Yes)
      * Eg: 1| BPM|book||McArthur|Author1|Available|null|null|null|null|200.20|


### setReturnedBooktoReturned ###
  * Description: This operation marks the returned item to ‘Available’. This operation is used to change the status of the item in Lib\_Item table.
The operation however does not unblock the user account.
  * Inputs:
    * Input1: username (STRING)
> > > Eg: student4
    * Input2: libraryItems (Business Object: LibraryItem;  Is List: Yes)
> > > Eg: 1| BPM|book||McArthur|Author1|Borrowed|null|null|null|null|200.20|


### updateOnReportLost ###
  * Description: This operation marks the lost item as ‘Lost by- 

&lt;username&gt;

’. This operation is used to change the status of the item in Lib\_Item table, when the item is reported as lost.
The operation also updated the lib\_transaction table to mark the end of transaction.
The operation however does not unblock the user account.
  * Inputs: input1: username (STRING)

> > Eg: student4
> > Input2: libraryItems (Business Object: LibraryItem;  Is List: Yes)
> > Eg: 1| BPM|book||McArthur|Author1|Borrowed|null|null|null|null|200.20|


### allowUserToBorrowAgain ###
  * Description: This operation unblocks the user account.
  * Inputs: input1: username (STRING)
> > Eg: student4
> > Input2: libraryItems (Business Object: LibraryItem;  Is List: Yes)
> > Eg: 1| BPM|book||McArthur|Author1|Borrowed|null|null|null|null|200.20|


### isBookNotReturned ###
  * Description: This operation checks if the borrowed book is returned by the student.
  * Inputs: username (STRING)
> > Eg: student4
  * Output: isBookNotReturned (BOOLEAN)
> > True    (Indicating the book is not returned. False indicates the book is successfully returned)


### getTotalFine ###
  * Description: This operation fetches the current fine on the student account.
  * Input: username (STRING)
    * Eg: student4
  * Output: totalFine (INTEGER)
    * Eg: 120


### add10FineForDue ###
  * Description: This operation add a fine of $10 to the already existing amount in the Lib\_User table.
The operation also adds the fine in the Lib\_Transaction table.
  * Inputs: username (STRING)
> > Eg: student4
  * Output: studentDetails (Business Object: StudentDetails;  Is List: Yes)
> > Eg: student4|Kavya|Mallur|Computer Science|AccountBlocked




### add1000FineForLost ###
  * Description: This operation add a fine of $1000 to the already existing amount in the Lib\_User table.
The operation also adds the fine in the Lib\_Transaction table.
  * Inputs: username (STRING)
> > Eg: student4
  * Output: studentDetails (Business Object: StudentDetails;  Is List: Yes)
> > Eg: student4|Kavya|Mallur|Computer Science|AccountBlocked



### setFineTo0 ###
  * Description: This operation clears the fine amount in the Lib\_User table.
  * Inputs: username (STRING)
> > Eg: student4
  * Output: studentDetails (Business Object: StudentDetails;  Is List: Yes)
> > Eg: student4|Kavya|Mallur|Computer Science|AccountBlocked


### send EmailToStudentOnAddingFine ###
  * Description: This operation sends an email to the student, when a fine is added to the student account, for crossing the return due date.
  * Inputs:
    * Input1: username (STRING)
      * Eg: student4
    * Input2: studentDetails (Business Object: StudentDetails;  Is List: Yes)
      * Eg: student4|Kavya|Mallur|Computer Science|AccountBlocked



## What Web service operations to call when? ##
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