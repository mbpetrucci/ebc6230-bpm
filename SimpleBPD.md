#Simple Business Process Definition.

[Back to Table of Contents](TableOfContents.md)

## A Simple Business Process Definition ##
> We are designing in the first tutorial a simple business process where an employee is sending a Request Resource Form to his manager for his approval.

  * From the Designer menu, select Processes -> Business Process Definition.
  * Name the new Business Process Definition, such as "Store Business Process".
  * The diagram of the Store Business Process shows two lanes with a start and end events. Drag and drop a lane from the palette on the top of the "Team" lane.
  * Name the top lane as "Clerk" and the other lane as "Manager". (Leave the system lane without changes).
  * Drag and drop three activities: an activity in the "Employee" lane and name it "Item Request"; a second activity in the "Manager" lane and name it "Item review"; a third activity in the "System" lane and name it "Print Request";
  * Drag and drop a Gateway.
  * Select the Sequence flow in the palette and connect the notations (Start event, "Item Request" activity, "Item review" activity and Gateway. From the Gateway connect the first path to the End event, while connect the second path to "Print Request" activity and then to the End Event).

![http://i.imgur.com/lLYcGnF.png](http://i.imgur.com/lLYcGnF.png)

  * Select the Variables tab and define seven Private variables:
    1. "clerkName" of type String
    1. "itemNumber" of type String
    1. "itemDescription" of type String
    1. "unitPrice" of type Decimal
    1. "quantity" of type Integer
    1. "totalPrice" of type Decimal
    1. "Approved" of type Boolean

![http://i.imgur.com/mWVFaJS.png](http://i.imgur.com/mWVFaJS.png)

  * Select the Diagram tab and from the main canvas, right click the "Item Request" activity and select Activity Wizard.
  * An Activity Wizard window open, as in figure below, make the Activity Type Selection as "User Task". Select Next.
![http://i.imgur.com/neJk8o1.png](http://i.imgur.com/neJk8o1.png)

  * From the Activity Wizard - Parameters window, as in the figure below, select the output of the "Approved" variable into "false". This is because the "Manager" is the one who approve or disapprove the request. Click Finish.
  * Do the same Activity Wizard procedures with the "Item review". The only difference is that the "Approved" variable is "True" for both the input and the output.
![http://i.imgur.com/9eYa5jY.png](http://i.imgur.com/9eYa5jY.png)

  * From the main canvas of BPD, double click on the "Item Request" activity and select the Coaches tab.
  * The Coaches tab presents the Item Request Form which contains the modeling controls of the variables.
  * You can change the captions of the controls and re-arrange them in different way. The figure below presents the Form of the "Item Request".
![http://i.imgur.com/njZzr2J.png](http://i.imgur.com/njZzr2J.png)

  * You are done. So you can run the process by clicking on the "Run Process" icon at the right top.
  * The figures below show the sending the "Item Request" form and submitting the approval of "Item Review" form and then Print the approved request.

![http://i.imgur.com/dvdAMfX.png](http://i.imgur.com/dvdAMfX.png)

![http://i.imgur.com/RxFTpal.png](http://i.imgur.com/RxFTpal.png)