#This page explains how decision gateway can be used in constructing business processes.


[Back to Table of Contents](TableOfContents.md)


To start with, let us construct a simple business process flow.

  * Step 1:
Login to Process Designer. Click on '+' sign against 'Processes' tab and select 'Business Process Definition'. This will open a 'New Business Process Definition' window. Provide valid process name(say, Sample process) and click on 'Finish' button.

You are now on the process page. The process view by default shows start and end events.

![http://i.imgur.com/VtQnN02.jpg](http://i.imgur.com/VtQnN02.jpg)

  * Step 2:
You will see two swim lanes by default: Team and System lanes.
Delete System lane. Click on System lane and hit delete button on the key board. This will delete the system lane for you.
Add another participant lane by dragging and dropping 'Lane' component from the BPD pallet(shown on the right hand side of the window).
Name the 2 swim lanes. lane1:Student and lane2:Professor as shown in the following screenshot.
You can move the lanes up and down and arrange them in what ever order you wish to see them in the process.

![http://i.imgur.com/rey9S3W.jpg](http://i.imgur.com/rey9S3W.jpg)

  * Step 3:
Drag an activity from the BPD pallet and place it between start and end points. Lets call this 'Request Course Admission'. This is the student task. Student is responsible for filling a course admission form form. Once the form is filled it needs to be submitted to the professor.

Similarly drag and drop another activity and place it in the Professor lane. Lets call it 'Review Course Admission'. This will have the form details filled and submitted by the student. The professor reviews the student application.

Connect the activities using flow lines.

![http://i.imgur.com/SEVLqsV.jpg](http://i.imgur.com/SEVLqsV.jpg)

  * Step 4:
Create a human service/coach interface for the student and the similar one for the professor. Follow [Tutorial:A simple Human Service Coach](SimpleCoach.md) tutorial to create an application form.
A sample student form is shown in the following screen shot:

![http://i.imgur.com/VGCWue6.jpg](http://i.imgur.com/VGCWue6.jpg)

Also create a similar form for the Professor. The professor should be able to view all the student-filled form details. In addition, lets have a check box that indicates if the professor has approved the admission request or rejected the request.
A sample professor form is shown in the following screen shot:

![http://i.imgur.com/WKi3rfT.jpg](http://i.imgur.com/WKi3rfT.jpg)

  * Step 5:
Once the coaches for student and professor are prepared, they need to be attached to the activities created in Step 3.
Select student's 'Request Course Admission' activity. Navigate to 'Implementation' section. Under user task, you will observe that 'Default Human Service' coach is attached. Replace this human coach with 'Student form' human coach(created in step 3. Click on 'Select' button and select the student form from the list of heritage human coaches shown.

![http://i.imgur.com/Cs7f61n.jpg](http://i.imgur.com/Cs7f61n.jpg)

Similarly attach Professor Approval form for the 'Review Course Admission' activity.


### This step targets the use of decision gate way ###
  * Step 6:
To continue with the process, once the professor reviews the student application, he will decide if the application has to be approved or rejected. This decision needs to be handled in the process.

So, drag and drop decision gateway after the 'Review Course Admission' activity.

And add suitable display coaches after the professor has approved/rejected the request.

In our example we created two more activities. One for Approve and the other for Reject.
We will create 2 human service coaches (approval and rejection) and attach them to respective activities.

Approve human service is shown here:
![http://i.imgur.com/6kODc98.jpg](http://i.imgur.com/6kODc98.jpg)

Reject human service is shown here:
![http://i.imgur.com/3hE2f9N.jpg](http://i.imgur.com/3hE2f9N.jpg)


  * Step 7:
The next step is to write a condition to control the decision of the flow.
Click on decision gateway added. Navigate to 'Implementation' section.
You will see two different flows here. One flow going to 'Approve Message' and the other to 'Reject Message'.
The flow is controlled by the 'Approved' checkbox in the professor's 'Review Admission Request' form.

Provide a condition as shown in the screenshot:
![http://i.imgur.com/6VLiWvx.jpg](http://i.imgur.com/6VLiWvx.jpg)


  * Step 8:
This step targets data mapping at the activity level.
In a business flow, the variable values flow from one level/activity to another.
The flow can be controlled by mapping the output and input variables between the activities in the flow.

Select 'Request Course Admission' activity and navigate to 'Data Mapping Section'. You will see a set of input and output variables. And none of these are initially mapped.

A simple way to map these variables are to click on the 'Auto-Map' button seen in the screenshot. This will create private process variables and map them suitably.
The private variables are created just once. And the same set can be mapped across other activities.

![http://i.imgur.com/lOLufIV.jpg](http://i.imgur.com/lOLufIV.jpg)

Repeat this step for every activity in the process flow constructed.

  * Step 9:
Run the process end to end. Verify both the approval and rejection options and ensure the flow works fine based on the action performed by the professor(approve/Reject).

Approval flow screenshots:
![http://i.imgur.com/tUnA15J.jpg](http://i.imgur.com/tUnA15J.jpg)

Rejection flow screenshots:
![http://i.imgur.com/QEoJ5vr.jpg](http://i.imgur.com/QEoJ5vr.jpg)