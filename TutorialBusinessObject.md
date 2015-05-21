[Back to Table of Contents](TableOfContents.md)

#summary One-sentence summary of this page.

# Tutorial for Complex Business Object #

This tutorial explains how complex data can be created and used in the business process.

## Creating Business Data ##

Step 1: Click on '+' under 'Data' section and select 'Business Object' from the list.
![http://i.imgur.com/Zz0GTGS.jpg](http://i.imgur.com/Zz0GTGS.jpg)

Provide valid Business Object name 'StudentInformation' and click on 'Finish'.
![http://i.imgur.com/pxnVP5o.jpg](http://i.imgur.com/pxnVP5o.jpg)

Step 2: Click on 'Add' button in the 'StudentInformation' business object page. Add the related data to that business object under 'Parameter' as shown in the screenshot below:
![http://i.imgur.com/m9VMUQF.jpg](http://i.imgur.com/m9VMUQF.jpg)


At this stage, Complex Business Data is ready.

The following section explains how this created business data can be used in the business process


## Using the created Business Data in the Business Process ##

Step 3: Create a business process where in a student fills in his information and submits it to the professor for review.

(i) Let the business process have 2 participants say, Student and Professor
(ii) The student should be provided with a form to fill in his details. The information should then be passed on to his professor for approval.
(iii) The professor should be able to view the student submitted information and review the same.

Let us construct this business process using the above created complex data..

Step 1: Create a business process. Say 'Example of using Complex Data' as shown in the screenshot:
![http://i.imgur.com/GMmeGb4.jpg](http://i.imgur.com/GMmeGb4.jpg)

Step 2: Let us have two swimlanes. One for each participant(Student and professor).
Start constructing the business flow as shown in the screenshot below:
![http://i.imgur.com/ploqSZx.jpg](http://i.imgur.com/ploqSZx.jpg)

Variables on the process level:
![http://i.imgur.com/eYLHOzD.jpg](http://i.imgur.com/eYLHOzD.jpg)

Create appropriate user interfaces/human coach for each of the above shown activities.

**Fill Form human interface:**

![http://i.imgur.com/hSHwTcq.jpg](http://i.imgur.com/hSHwTcq.jpg)

Variables within the coach:

![http://i.imgur.com/NnP4wfj.jpg](http://i.imgur.com/NnP4wfj.jpg)

As seen here, the variable is a list and is of complex data type. It can be basically dragged and dropped onto the coach for use.

Coach view:

![http://i.imgur.com/6eVuDqc.jpg](http://i.imgur.com/6eVuDqc.jpg)

**Review human interface:**

![http://i.imgur.com/ndHAj9Q.jpg](http://i.imgur.com/ndHAj9Q.jpg)

Variables within the caoch:

![http://i.imgur.com/PjCi1zj.jpg](http://i.imgur.com/PjCi1zj.jpg)

As seen here, the variable is a list and is of complex data type. It can be basically dragged and dropped onto the coach for use.

Coach view:

![http://i.imgur.com/QvnF6cr.jpg](http://i.imgur.com/QvnF6cr.jpg)


## Running the business process ##

Step 1: Click on 'run' button.
you will now be taken to the inspector mode as shown here:
![http://i.imgur.com/rbZpEDp.jpg](http://i.imgur.com/rbZpEDp.jpg)

Step 2: Select the instance and run the same. You will provided with browser interface as seen here:

(1) Student filling the form:
![http://i.imgur.com/Dw1Fmmf.jpg](http://i.imgur.com/Dw1Fmmf.jpg)

As seen in the screen shot, the student needs to click on '+' symbol to edit the columns.

(2) Professor reviewing the form:
![http://i.imgur.com/LjNTwvX.jpg](http://i.imgur.com/LjNTwvX.jpg)

As seen here, the prof would see the student information. He can check the checkbox 'Reviewed' and submit the same.



## Note 1 ##
The parameters of business object can be accessed separated.
Say for Eg: You want to access only 'studentNumber' from 'StudentInformation' business object variable.
This can be achieved by using: tw.local.StudentInformation.studentNumber


## Note 2 ##
A variable can be a list of business object type.
Users may come across a list of items being displayed out of which 1 item needs to be selected.
In such a scenario, the selected item can be obtained by using: tw.local.<BusinessObject Variable>.listAllSelected


## Note 3 ##
A variable can be a list of business object type.
A parameter of such a list of business object can be accessed separated.
Say for Eg: You want to access only 'studentNumber' from 'StudentInformation' business object list variable.
This can be achieved by using: tw.local.StudentInformation[0](0.md).studentNumber