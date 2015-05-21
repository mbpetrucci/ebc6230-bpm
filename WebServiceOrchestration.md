#Web Service Orchestration.

[Back to Table of Contents](TableOfContents.md)

# Web Service #
A Web Service represent a software approach that uses composable services to build distributed applications in a distributed heterogeneous system.

[What is a WebService](http://en.wikipedia.org/wiki/Web_service)

[Introduction to WS](http://www.w3schools.com/Webservices/ws_intro.asp)


# Web Service Orchestration #

  * The Web Service Orchestration refers to an executable business process that may interact with both internal and external Web services.
  * Orchestration describes how Web services can interact at the message level, including the business logic and execution order of the interactions.
  * The interactions may span applications and/or organizations, and result in a long-lived, transactional process.
  * With orchestration, the process is always controlled from the perspective of one of the business parties.

## Modeling Web Service Orchestration ##
  * The Web Service Orchestration can be modeled by different modeling languages.
  * An example of those languages is the Business Process Execution Language for Web Service (BPEL4WS), which describes the Web Service Orchestration by  providing an XML-based grammar for describing the control logic required to coordinate Web services participating in a process workflow.
  * The process workflow of BPEL4WS is layered on top of WSDL and defines how the WSDL operations should be sequenced.
  * Web services technology rely on different XML-based languages, such as WSDL, which describes how the service can be called; SOAP, which is used as a message protocol between the service consumer and provider; and UDDI, which is used for publishing and discovering information about web services in the registries

## Implementing Web Service Orchestration in BPM ##
IBPM BPM allow the designer to invoke the web services in two ways:

  * **Outbound Web Services:**
In the IBPM PD, we can create an IBPM service that encapsulates the invocation of a Web Service. When this IBPM Service is called, the result is a call to the Web Service provider that the IBPM service is configured to call.
To achieve this, select the _Implementation_ category in the Library and in the Create New menu, select _Integration Service_.

> ![http://i.imgur.com/xoxh4n7.png](http://i.imgur.com/xoxh4n7.png)

Once selected and named, an empty service diagram is shown.
From the palette, a _Web Service Integration_ primitive can be dragged and dropped onto the canvas and wired into the flow.
It is this component that will perform the call to the external Web Service.

The next step is to select the Web Service calling component on the canvas and examine its Implementation properties.
Several online websites offer free web services with different functionalities and capabilities.
After selecting the web services, we insert the WSDL URI in the implementation tab of the _Web Service Integration_ properties.

> ![http://i.imgur.com/JXtsWcl.png](http://i.imgur.com/JXtsWcl.png)

  * When the Discover button is pressed, a new dialog is presented. This allows you to enter a username/password combination if the access to the target URL is restricted.
  * When the View button is pressed, a new dialog is presented. This allows you to view the WSDL source form.
  * when the Generate Types button is pressed, the data type definitions of the web service input and output will be created.
  * The Operation combo box allows to select between different operations of the web service

  * **Inbound Web Services**
An inbound Web Service is the notion that a IBPM solution can "advertise" or "expose" itself as a Web Service allowing it to be called from an external Web Service caller or client.
To construct an inbound Web Service definition, the selection can be made from the _Implementation_ category and selecting _Web Service_.

> ![http://i.imgur.com/j6kkDpO.png](http://i.imgur.com/j6kkDpO.png)

Once selected and named, the properties of the Web Service definition can be completed.
In the Operations section, press Add for each operation that is desired to be exposed on the Web Service.
For each operation added, an IBPM Service needs to be associated with it. This implies that the service must be created before adding the operation.
When deployed, a call to a named operation will result in the invocation of the corresponding IBPM Service.
Any parameters defined as input on the IBPM Service will be exposed as parameters on the Web Service call.
Any parameters defined as output on the IBPM Service will be returned as parameters on the Web Service call.

> ![http://i.imgur.com/8L0iFTp.png](http://i.imgur.com/8L0iFTp.png)


# Tutorials #
[Tutorial: Using Calculator Webservice](WebServiceIntegration.md)