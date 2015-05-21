[Back to Table of Contents](TableOfContents.md)

## Using the created Data Source in Process Designer ##

## Prior Steps: ##
Please see the related tutorials below.

Once these two above steps are performed and Data Source is ready to be used, following steps are to be followed to test the jdbc connection created in (2)


(a)	Create a General System Service. This option is available under Implementation



![http://i.imgur.com/sz8eXFu.jpg](http://i.imgur.com/sz8eXFu.jpg)



![http://i.imgur.com/IDGw2yD.jpg](http://i.imgur.com/IDGw2yD.jpg)



![http://i.imgur.com/XqYtZED.jpg](http://i.imgur.com/XqYtZED.jpg)




(b)	Drag ‘SQL Execute Statement’ which is seen under ‘Implementation’ listed under ‘ToolKits’. Connect using flowlines




![http://i.imgur.com/F2q1Isv.jpg](http://i.imgur.com/F2q1Isv.jpg)



![http://i.imgur.com/RcErUR4.jpg](http://i.imgur.com/RcErUR4.jpg)




(C) Make the necessary changes as seen below, under the propert section’s Data Mapping:

Sql: "Select getdate()";

Return Type: "XMLElement"

DataSourceName:"jdbc/bpmtest"


Create variables suitably:



![http://i.imgur.com/G29JQ5Z.jpg](http://i.imgur.com/G29JQ5Z.jpg)


Initialize the String value to map properly with the XMLElement.

![http://imgur.com/fm3Qpjc.png](http://imgur.com/fm3Qpjc.png)


Map this result XMLElement variable in the Propery section as seen below:



![http://i.imgur.com/wsQr4iL.jpg](http://i.imgur.com/wsQr4iL.jpg)



(c)	Run the process in the debug mode to step through the code: Select ‘Debug’ option which is right next to the ‘Run’ button as seen in the above screenshot.



![http://i.imgur.com/aUdpc2f.jpg](http://i.imgur.com/aUdpc2f.jpg)



Click on StepOver to traverse to the result:


![http://i.imgur.com/eYa5ulV.jpg](http://i.imgur.com/eYa5ulV.jpg)



With the above result, we can confirm that the connection to the DB is successfully established.