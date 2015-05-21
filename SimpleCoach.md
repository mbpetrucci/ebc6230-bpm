#Tutorial: How to create Human Service Coach

[Back to Table of Contents](TableOfContents.md)

## Creation of Human Service coach ##
The following tutorial explains how to create a Human Service with a simple Coach:

  * Login to Process Designer by providing a valid username and password.
In the Designer view, Click on '+' sign next to User Interface. Select 'Heritage Human Service' from the list displayed. A 'New Heritage Human Service' dialog opens. Now provide a valid name for the human service and click on 'Finish' button.

![http://i.imgur.com/a65Cp9U.jpg](http://i.imgur.com/a65Cp9U.jpg)

  * A new human service will be created. The designer will now open this human service in the project area. The diagram view contains just the start and end events by default, as shown in the screenshot:

![http://i.imgur.com/tgGtCSv.jpg](http://i.imgur.com/tgGtCSv.jpg)

  * The user can also view a number of pallet items displayed on the right side of the coach view. These pallet components can be dragged and dropped on the diagram editor to create the desired web-based interface.

[![http://imgur.com/RGSHLBd.png](http://imgur.com/RGSHLBd.png)]


## Steps to create a sample Human Service Coach ##
  * Eg: To create an admission form that needs to be filled by every student to get a seat in the preferred stream at University of Ottawa.

1. Login to Process Designer, create a Heritage Human Service coach from the 'User Interface' option. (Steps described above)
Drag and drop a 'Coach' component from the pallet. Select the coach added and navigate to the 'Properties' tab for that coach. Provide 'LoginForm' as the name of the coach. At this stage, we have added a coach successfully.

![http://i.imgur.com/ikBwyBB.jpg](http://i.imgur.com/ikBwyBB.jpg)

2. Navigate to 'Coaches' section. You can do this by clicking on 'Coaches' tab or by double clicking on the 'LoginForm' added human coach. By default, you will observe 'OK' button.

  * To begin designing the interface, it is always best practice to add sections before we add any other components to the coach. Every component should be bound to a variable except for the sections(horizontal/vertical) and custom HTML displayed under Advanced Section.

3. Start adding the components of choice to build the interface.
In our example, we will be adding student's First Name, Last Name, Date Of Birth, Gender, Subject Stream, and finally a Submit button.

![http://i.imgur.com/zxpPWBy.jpg](http://i.imgur.com/zxpPWBy.jpg)

  * First Name: This is a 'Text' component from the pallet. This field is a free text which accepts user's input.
  * Last Name: This is a 'Text' component from the pallet. This field is a free text which accepts user's input.
  * Subject Stream: This is a 'Text' component from the pallet. This field is a free text which accepts user's input.
  * Date of Birth: This is a date picker selected from the pallet. This lets the students select the date from the calendar displayed. You can make it a user-enterable 'Text' field too.
  * Gender: This is a checkbox selected from the pallet. The check box property is changed to serve as 2 radio buttons. One mapping to 'Male' and another mapping to 'Female'. This change is done under the 'Configuration' tab of the checkbox item(as seen in the screenshot).

![http://i.imgur.com/16Tl63H.jpg](http://i.imgur.com/16Tl63H.jpg)

  * Submit: This is a button component. It can be added from the pallet or the default 'OK' button can be used. In case you need two buttons (Say, 'Submit' and 'Cancel') then you should have two button components dragged and dropped to the coach view.

4. The next step is to connect the coach to start and end points.
Navigate to 'Diagram' tab. Draw a sequence flow line from Start to LoginForm coach and another flow line from LoginForm to End. The flowline from LoginForn to End will display the End State Binding as 'Submit'. This means on clicking the submit button, the form is submitted and thus ending the task. In case more than one button is used, then the user can change the end state binding under the property section of that flow line.

![http://i.imgur.com/yJIL0hH.jpg](http://i.imgur.com/yJIL0hH.jpg)

5. We will next view the created interface in the browser.
Click on 'Run' button seen at the extreme right corner of the designer.
This action will open the created coach in the browser as shown in the following screenshot.

![http://i.imgur.com/mdFMjmG.jpg](http://i.imgur.com/mdFMjmG.jpg)

We have now successfully created a human interface coach.

### Note ###
The coach created here is still non-functional. The next step is to associate variables to the coach components.
Please visit "Tutorials:Binding Variables to coach components" to learn about binding variables to the coach components.



### Another Sample Coach Screenshot ###
![http://imgur.com/BsyCLIY.png](http://imgur.com/BsyCLIY.png)