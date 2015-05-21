#An example of time elapsed UCA

[Back to Table of Contents](TableOfContents.md)

# Time Elapsed UCA #

  * It is an UCA that runs regularly at pre-defined times of the day.

### Example of creating Timed UCA ###
  * Let us consider a simple example where the customer fills in the order entry form and is displayed to him to confirm before submission.
  * As seen in the following screen shots, 2 activities are used:
> > (i) Order Entry Activity: allows the customer to provide his details.


> (ii) Results Activity: displays the customer-entered information to the customer before submitting.

The following screenshot shows the process constructed:
![http://i.imgur.com/5HLkdmw.jpg](http://i.imgur.com/5HLkdmw.jpg)

The following screenshot describes creation of business object:
![http://i.imgur.com/o1yDcDy.jpg](http://i.imgur.com/o1yDcDy.jpg)

The following screenshot describes construction of variables:
![http://i.imgur.com/23uzpsU.jpg](http://i.imgur.com/23uzpsU.jpg)

The following shows the construction of human coaches for each of the above mentioned activity.

(i) Order Entry:
![http://i.imgur.com/BapmfxM.jpg](http://i.imgur.com/BapmfxM.jpg)

(ii) Results:
![http://i.imgur.com/zg77JV7.jpg](http://i.imgur.com/zg77JV7.jpg)

Output:
![http://i.imgur.com/AcLVnxm.jpg](http://i.imgur.com/AcLVnxm.jpg)

![http://i.imgur.com/Z0qkdNS.jpg](http://i.imgur.com/Z0qkdNS.jpg)


### Running the UCA ###
  * Now, to start this process at 10:00AM and 2:00PM on Wednesdays and Fridays, we need to use Timed-UCA. This is illustrated in the following section:

  * Step 1:
Create a General System Service from 'Implementation' tab. Also create an output variable(say, message)
![http://i.imgur.com/55x8nNk.jpg](http://i.imgur.com/55x8nNk.jpg)

![http://i.imgur.com/fCxzK4y.jpg](http://i.imgur.com/fCxzK4y.jpg)

  * Step 2:
Create a new Undercoverage Agent from 'Implementation' tab.Attach the above created General System Service to it.
![http://i.imgur.com/ifpTs8P.jpg](http://i.imgur.com/ifpTs8P.jpg)

  * Step 3:
For this created UCA, select the time schedule as shown in the screenshot.
![http://i.imgur.com/MTceQJ8.jpg](http://i.imgur.com/MTceQJ8.jpg)

  * Step 4:
Change the Start Event type in the process from 'None' to 'Message Start Event' as seen in the screen shot. And attach the above created UCA to this message trigger.
Also, create a variable in the main process that accepts the variable:message passed in through the UCA.

![http://i.imgur.com/anzPBH6.jpg](http://i.imgur.com/anzPBH6.jpg)
![http://i.imgur.com/Nx2A28O.jpg](http://i.imgur.com/Nx2A28O.jpg)

Thus, the process is now started by the UCA event on every wednesdays and fridays at 10:00AM and 2:00PM.

Note:
A process can have only 1 start event of type 'None'. But, there can be many message start events that use UCAs.

For example:
In the screenshot shown in step 4, there can be another UCA that directly passes the data to the Results service.
![http://i.imgur.com/ndiwiji.jpg](http://i.imgur.com/ndiwiji.jpg)

