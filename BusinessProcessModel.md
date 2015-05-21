# This page speaks about Business Process Definition (BPD)in IBM BPM

[Back to Table of Contents](TableOfContents.md)

# Business Process Model #
  * BPD describes the model of the business process workflow and captures the initial design of the business solution.
  * Business Process Definition (BPD) is the core of  BPM solution.
  * It also allows the process to be easily modified.

  * At a high level, a BPD is a diagram that represents the overall view and flow of the process.
  * It is commonly constructed by the Business Process Analyst in conjunction with discussions and interviews with other members of staff.

## BPM Modeling Notation ##
  * The diagram style of a Business Process Definition conforms to the industry standard Business Process Model and Notation (BPMN) format.
  * When a new BPD is defined, a main window area is created called Canvas.
  * The Canvas initially has two lanes: the System lane and the Participant Lane; and two events: Start Event and End Event.

#### A sample BPM Process showing BPDs ####

![http://i.imgur.com/zs4FxBI.jpg](http://i.imgur.com/zs4FxBI.jpg)


  * **Sequence Flow**
It is the order in which BPM processes and services are executed.Sequence flow is constructed using sequence lines.


  * **Activity**
Activities are objects representing a tasks or nested processes that can be executed by the user or by the system. Activities can contain java script code.


  * **Swim Lane**
Lanes are containers used to control user access to different parts of the project. They can be assigned to users, participant groups or the system.
A lane can be designated as "system lane", so that the system doesn't wait for the user interaction while performing tasks in that lane.
Lanes are always horizontal in the process diagram.
An activity cannot belong to more than one lane.
A swimlane can be of Participant type or System type.
There can be more than one swim lane. The screenshot shows three swim lanes: Clerk(Participant type), Manager(Participant type) and System(System type).


  * **Milestone**
Milestones are indicators used to highlight different stages of a process. They are purely symbolic and do not affect the process behavior.
Milestones are marked in vertical columns.


  * **Decision Gateway**
Decision gateways are used to direct the flow of tokens along multiple paths. Depending on the type of gateway, the token can be made to take one/more path coming out of the gateway.
There are 4 types of gateways:

(a) Exclusive gateway:

In an exclusive gateway, the token takes the direction of the first condition that is satisfied.


(b) Parallel gateway:

This will direct the flows in more than one direction. In other words, it is used to fork the process in two or more directions.


(c) Inclusive gateway:

This is similar to an exclusive gateway, except that, the token takes the directions of all the conditions that are met/satisfied.


(d) Event gateway:

This gateway will wait for 2/more events to determine the flow through the gateway.


  * **Start Event**
This event is used to indicate the beginning of a process or service. This represents the starting point of the process.
There are 3 different kinds of start events:
(a) None event:
This is a simple event which is used to start the process/activity unconditionally. An activity can have only one none start event.

(b) Message event:
This type of event is used to trigger an event using a message sent through an under coverage agent.

(c) Adhoc event:
This is used to start an adhoc process, while another process is in execution.


  * **End Event**
This marks the end of a process/activity. There can be multiple end events for an activity.
The process will not end until all end events have been reached.
There are 4 types of end events:
(a) None end event:

This is a simple unconditional end event. The activity ends when this end point is reached.

(b) Message end event:

This is used to send a message through a UCA and immediately end the process.

(c) Error end event:

This is used to end the process in the event of an error.

(d) Terminate end event:

This is used to close all open tasks within a process. The process is then marked as 'terminated'.
And outstanding timers also get cancelled.


  * **Intermediate Event**
Intermediate events are used to pause the process flow until a specific event occurs. The occurrence is determined using a correlation\_id, which is evaluated using an UCA.


  * **Note**
This is used to label different parts of a process diagram. It can even be used as a place holder for leaving comments.


## Table explaining BPDs and their definitions ##

![http://i.imgur.com/wK7lBA3.jpg](http://i.imgur.com/wK7lBA3.jpg)
![http://i.imgur.com/dR955ty.jpg](http://i.imgur.com/dR955ty.jpg)


## Related Tutorials ##
[A Simple Business Process Definition](SimpleBPD.md)


## Some useful links related to BPD ##

**[Creating BPDs](http://pic.dhe.ibm.com/infocenter/dmndhelp/v8r5m0/index.jsp?topic=%2Fcom.ibm.wbpm.wle.editor.doc%2Fmodeling%2Ftopic%2Fcreating_bpd.html)**

**[Modeling BPDs](http://pic.dhe.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.main.doc%2Ftopics%2Fcbpm_bpd.html)**

**[Configuring BPD](http://pic.dhe.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.main.doc%2Ftopics%2Fcbpm_bpd.html)**