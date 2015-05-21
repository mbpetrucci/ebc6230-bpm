#This page explains what a 'Human Coach' is in IBM BPM

[Back to Table of Contents](TableOfContents.md)

## Coaches ##

  * Coaches are the user interfaces for human services. There are two types of user interfaces for human services: dashboards and task completion. To build either type of user interface for human services, you use Coaches.

  * Coaches are the web-based forms that provide process-related data to end users as well as collect input from those users.

  * Coaches enable the users to add controls and fields like radio buttons, check boxes, drop down menu, input/output fields.

  * Coaches contain one or more Coach Views. The Coach Views provide the user interface elements and layout for the Coach.

  * Each Coach View can contain one or more other Coach Views, which creates a parent-child relationship between these Coach Views.

  * Each Coach View can also have a binding to a business object, CSS code to control its visual layout, and JavaScript to define its behaviour.

![http://imgur.com/WOF2N2m.png](http://imgur.com/WOF2N2m.png)

  * Coach Views are reusable so you can create a library of common user interfaces and behavior. You can combine these common user interfaces to rapidly develop new Coaches.


## Human Service ##

  * Human service is a kind of interactive service which allows us to add a step into our business process definition(BPD) in order to create an interactive task that "process participants" can perform in a web-based interface.

  * The main purpose of implementing human services in BPD is not only to improve the quality of service delivery systems but also to improvise on accessibility, accountability and coordination among process participants in the service delivery.

For example:
- If an activity requires a call center employee to enter data about   customer order requests, we can then create a human service.
- So basically these are the services with human interactions.

## Note: ##
Modelling services that contain coaches involves working in 'Coach Designer', which is an editor that provides an intuitive, drag-and-drop interface in which you can very quickly build and test your Coaches.


  * The following screenshot shows how a coach looks like in the designer and how the same looks like when run in the web browser:

![http://i.imgur.com/KtdwPef.jpg](http://i.imgur.com/KtdwPef.jpg)

## Tutorials ##
[A Simple Human Service Coach](SimpleCoach.md)