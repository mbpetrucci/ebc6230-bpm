#This page explains what data source means to the user.


[Back to Table of Contents](TableOfContents.md)


# Data Source #

  * Data Sources are used to establish a connection between an application and a relational database.

  * JDBC(Java Database connector) provides driver implementation classes which would connect with database.

  * The components of an application directly interact with data source.


## Sample screenshot showing the use of created jndi ##

![http://i.imgur.com/cGx29tP.jpg](http://i.imgur.com/cGx29tP.jpg)

  * As seen in this screenshot, jdbc/BPMCourse is the jndi created. This connects to 'BPMCourse' database.
  * 'JNDI\_BPMCourse' is the environment variable created.
  * The environment variable should follow the syntax: 

<JNDI\_DataBase>




## Note ##

  * Created jndi will be provided to you in this course.
  * An environment variable should be created to store the value of this provided jndi on different servers.
  * The environment variable should then be used within the process as the data source.

 Follow the tutorial to achieve these steps 


## Tutorials ##

[Using the created Data Source in Process Designer](Using_DataSource_In_IBM_BPM_Process_Designer.md)