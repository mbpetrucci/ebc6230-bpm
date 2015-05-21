#Tutorial: Shows how to perform binding of variables

[Back to Table of Contents](TableOfContents.md)


In the previous tutorial, we have learnt how to create a human interface coach.

As mentioned under the 'Notes' section in the previous tutorial, the coach components are to be bound to variables. This way the values entered in the coach components are stored in the bound variables and can be transferred across the entire process among various activities.

## Steps to bind variables to a human coach ##

Step 1:
Create a human coach as described in the [Tutorial: A Simple Human Service Coach](SimpleCoach.md) section.
At this point, we will consider the coach that we created and try to map the variables in that coach.
  * Screenshot of the already prepared coach:
![http://i.imgur.com/wy0LMkw.jpg](http://i.imgur.com/wy0LMkw.jpg)

As seen here, the coach has only got the components. The components are not bound to any variables. Also, no variables are declared under 'Variables' tab.

Step 2:
Let us start creating input variables for the coach components.
Navigate to 'Variables' tab in the coach view. Click on 'Add Input' to add the input variables.
A new untitled input variable will be added. Provide valid name for the added variable in the 'Name' field. Also, select the data type of the variable under 'Variable Type' option by clicking on 'select' button.

On clicking the 'select' button, a list of variable types are displayed. The user can make a better choice by typing the data type name. The list is then screened to display only those types that match the typed char seq(Like, wild card matching).

Every field added in the coach should correspond to a variable of suitable type.
  * First Name corresponds to 'firstName' of type 'string'.
  * Last Name corresponds to 'lastName' of type 'string'.
  * Date of Birth corresponds to 'DOB' of type 'Date'
  * Gender corresponds to 'gender' of type 'boolean'.
  * Subject Stream corresponds to 'subjectStream' of type 'string'.

### Note ###
Variables follow lower-camel case. The acronyms are written in upper case.

At this stage, we have completed creation of input variables.
![http://i.imgur.com/VPtpSMe.jpg](http://i.imgur.com/VPtpSMe.jpg)

Step 3:
Once the variables are added, the next step is to bind them to the suitable coach components.
Navigate to 'Coaches' tab. Select 'First Name' input field in the coach. Under the 'Properties' section, navigate to 'General' tab. Under the 'behavior' column, you will find 'Binding' field being empty.
Click on 'Select' against Binding column and select 'firstName' from the list.

You will see that the variable is successfully bound to the coach field now.
Repeat this for every other component in the coach.
![http://i.imgur.com/Xg5QQcd.jpg](http://i.imgur.com/Xg5QQcd.jpg)


Step 4:
Running the coach in 'Debug' mode.
To ensure that the values entered/selected in the coach fields are properly mapped to right variables, it is always necessary to run the service in 'Debug' mode.

On the right corner of the coach view, you will see 'debug' button next to 'run' button. Click on 'debug' button. 'IBM BPM Service Debug' screen will be opened in the browser as seen in the following screenshot.
'Step' button will step you over the next step sequentially. While the run button will take you to the interface directly without displaying the code-level details.
![http://i.imgur.com/mQKsY4A.jpg](http://i.imgur.com/mQKsY4A.jpg)

To debug, let us click on 'step' button. The user interface is the very next step and hence the user will be shown the interface. Provide valid inputs to the coach and click on submit button.
As observed in the following screenshot, the debug mode screen now shows the variable values successfully.

![http://i.imgur.com/QIhWpmZ.jpg](http://i.imgur.com/QIhWpmZ.jpg)

This ensures that the variable mapping is rightly performed.