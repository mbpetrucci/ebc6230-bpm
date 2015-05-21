#Project: User Story and Process WalkThrough

[Back to Table of Contents](TableOfContents.md)

# Project: Library System #

## Prerequisite ##

Create a business object as shown in the below screenshot and use the same throughout the process:

![http://i.imgur.com/FKynorN.jpg](http://i.imgur.com/FKynorN.jpg)

## Overview of the Process ##
A student visits homepage of the university library and is given two options to select from: (A) Borrow item(s)  (B) Return item(s).

'Item' here can be a book or a DVD/CD.
And a student can borrow or return more than 1 item at a time.

Snapshot of the homepage:

![http://i.imgur.com/d07S293.jpg](http://i.imgur.com/d07S293.jpg)


## (A) Borrow Process ##
A student selects 'borrow a book/DVD' from the homepage and visits the borrow coach screen, where in he is again given two options to select from: (1)Academic (2)Reference

Snapshot of borrow category selection coach:

![http://i.imgur.com/NbauqeE.jpg](http://i.imgur.com/NbauqeE.jpg)


## (1) Academic Category ##
  * If a student selects 'Academic books/CDs', the process isn't expected to be long.
The system displays all the "Available Academic" books from the database.

  * The student browses them and selects one/more items that he would like to borrow.

  * All the selected item(s) for borrow is to be and confirmed next.

  * Once the items are confirmed, the status of these items is changed to 'Borrowed' and the due date on each borrowed item is calculated.

## Note: ##
To keep the demonstration of the project quick, due date is tuned to 2 minutes.
In other words, if an item is borrowed on 25-july-2014 at 11:10AM, the due date is field in the database will be updated to 25-july-2014 at 11:12AM.

  * The Library system is responsible for sending the reminder email 60 seconds before the due date.

Snapshot of the Borrow Academic Items coach:
![http://imgur.com/RYu3D4w.png](http://imgur.com/RYu3D4w.png)


Snapshot of Confirm Borrow Item Selection:
![http://imgur.com/YRYhe21.png](http://imgur.com/YRYhe21.png)


Snapshot of the confirmation email sent after borrowing the items:
![http://i.imgur.com/w5s2wDQ.png](http://i.imgur.com/w5s2wDQ.png)



## (2) Reference Category ##
  * If a student selects 'Reference books/CDs', the process is a bit longer since these reference items are special categories and would require an approval from the librarian.
The system displays all the "Available Reference" items from the database.

  * The student browses them and selects item(s) that he would like to borrow.

  * He then confirms the borrow of those selected item(s) and waits for the librarian to approve them.

  * Unlike 'borrow academic items', the items falling under 'Reference' section are to be approved by the librarian before they are borrowed.
The librarian checks and verifies those selected items and confirms the borrow of them.

  * Once confirmed, the status of these items is changed to 'Borrowed' in the database and the due date on each book/item is calculated.

## Note: ##
To keep the demonstration of the project quick, due date is tuned to 2 minutes.
In other words, if an item is borrowed on 25-july-2014 at 11:10AM, the due date is field in the database will be updated to 25-july-2014 at 11:12AM.

  * The Library system is responsible for sending the reminder email 60 seconds before the due date.

Snapshot of the Reference Category coach:
![http://imgur.com/yumrYoG.png](http://imgur.com/yumrYoG.png)

Snapshot of Confirm Borrow Item Selection:
![http://imgur.com/0iGhaqV.png](http://imgur.com/0iGhaqV.png)

Snapshot of the Approve Items coach, where in the librarian approves the selected items:
![http://imgur.com/k4UTFfd.png](http://imgur.com/k4UTFfd.png)


  * Once academic/reference item(s) are borrowed, a reminder email is sent to the borrower email address(which is obtained from DB table) after 60 seconds.



## (B) Blocking user account ##
  * After sending a reminder email, the system waits for another 60 seconds to reach the due datetime and checks if the due items are returned.

  * If the due items are still not returned, the library system will now request the university system to block the the user account. And an email has to be sent to that student to convey that his account is blocked.
At this point, the student is only allowed to return the item(s) that he has borrowed. He is restricted from borrowing item(s) until all the due item(s) are returned.

Snapshot of the email sent after blocking the user account:
![http://i.imgur.com/cElQWju.jpg](http://i.imgur.com/cElQWju.jpg)



## (C) Return Process ##
  * If the student comes to return item(s) page, the system firstly displays all the item(s) that he has borrowed.
The user then decides and selects which item(s) he would like to return.

  * In this process, the Library system is responsible for calculating the fine if there exists any, on the item(s) borrowed. The system then displays the calculate fine for each book and displays them with the item(s) selected by the user to be returned. The user is responsible for paying the fine(if any) at the time of return.

  * Once the system calculates the fine on the borrowed item(s) and the student has confirmed the return of item(s), the process is taken forward by the librarian. The librarian verifies and confirms the return of item(s) and the fine, if any.

Snapshot of Return Page:
![http://imgur.com/iiKECUg.png](http://imgur.com/iiKECUg.png)

Snapshot of Items with Fine Calculated by the System:
![http://imgur.com/0LnK25z.png](http://imgur.com/0LnK25z.png)

Snapshot of confirming the transaction by the Librarian:
![http://imgur.com/xUsEtWY.png](http://imgur.com/xUsEtWY.png)


## (D) Unblocking user account ##
  * Once the librarian confirms the return of item(s) from the borrower, a check is made to see if the item(s) are returned by a blocked user.

  * If the item(s) are returned by a blocked user, a check is made to verify if there are any more due item(s).
If there are no more due item(s), the university system will unblock the blocked account.
An unblocked email needs to be sent to the user. And the user will now be allowed to borrow item(s) of interest.

  * If the item(s) are returned by a blocked user and there is 1/more due item(s) remaining for return, then the user account will remain blocked.

  * If the item(s) are returned by an unblocked user, the process simply ends here.

Snapshot of an email after unblocking the user account:
![http://i.imgur.com/D8oV04n.jpg](http://i.imgur.com/D8oV04n.jpg)



## High-Level Business Flow ##
![http://i.imgur.com/zSiAw18.jpg](http://i.imgur.com/zSiAw18.jpg)