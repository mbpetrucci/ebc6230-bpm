#Project: User Story and Process Walk Through

[Back to Table of Contents](TableOfContents.md)

[Library Project Description](LibraryManagementProjDesc.md)

## Overview of the Library Management Business Process ##
A student visits homepage of the university library and is given two options to select from: (A) Borrow Academic item(s)  (B) Borrow Reference item(s).

'Item' here can be a book or a DVD/CD.
And a student can borrow more than 1 item at a time.

Snapshot of the homepage:

![http://i.imgur.com/K9ldzz6.png](http://i.imgur.com/K9ldzz6.png)


## (1) Borrow Item(s) ##
  * On selecting the borrow type, the student should be taken to 'Browse and Select available/reference Item(s)' page.
The following image shows two different pathways based on the borrow type selected.
![http://i.imgur.com/HYJgPcH.jpg](http://i.imgur.com/HYJgPcH.jpg)
  * The page should display all the available item(s) of selected category (Academic/Reference).
  * The student should be able to select one or more books from the available list and submit their selection for borrow.

The screenshot of this page is as shown below:
![http://i.imgur.com/buY00yI.jpg](http://i.imgur.com/buY00yI.jpg)

In the above image, it is understood that the student selected 'Borrow Reference Items' from the main page and was then brought to 'Browse and Borrow Reference Items' page.
So, this page is only meant for browsing, selecting the items for borrow and submitting the request for borrow. Note that the student has not borrowed the books yet.

  * After the selection of items is submitted for borrow, one of the two things should happen:
    * If the student account is blocked, the system should next display a 'account blocked message' and should not perform any DB updates.
This is clearly depicted in the following screenshot
![http://i.imgur.com/4zgoaJh.png](http://i.imgur.com/4zgoaJh.png)

  * The system should approve the items to borrow if the student account is not blocked. All the selected items should be marked as borrowed in DB against the student's username and the due date will be automatically calculated for the borrowed items. Also, successful message should be displayed to the student for his/her borrow action as seen in the following screenshot
![http://i.imgur.com/PMgMcsW.jpg](http://i.imgur.com/PMgMcsW.jpg)

The image below shows how the display borrow success message activity is constructed. As seen here, the borrowed books are updated to DB and then are retrieved and showed to the student.
![http://i.imgur.com/BpT2Ha8.jpg](http://i.imgur.com/BpT2Ha8.jpg)

  * If the borrow is successful, the control is given to the Librarian's Return Item(s). So, this request will sit in the librarian's bucket.
  * If the borrow is not successful due to blocked status of the account, the error message is displayed and the process should terminate there.


## (2) Return Item(s) ##
  * This task is to be performed by the librarian.
  * The student is supposed to get the books to the librarian for return.
  * The librarian is then responsible to fetch all the borrowed books of this student and mark only those returned books as 'Returned'.
  * Soon after the librarian submits the action to return the selected items, the items are to be marked 'Available' in the DB for next borrow.

The image below shows the process level design for 'Return' activity
![http://i.imgur.com/n580PJu.jpg](http://i.imgur.com/n580PJu.jpg)

The following image displays the interface of the librarian:
![http://i.imgur.com/hNCw6P0.jpg](http://i.imgur.com/hNCw6P0.jpg)
As seen in the above screenshot, the student has returned two books out of four books that he initially borrowed.
So, the librarian marks against the books that the student gets to return and clicks on Return button.


## (3) Collect Fine ##
  * This task needs to be performed by Financier.
  * A Timer-UCA is used initiate this task. This UCA is timed to run everyday at 9:00AM. The UCA invokes system call to DB which checks if there are any items that is not returned within due date. Also, the system task will update the status of the User to 'Owing' if the student owes any fine. The system task updates the user status to 'Blocked' if the owing amount is >= 100. Else, if there is no due amount, the system sets the user status to 'OK'.

So, In brief:
Every day at 9am the system checks for overdue books and adds a fine of $1 per overdue book to amount owing for student.
> ### CONDITIONS ###
> a.  If the account status is nothing, THEN change status to owing, send account to Finance

> b.  If the account status is owing AND amount owing >=$100; change status to  blocked, send blocked message to Student

> c. Otherwise nothing (end)

  * The flow is given to Financier to collect fine until all the amount owed by the student is cleared (becomes 0).
The following screenshot shows the interface of the cashier.
![http://i.imgur.com/jYqiXsW.jpg](http://i.imgur.com/jYqiXsW.jpg)

As seen here, the student4 owes totally 4$ fine. And he came to the financier and pays $2. So, the status of the student still remains 'Owing'. And he needs to come to the cashier to pay the remaining due amount. Also, if the items that has crossed the due date is not returned, the fine is recalculated on those items.

  * When Financier received fine payment, subtract fine from amount owing for student.
> ### CONDITIONS ###
> a. If the amount owing is >0, send account to Finance

> b. If amount owing is <=0, change status to nothing (end)


## (4) Blocking the user ##
  * This is a system task.
  * Whenever the UCA runs everyday at 9:00AM, it checks for all those users whose total fine owned has reached 100. And changes the status of that user as 'Blocked'.
  * After blocking the account of the student, the system sends an email to that student, to indicate the status of his account.

The following is the screenshot of the blocked email received by student4.
![http://i.imgur.com/X4wmtHB.png](http://i.imgur.com/X4wmtHB.png)

The below screenshot describes how system task is designed.
![http://i.imgur.com/KO8bd4h.jpg](http://i.imgur.com/KO8bd4h.jpg)



## High-Level Business Flow ##
![http://i.imgur.com/rYPofqS.jpg](http://i.imgur.com/rYPofqS.jpg)