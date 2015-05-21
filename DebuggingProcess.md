#This page describes step-by-step process of debugging the business process created in process designer.


[Back to Table of Contents](TableOfContents.md)


## Debugging a process ##

The inspector in the Lombardi environment includes several tools that allows us to complete tasks.

A process instance is a run-time execution of process model. The inspector allows the user to view and manage instances.

For a selected instance of a process, the user can wish to execute the model step-by-step. The user would wish to step through and debug the process in order to validate data flow implementations. This provides users an advantage of seeing the variables used in each step and the value that they currently hold.

## Debugging in the inspector ##

Debug mode in Process Designer ensures an iterative approach to process development such that your process applications meet the goals and needs of everyone involved.

Here is an example of how debug mode can be used in process designer.

  * Step1:
Open the process that you want to debug. Click on the 'run' button(seen on the right end of the designer window).
![http://i.imgur.com/uAZ90Kk.jpg](http://i.imgur.com/uAZ90Kk.jpg)

  * Step2:
A process instance is created on running a process. And tasks relevant to that instance are seen on the right side of the window as shown in the screenshot
![http://i.imgur.com/eJYNt29.jpg](http://i.imgur.com/eJYNt29.jpg)

  * Step3:
Select the first displayed task and click on 'Debug' task icon. This action should open a debugging session in a browser window as shown below, after selecting a valid username to run the task
![http://i.imgur.com/uXjmCfp.jpg](http://i.imgur.com/uXjmCfp.jpg)

  * Step4:
"Step" button in the debugger session in your browser can be clicked to proceed. Filling in the fields and clicking the Next button causes the debugger to move to the next step.
![http://i.imgur.com/M6fpytl.jpg](http://i.imgur.com/M6fpytl.jpg)

![http://i.imgur.com/nhmXYXT.jpg](http://i.imgur.com/nhmXYXT.jpg)

![http://i.imgur.com/GY9l6W0.jpg](http://i.imgur.com/GY9l6W0.jpg)

As seen in the above example, the debugger session in the browser allows the user to view data that one enters into any displayed coaches as well as the values that cause the underlying logic in the services and BPD to proceed along the available paths.

## Execution State and Evaluator ##

They can be used to see what value is stored in that variable at any given point.
![http://i.imgur.com/eeEFJZD.jpg](http://i.imgur.com/eeEFJZD.jpg)

The Execution Evaluator enables you to inspect the variable values as they change through the flow of the BPD.
You can also manipulate variables in the Execution Evaluator using JavaScript expressions to validate your process implementation.

![http://i.imgur.com/gHeFo4B.jpg](http://i.imgur.com/gHeFo4B.jpg)

![http://i.imgur.com/ukf16Nx.jpg](http://i.imgur.com/ukf16Nx.jpg)


Thus, this insight can be extremely helpful when issues are identified.