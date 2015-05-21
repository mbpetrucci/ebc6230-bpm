#This page explains what variables are in BPM, how can they be bound to a coach and how they can be mapped in a process

[Back to Table of Contents](TableOfContents.md)


# Variables #
  * Variables represent the data, which provides business context to a running process.

  * The data in a process can be passed from one step to another using variables.
So, variables are the place holders for storing process data.

  * Variables are "named" entities which have associated data types.

  * The variable names follow lower-camel case. The acronyms are written in upper case.
(For example: firstName, lastName, age, DOB etc..)


## Declaring Variables ##

Variables can be defined with a qualifier of input, output or private.

  * Private variables: Private variables only have scope within a process or service and are deleted when they end.

  * Input Variables: Input parameters are mapped to values that you can pass into the current process or service. Input variables have their values passed into a process or service when that process or service is initiated.

  * Output Variables: Output parameters are mapped to values that you can pass out from a process or service to a parent process or service. Output variables have their values returned from a process or service when it completes.

  * When a variable is defined, it is given a name and other attributes including:
> •(1) Data type – The type of data represented by the variable

> •(2) Default value – An optional default value

> •(3) Is List – A flag indicating that the variable represents a list/array of instances of the data type

> •(4) Documentation – Human readable documentation on the purpose of the variable.

# Binding Variables #
  * Every field in the coach should be bound to a suitable variable.

  * The Binding property allows us to select a variable instance who's content will be used to populate the Coach View and/or will be populated by the Coach View.

  * The View entry names the type of Coach View that will be displayed on the Coach.

  * The Control Id names the unique identity of the Coach View within the Coach.

  * The Label Visibility entry determines if the label associated with the Coach View will be shown when rendered.

Sample variables used in the process is shown in the following screenshot:

## The following screenshot explains how variables can be used: ##
![http://i.imgur.com/46WsKqP.jpg](http://i.imgur.com/46WsKqP.jpg)


## Setting default values on variables ##
  * When a variable is defined in a service or BPD as either input or private, a default value can be provided.

  * The default value is set in the variables tab if the "Has Default" check box is selected. If selected, the text area provides a place in which the default values can be placed.


# Variable Mapping #
  * Many activities have a Data Mapping section. This is the act of mapping the variables in scope in the BPD to the expected parameters of the service that is to be called by the Activity.

  * This applies to both input parameters and output parameters.

  * The Data Mapping screen area is split into two columns. One for input mapping (mapping BPD variables to the parameters expected by a service) and the other is for output mapping (mapping returned values from a service to the variables in the BPD).

  * Entry assistance is available to bring up lists of BPD scope variables which can be selected.

## The following screenshot shows data mapping section: ##
To map the variables to the current or next activity, we need to go to the data mapping section of the activity and add the respective variables to the input and output as shown here.

![http://i.imgur.com/c5aYYXJ.jpg](http://i.imgur.com/c5aYYXJ.jpg)

## Note1 ##
The variables defined in the scope of the BPD do not have to have the same names as the actual parameters of the service implementation. However their data types should be compatible with each other.

## Note2 ##
The data mapping can be on the main process level as well as the at the activity level but are mainly dependent on the input and output variables which have to be mapped accordingly.


# Tutorials #
[Create a listview on the coach from variables](ListView.md)