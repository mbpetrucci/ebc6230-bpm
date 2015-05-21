#Undercover Agents (UCAs).

[Back to Table of Contents](TableOfContents.md)


# Undercover Agents (UCAs) #

  * An Undercover Agent (UCA) listens for triggers from external systems, Invoke UCA service components or for scheduled time based events.
  * UCAs are also responsible for firing either a Message Start Event or for firing an Message Intermediate Event that is contained within a BPD.

  * The UCA does not invoke the service explicitly, but instead,it queues the request to start the service on a logical queue.
  * The queuing mechanism is used to serialize the execution of UCA originated events. When the UCA places a request on a queue, any further requests placed on that queue are not processed until the previous events have completed which means that the associated services have completed.
  * One exception to this is the special queue called the Async Queue.

### Creation of UCA ###
  * To create a UCA, select from the Design list: Implementation -> Undercover Agent.
  * A new UCA window appears, which allows you to name the UCA and

![http://i.imgur.com/P5xvdqd.png](http://i.imgur.com/P5xvdqd.png)

There are two "Schedule Type" selections:
  * On Event: Fired as a result of an explicit Invoke UCA in a service
  * Time Elapsed: Fired on schedule from the run-time Event Initiated


## UCA with Event initiated ##
![http://i.imgur.com/A1wlsvx.png](http://i.imgur.com/A1wlsvx.png)


## UCA with Time Elapsed ##
![http://i.imgur.com/0BhZxzz.png](http://i.imgur.com/0BhZxzz.png)


  * When a UCA is scheduled, we can see it in the Process Admin Console under Event Manager -> Monitor
![http://i.imgur.com/lJ1IOik.png](http://i.imgur.com/lJ1IOik.png)
  * The UCA can also be seen in the process designer as another instance.