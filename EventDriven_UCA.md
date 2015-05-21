# Introduction #

Event Driven UCA is a type of UCA that fire upon the occurrence of an event.
Example: When a coach is submitted, the UCA is invoked.


# Details #

The following example shows how event driven UCAs are implemented in the process.

Let us consider the process described under 'Timed UCA' section. The process consists of 2 activities: Order entry and Results. Order Entry allows the customer to enter their details. The Result activity shows the customer-entered details for confirmation.

In addition to this process, let us construct another process called: 'Order Printing'. This process will display the customer-entered details and thus print the information.

This 'Order Printing' process action(:Allow printing the details) takes place on occurrence of an event:(when the customer confirms his entered details). This is achieved using event-driven UCA.

Step 1:
Creating 'Print Order UCA Impl' general system service
Select 'General Service System' under 'Implementation' section and provide a valid name for this service (say, Print Order UCA Impl).
Under variables tab, create input and output variables as shown in the screen shot.
![http://i.imgur.com/VMrq6BX.jpg](http://i.imgur.com/VMrq6BX.jpg)

![http://i.imgur.com/Zfq6Fnt.jpg](http://i.imgur.com/Zfq6Fnt.jpg)

Step 2:
Create 'Print Order' UCA from the 'Implementation' tab as shown in the following screenshots. Make the schedule type: On Event. Also attach the above created service to this UCA.
![http://i.imgur.com/JFz1IGF.jpg](http://i.imgur.com/JFz1IGF.jpg)

Step 3:
Create a new process ' Example Event Driven UCA'. Attach the above created UCA to this process by changing the 'None start event' to 'Message start event'.
![http://i.imgur.com/aJWkYnD.jpg](http://i.imgur.com/aJWkYnD.jpg)

Add the variables needed and map them under 'data mapping' section.
![http://i.imgur.com/NLS8QXp.jpg](http://i.imgur.com/NLS8QXp.jpg)

Also make necessary changes to the coach to display the entered data for printing.
![http://i.imgur.com/0rLBzzU.jpg](http://i.imgur.com/0rLBzzU.jpg)


Now, the 'Order Printing' process is invoked when the first process 'Order creation' is completed successfully.

Result:
To observe this UCA behavior, manually start the first process 'Order Creation' by clicking on 'Run Now' under the attached UCA: 'Start New Order UCA'(which is created under Timed UCA section)
![http://i.imgur.com/3PGm6Oq.jpg](http://i.imgur.com/3PGm6Oq.jpg)

This will create an instance of the first process:Order Creation

![http://i.imgur.com/rf91pnk.jpg](http://i.imgur.com/rf91pnk.jpg)

![http://i.imgur.com/tPtuvQ6.jpg](http://i.imgur.com/tPtuvQ6.jpg)


Completion of this process will automatically invoke 'Order Print' instance as seen in the screenshot:
![http://i.imgur.com/C15g6aA.jpg](http://i.imgur.com/C15g6aA.jpg)




