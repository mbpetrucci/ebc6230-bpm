#This page explains how to control single and multiple selection of item(s) in a coach.

[Back to Table of Contents](TableOfContents.md)

# Introduction #

Multiple Selection allows the user to select more than 1 item in the selection item list.

Following examples show how to select multiple items from the displayed list and how single selection can be controlled.

To start with, lets consider a list (say list of students). The list of items can come from database tables (or) fixed values are initialized in the business process.

### Example: Initialized list ###

  * Step 1:
Create a local variable of list type and 'STRING' datatype.

  * Step 2:
Create a human coach. Add a Server Script before the coach as shown in the below screenshot:

![http://i.imgur.com/YQz1i4Y.jpg](http://i.imgur.com/YQz1i4Y.jpg)

In the implementation section, initialize the list variable as seen in the screenshot.

  * Step 3:
In the coach, create a vertical section. Drag and drop the list variable onto the coach.
Under 'Configuration' tab of the list variable, 'List Type' will show two items: Single Selection and Multiple Selection in the dropdown.
Select 'Multiple Selection' as shown in the screenshot.

![http://i.imgur.com/RxTb7Bm.jpg](http://i.imgur.com/RxTb7Bm.jpg)

  * Step 4:
Run the human service created.

![http://i.imgur.com/nCMbqDm.jpg](http://i.imgur.com/nCMbqDm.jpg)

As seen in the above screenshot, the user can select more than one list item.

Change the List Type from 'Multiple Selection' to 'Single Selection' to view the difference.

![http://i.imgur.com/8LQpqb3.jpg](http://i.imgur.com/8LQpqb3.jpg)

As seen in the screenshot, 'Multiple Selection' shows checkbox against list items. But, single selection shows items as dropdowns allowing the user to make one and only selection at a time.




