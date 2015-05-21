# Correlation ID #

Correlation Id is a parameter which is used to determine which instance needs to react to a message from a UCA.

Example: We will tweak the 'Example Timed UCA'process considered under 'Timed UCA' section. To tweak this process, first create an event-driven UCAcalled: 'Update Order' UCA. This UCA will be fired only for those instances that match the correlation ID.
We will consider orderId as the correlation ID in this example, as it uniquely identifies the instances.

Step 1:
Create a General System Service called: 'Update Order UCA Impl' from 'Implementation' tab.
![http://i.imgur.com/Cug2DjZ.jpg](http://i.imgur.com/Cug2DjZ.jpg)

Declare 2 input and output variables. The idea is to change the name of the customer for a chosen orderId(which is set as correlation Id)
![http://i.imgur.com/XUuo5rl.jpg](http://i.imgur.com/XUuo5rl.jpg)

Step 2:
Create an UCA called 'Update Order UCA' as shown in the screenshot. Select Schedule Type=On Event and attach the general system service created in step 1.

![http://i.imgur.com/SVFOrbW.jpg](http://i.imgur.com/SVFOrbW.jpg)

![http://i.imgur.com/cwANat8.jpg](http://i.imgur.com/cwANat8.jpg)

Step 3:
Create another General System Service say, 'Update Order Service' as shown in the screenshot. Drag and drop the created UCA to this process. And map the variables suitably.

![http://i.imgur.com/8ApFUEo.jpg](http://i.imgur.com/8ApFUEo.jpg)

Initialize the variables in the Init script as shown here:
![http://i.imgur.com/b7jPk5B.jpg](http://i.imgur.com/b7jPk5B.jpg)

Here, the orderid is set to 4444 and name is set to kavya.This means, whenever an instance with orderid=4444 is created, the name is changed to 'kavya' for that instance order.

Step 4:
Alter the 'Example Timed UCA' process that was used in 'Timed UCA' section. This process is known to contain two activities: Order entry and Results. Order Entry allows the customer to enter details while the Result displays the customer-provided field values for confirmation.

Edit this process to invoke the UCA created Step 2.
Add a 'Message Intermediate Event' on the 'Results' activity as shown in the figure. Also attach the UCA created in Step 2, to this message event.

![http://i.imgur.com/KgyorRb.jpg](http://i.imgur.com/KgyorRb.jpg)

Map the variables in the 'Data Mapping' section under 'Properties'. This mapping specifies that based on the 'orderId' the 'name' is suitably updated.

![http://i.imgur.com/gPyCz2J.jpg](http://i.imgur.com/gPyCz2J.jpg)

To verify that the UCA works for the set correlation ID, create two instances: (Manually run 'Start new order UCA' to create instances)
(1) Let the first instance have the orderid=4444, name=abc and address=1234
![http://i.imgur.com/VAyzDrF.jpg](http://i.imgur.com/VAyzDrF.jpg)

(2) Let the second instance have the orderid=9999, name=pqr and address=0987

![http://i.imgur.com/zYYf2bd.jpg](http://i.imgur.com/zYYf2bd.jpg)

After Order Entry step and before Results step in each instance, we will now run the 'Update Order Service' general system service created(in step 3) by using the created UCA.

![http://i.imgur.com/rL0Uppo.jpg](http://i.imgur.com/rL0Uppo.jpg)

![http://i.imgur.com/vFwaoPx.jpg](http://i.imgur.com/vFwaoPx.jpg)

Once the service is successfully run, check the instances in the inspector screen.
It is observed that the instance whose orderid=4444 has now received a new results step:

![http://i.imgur.com/rlwuZht.jpg](http://i.imgur.com/rlwuZht.jpg)

While the instance with orderid=9999 has the old results step:

![http://i.imgur.com/BKQVy2T.jpg](http://i.imgur.com/BKQVy2T.jpg)

It is observed that the instance with orderid=4444 shows the change in name from abc to kavya. While that instance with orderid=9999 has remained unchanged.

![http://i.imgur.com/mXNWf4U.jpg](http://i.imgur.com/mXNWf4U.jpg)

![http://i.imgur.com/JoNAaL5.jpg](http://i.imgur.com/JoNAaL5.jpg)






