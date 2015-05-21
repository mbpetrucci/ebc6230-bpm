#Linked Process Tutorial

[Back to Table of Contents](TableOfContents.md)

# Sample Linked Process #

Here is a sample example of how linked process can be used in BPM Process Designer.

The process is constructed to address the following business logic:
An employee of a company requests for a software that needs to be used in the project. He fills in the request form providing his employee number, project name, the software details.
This request needs to be approved by both the team lead and the manager.
So, both manager and the lead perform same set of activities and hence these activities are combined into a single linked process.

The following steps illustrate the business process constructed to address the above stated requirements:

Step1: Construct three separate swim lanes for each of the participants: Employee, team lead and manager.
Add a 'Request' activity in the Employee lane, a 'Approve or Reject' activity in the team lead and Manager lanes as shown in the diagram.
![http://i.imgur.com/xwHqHAg.jpg](http://i.imgur.com/xwHqHAg.jpg)

Step2: Designing 'Request' activity:
Create a human service called: 'request Form' as shown below. Also have the coach designed as seen in the screenshot using the variables displayed below:
![http://i.imgur.com/atsbT2P.jpg](http://i.imgur.com/atsbT2P.jpg)
![http://i.imgur.com/icqNbS9.jpg](http://i.imgur.com/icqNbS9.jpg)

Step3: Designing Linked Process:
Create another process called: 'Approve Requested Software' as seen in the screenshot. Have two activities in this process: View & Review Request and Approve or Disapprove Request.
![http://i.imgur.com/j0th67X.jpg](http://i.imgur.com/j0th67X.jpg)

Design each of the coaches suitably.
![http://i.imgur.com/msCaSOm.jpg](http://i.imgur.com/msCaSOm.jpg)
![http://i.imgur.com/Tkz6ODs.jpg](http://i.imgur.com/Tkz6ODs.jpg)

Step4: For the 'Approve or Reject' activity in the main process, change the type to 'Linked Process' under Implementation section and attach the above created process. This needs to be performed for both the swimlane activities(for both lead and manager activities)
![http://i.imgur.com/9mVGb2W.jpg](http://i.imgur.com/9mVGb2W.jpg)

Step5: Perform variable mappings suitably and run the entire process.

Output:
Task1: Request(to be performed by the employee)
![http://i.imgur.com/ND4HXU1.jpg](http://i.imgur.com/ND4HXU1.jpg)

Task2: View and review Request(first to be performed by the lead)
![http://i.imgur.com/DuvkVAa.jpg](http://i.imgur.com/DuvkVAa.jpg)

Task3: Approve/Disapprove request(to be performed by the lead)
![http://i.imgur.com/s3959sx.jpg](http://i.imgur.com/s3959sx.jpg)
As seen, the lead has approved the request and hence a successful message is displayed to him.
![http://i.imgur.com/nTupAVr.jpg](http://i.imgur.com/nTupAVr.jpg)

same set of tasks are performed by the manager.
Both the manager and the leads have the option to approve/disapprove the request.
If the manager or lead rejects the request, the above seen success message is not displayed to them.