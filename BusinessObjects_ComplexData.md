#This page explains how to use complex data type in IBM BPM


[Back to Table of Contents](TableOfContents.md)


# Complex Data Variables #

  * Business objects(also called as Complex data variable) is used to present the business data in the business process.
  * It is basically a structure containing related data items.
  * A Business Object is commonly used to describe a series of attributes that apply to a concept being worked upon in a process.

Eg1: 'InventoryItem' can be a business object. It can be created as a structure containing multiple related items.
The 'InventoryItem' can contain related items like: 'materialNumber', 'description', 'unitPrice', 'quantity'.

Eg2: 'StudentInformation' can be a business data . It can have related multiple items like 'studentNumber', 'firstName', 'lastName', 'DOB', 'stream', ..etc..

## Sample screenshot of the complex data ##
![http://i.imgur.com/WnpJsR4.jpg](http://i.imgur.com/WnpJsR4.jpg)


## Tutorials ##

[Creating and using complex data types](TutorialBusinessObject.md)