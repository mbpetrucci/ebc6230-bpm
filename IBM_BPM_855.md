# Introduction to basic Business Process Modeling concepts using IBM BPM.

[Back to Table of Contents](TableOfContents.md)

## Introduction ##

IBM BPM v8.5.5 is a comprehensive BPM offering that enables companies to continually improve their end-to-end business processes. With BPM, teams can build, manage, and optimize process applications that orchestrate human collaboration and system interactions.

IBM BPM tool is a client-server architecture. You can use the client to access the shared model. This architecture allows multiple clients to access the BPM shared model simultaneously.

## Download IBM Process Designer ##

To download the "IBM Process Designer.zip":

**Step1:** Connect through UOttawa VPN. Follow this tutorial to download and connect to uottawa VPN at:
[uOttawa VPN Setup](uOttawa_VPN_SetUp.md)

  * Then go to the Process Center page:
http://bpm2.site.uottawa.ca:9081/ProcessCenter/login.jsp


**Step2:** Log In. The students are required to provide the username and password given to them.

**Step3:**
You can download the process designer either by-

  * Clicking on the link "Download Process Designer", seen on the top right hand side of the screen.

(or)

  * Clicking on "Download" seen on"Getting Started with IBM BPM Process Center 8.5.5.0" page.


![http://i.imgur.com/KxkzbYF.png](http://i.imgur.com/KxkzbYF.png)

The "IBM Process Designer.zip" zip will start downloading.
This might take a few minutes.

## IBM BPM Process Designer ##

The IBM BPM Process Designer(PD) is the development time tooling used to
design, model and build processes. It is implemented under the covers using the Open Source technology called Eclipse.

IBPM PD can be downloaded from the IBPM Process Center and installed on a user's Windows based workstation.

At a high level IBPM PD allows us to describe business processes using the BPMN notation. The processes are "drawn" visually on the screen canvas and the technical skills needed to achieve this task are as low as can possibly be made.


## How to install BPM Process Designer? ##

Following steps illustrate the installation of IBM BPM Process Designer.

**Step1:** Unzip 'IBM Process Designer.zip" which is downloaded from the process center.

**Step2:** Open the unzipped folder,  and run the batch file "installProcessDesigner\_admin.bat" as an administrator (Right click on the batch file and select the option 'Run as Administrator').

Step2 may take a while - may be 10-15 minutes. So, wait patiently.


**Step3:** IBM Process Designer will be successfully installed. After installing IBPM, the IBPM Process Designer can be launched from the Windows start menu.
Navigate to Start Menu, and search for 'IBM Process Designer 8.5' and launch the same.


![http://i.imgur.com/LFnggBi.png](http://i.imgur.com/LFnggBi.png)


**Step4:** Provide valid username and password.(Same username and password that you used to download the designer from the process center.)
Once launched, the IBPM PD will ask for authentication information with a userid/password pair. Click on 'Yes' to proceed to the Process Designer Welcome Page.


![http://i.imgur.com/sW6nUu6.png](http://i.imgur.com/sW6nUu6.png)



Note: With successful login, you will observe that the currently logged in user is shown in the title of the window.

Note: In case you cannot download/login to Process Designer, kindly send an email to 'kmall093@uottawa.ca'.


## Process Designer Interface ##
In the IBPM PD interface, one will see the following major "views" only one of which is shown at a time:

**View seen in the Process Designer page**
• Process Apps – Selection of available/existing Process Apps

• Toolkits – Selection of available/existing Toolkits

• Servers – List of the Process Server instances

• Admin – Administration tasks

**Views seen when a Process App is selected and opened in designer**
• Designer – Design/construction of a solution

• Inspector – Debugging/monitoring a solution (usually in test)

• Optimizer – Examining performance characteristics
