#Project: User Story and Process Walk Through

[Back to Table of Contents](TableOfContents.md)

[Project Description](Project_RareBooksCollection.md)

The following screenshot describes the sample business process model constructed for Borrow process of Rare Books Collection
## High-Level Business Flow ##
![http://i.imgur.com/Qho8d0f.jpg](http://i.imgur.com/Qho8d0f.jpg)


## Overview of the Rare Books Collection Business Process ##

  * A student visits homepage and is displayed with all his account details. He proceeds further to view all the available rare books.

Note: The student can borrow only one rare book at a time.

Snapshot of the homepage is shown here:
![http://i.imgur.com/pygntAR.jpg](http://i.imgur.com/pygntAR.jpg)

On clicking 'Next' button, the student is displayed with all the available rare books. As seen in the below screenshot, the student4 has selected 'Ask your system administrator' book for borrow.
![http://i.imgur.com/QxbWH5f.jpg](http://i.imgur.com/QxbWH5f.jpg)



  * Once the student has selected a rare book from the displayed available list, the student account is verified if the student has already borrowed a rare book or owes any fine on previously borrowed book.

> (a) If the student has no borrowed books and no fine, he will be displayed with a success message as seen in the below screenshot.
![http://i.imgur.com/cKDC5Ky.jpg](http://i.imgur.com/cKDC5Ky.jpg)

The process continues and the request is passed to Librarian, where the student can return borrowed book or report loss of the book.
The request is also sent in parallel to wait event, where the timer begins.

> (b) If the student has not returned previously borrowed book (or) that he owes fine on his previous borrowed book, then an error message is displayed to the student as seen in the below screenshot:
![http://i.imgur.com/vZjlZKg.jpg](http://i.imgur.com/vZjlZKg.jpg)
The process should end at this stage.



  * After the borrow of rare book, the 2-minutes timer begins. The student should return the book within 2 minutes of borrow. Else, $10 fine is added and a reminder email will be sent. The email snippet is as shown in the below screenshot:
![http://i.imgur.com/yK7kzNL.jpg](http://i.imgur.com/yK7kzNL.jpg)

After the first email, another timer (1-minute timer) begins. $10 fine is added to the previously existing fine if the student has not returned the book yet. This continues until the book is returned or reported as lost to the librarian.
Every time fine is added, an email is sent to the student as seen in the below screenshot:



  * After the book is returned/reported as lost, the timer stops.
(a) In case of loss of the borrowed book, $1000 fine is added to the existing fine and the student becomes eligible to make next borrow transaction only after clearing the fine.

(b) In case of book returned successfully, the student becomes eligible if he owes no fine.



  * The librarian is responsible for processing the Return/Report loss request from the student. The Librarian marks the rare book as returned, if the book is personally returned by the student to the librarian.
The book is marked lost if the student personally reports to the librarian.

(a) If the book is returned, the timer stops here. The librarian marks the book as returned. This is shown in the following screenshot.
At this point, if the user owes fine on this returned book, he needs to pay the fine to the cashier. After which he becomes eligible for the next borrow transaction.
![http://i.imgur.com/rGKaxBo.jpg](http://i.imgur.com/rGKaxBo.jpg)

(b) If the book is reported as lost, the system adds $1000 fine and the timer stops here. The student is then responsible for paying the fine to the cashier. After which he can make another borrow transaction.

> (i) The student should be able to pay full fine amount.
![http://i.imgur.com/3e6axyy.jpg](http://i.imgur.com/3e6axyy.jpg)

> (ii) In case the student makes partial payment, an error message should be displayed as shown in the screenshot below.
![http://i.imgur.com/2tYkT8T.jpg](http://i.imgur.com/2tYkT8T.jpg)