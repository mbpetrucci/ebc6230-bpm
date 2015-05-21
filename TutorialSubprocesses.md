#Tutorial: Sub-Processes .

[Back to Table of Contents](TableOfContents.md)

## Sub process Example ##

Here is a sample example on how sub process can be created and how it can be used.

The process is constructed to address the following business logic:
An employee of a company requests for a software that needs to be used in the project. He fills in the request form providing his employee number, project name, the software details.
This request needs to be approved by the Decision Committee. The decision committee has the Team Lead and the Manager who needs to approve the request. Here we treat the Decision Committee as a subprocess which consists of authority to approve or reject the request.

The following steps illustrate the business process constructed to address the above stated requirements:

Step 1: Construct a participant or employee lane. This consists of an activity-Request
and another one for the Decision Committee.

![http://imgur.com/JhRLt1e.png](http://imgur.com/JhRLt1e.png)

The variables and the data mapping at this level are:

![http://imgur.com/EQW6fOv.png](http://imgur.com/EQW6fOv.png)
![http://imgur.com/vJBZjpO.png](http://imgur.com/vJBZjpO.png)

Step 2: Designing 'Request' activity: Create a human service called: 'request Form' as shown below. Also have the coach designed as seen in the screenshot using the variables displayed below:
![http://i.imgur.com/atsbT2P.jpg](http://i.imgur.com/atsbT2P.jpg)
![http://i.imgur.com/icqNbS9.jpg](http://i.imgur.com/icqNbS9.jpg)

Step 3: Under the high level view of the process, for the Decision Committee activity, go to implementation and change the task to a sub process.

![http://imgur.com/m9KWbav.png](http://imgur.com/m9KWbav.png)

Step4: Designing Sub-Process: Create two lanes one for Team Lead and the other for Manager. Have two activities respectively for each in this process: View & Review Request and Approve or Reject Request.

![http://imgur.com/XbfChVD.png](http://imgur.com/XbfChVD.png)

The variables at this level are:

![http://imgur.com/myrevph.png](http://imgur.com/myrevph.png)

Also have the coach designed as seen in the screenshot using the variables displayed below:

![http://imgur.com/RZ2kRDa.png](http://imgur.com/RZ2kRDa.png)
![http://imgur.com/65xIiOL.png](http://imgur.com/65xIiOL.png)

At this level, the data mapping would be:

![http://imgur.com/vgOhAgI.png](http://imgur.com/vgOhAgI.png)

Step 5: For Activity: Approve or Reject Request.
Design two of the coaches suitably with the variables needed.

![http://i.imgur.com/Tkz6ODs.jpg](http://i.imgur.com/Tkz6ODs.jpg)

The data mapping at this level would be:

![http://imgur.com/e4wcISk.png](http://imgur.com/e4wcISk.png)

## Output Steps ##

Task1: Request(to be performed by the employee)

![http://i.imgur.com/ND4HXU1.jpg](http://i.imgur.com/ND4HXU1.jpg)

Task2: View and review Request(first to be performed by the lead)

![http://i.imgur.com/DuvkVAa.jpg](http://i.imgur.com/DuvkVAa.jpg)
Task3: Approve/Disapprove request(to be performed by the manager)

![http://i.imgur.com/s3959sx.jpg](http://i.imgur.com/s3959sx.jpg)
![http://i.imgur.com/nTupAVr.jpg](http://i.imgur.com/nTupAVr.jpg)

Note: This example explains how the subprocess is used. Here we are hiding the low level details of the Decision Committee by making it as a subprocess.