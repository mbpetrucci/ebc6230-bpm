# This describes how to integrate web services in BPM


[Back to Table of Contents](TableOfContents.md)

## Integrating web services ##

1. Create a new 'Integration Service' from 'Implementation' section. Click on '+' to see the options available. Click on 'Integration Service'. Provide a name for the new integration service(say, Calculator\_Addition)

![http://i.imgur.com/qZAfIoi.png](http://i.imgur.com/qZAfIoi.png)

2. The user is now taken to the Integration Service screen. From the pallet on the right hand side of the screen, drag and drop 'Web Service Integration' between the start and end points as shown below. Name the service and connect to the start and end points.

![http://i.imgur.com/eBz3M4f.png](http://i.imgur.com/eBz3M4f.png)

3. Select the service added in step2 and goto 'Implementation section'.
In the 'Discovery Section', select 'Provide Inline Configuration' for the option 'Discovery Scheme'.
Provide the WSDL URI as http://137.122.93.142/CalculatorWSApplication/CalculatorWS?wsdl under 'Inline WSDL Section' and click on 'Discover' button. This will open a 'Discover' dialog with the copied URL. Click on 'Discover' button seen in the dialog.
All the operations in the WS are now listed under 'Operations' section.

![http://i.imgur.com/KsnXiZe.png](http://i.imgur.com/KsnXiZe.png)


4. Select 'add(float,float)' operation. An End Point Address URL will be created.
![http://i.imgur.com/ia0sM0k.png](http://i.imgur.com/ia0sM0k.png)

5. Data Mapping:
Now click on 'Data Mapping' under 'Properties' section. You will see input and output mapping sections.
Create two input variables of type 'Decimal'(say input1 and input2). Also create a decimal type output variable (say, output).
Map these created variables in the 'Data Mapping' section as shown in the screenshot below:

![http://i.imgur.com/uaxyP4R.png](http://i.imgur.com/uaxyP4R.png)

## Testing the Webservice Created ##
To ensure that the above created service works fine, hard code the input values and run the service in the 'debug' mode.

1. Select the webservice created. Navigate to the Variables section.
Hard code the values of input variables (Say, input1=10.2 and input2=2.2). You can do so by selecting the variable and checking the 'Has Default' checkbox seen under 'Default Value' section. Provide the value for the variable as shown here:
Repeat the same steps for another input variable.

![http://i.imgur.com/0od83yw.png](http://i.imgur.com/0od83yw.png)

2. Navigate back to 'Diagram' window and run the service in the debug mode.
Click on 'Debug Service' option seen next to 'Run Service' button.
This will take you to the debug service in the browser as seen below:

![http://i.imgur.com/I6enYvH.png](http://i.imgur.com/I6enYvH.png)

As seen in the screenshot, the hard coded input variables are clearly seen. The output variable is empty. This will be populated when the service is run or when you step over the process.

3. Click on 'Step' button to step on the next call to this service.
You will now see that the service is executed and the output field is successfully populated. The output should contain the sum of two inputs provided.

![http://i.imgur.com/7HXeCNA.png](http://i.imgur.com/7HXeCNA.png)

This ensures that the service created is working fine.

### Note ###
  * We can use this service as a part of business process.
  * We can also use other operations of this webservice.