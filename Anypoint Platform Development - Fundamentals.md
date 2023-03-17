---
id: t31kcttwde2uhjrc33tc7dn
title: Anypoint Platform Development - Fundamentals
desc: 'Notes for Mulesoft Course'
updated: 1678264882018
created: 1678264882018
---

# Anypoint Platform Development - Fundamentals - Part 1

## Scenario
Scenario of course with different data that we must unify

 - We have a **MySql DB**
	- Unlock it building a **rest api** defined by a **RAML** for use the input and output of our api American Flights API using http
- We’ve got two other source of data integrated with another api, **United Flights**, but we don’t have spec (RAML) using http
- Finally we have a *Soap Service called Delta Soap* using xml

We must build an API called **MUA, Mule United Airlines Flights** who talks with the other api and brings them together. 
It provides the same data to the other access poin regardelss one is SOAP and other json

The client is ARC advanced rest client

## The new IT Operating Model

It operating Model consist in **delevop reusable assets**. 

The key of the strategy is **emphatic consumption as much as production**. The reusable assets aren’t only for maintaining the system but for reuse them in the final product

The classic operating model has some problem like

- limited opportunity to reuse
- No Tight Coupling = brittleness
- Difficult to govern

**The modern API are composable**

They must be 
- accessable/ discoverable through self-servic
- Productized and designed for ease of consumption
- Easily managed for security, scalability and performance

Instead of build on service, we build a group of api and thery are of different type

- **System APIs**, those who connect to the resources (db, salesforce, sap )
- **Process APIs** that process the file to be used for the client thought 
- **Experience APIs** like web application

For example we build this for a e-commerce on internet; if six months later arrives a request from the client to build a mobile application, me’ve to worry about only of the last level (Experience API)

The result of this approch is Enable and empower the entire organization

To Applicate and sponsor this method of work we have the 
### C4E (central for Enablement):

	Organising differently to drive API-led connectivity. Is a team that drive the person to use the correct approach. They promote across the organisation


### Modern API
Modern APIs are discoverable, accessible designed asy scalable e performant
They provide the info to communicate with softwares defining the
1. Operations
2. Inputs
3. Outputs
4. Underlyng data types

**NB:** They defines functionalities indipendent of implementations 

### Difference between APIs and web-services

APIs can be web service, proxy, documentation API

But there're many differences between APIs and web-services in fact web services are a method of communications between two softwares system and it allows them to excange data over the internet 

The term web service has several meaning similar but different 

- web service API
Describe how to interact with the web service. It may or may not be explicitly defined. It could be a sort of text in any type of file
- Web service interface implementing api  is the code providing the structure to the application so it implements the API 
- Web service implementation itself code and application

**Two types of web service**   

1. SOAP more complex required two protocol, soap use for code and decode, http or other protocol
2. RESTful simple type used

### REST representational state transfer
Is and architectural style where clients and servers exchange representations of resouurces using http

Rest is **Statelss**: the server doesn’t remember any client stat from previous request, but the client can cache previous response to avoid repeated calls 

Rest use **http request**

The _http request methods_ indicates which operation should be performed on the object identidied by the **url** 

- (GET)/companies: returns list of companies
- (GET)/companies?country=France:returns list of companies where country is France 🇫🇷 
- (GET)/companies/3:returns company at index 3
- (POST)/companies with JSON:method to add companies
- (DELETE)/companies/3: to delete company at index 3
- (PUT)/companies/3 with json: in http body replace company identifies or creat

### HTTP METHODS 
1. GET current state of resources
2. POST create a resources 
3. DELETE delete 
4. PUT replace a resources completely and if doesn’t exist, it creates
5. PATCH partally pudates a resource

Web service returns data in **media-type like json or xml**

Json(Javascript Object Notation) is light, human readable and supports collections and maps

Learning about APIs
API documentations
	list of resources
API portals 
	provides developers a centralized place where they can found all information about a specific api documentation, tutorial, exemple, way to register app, test
Directories and MarketPlace  like APIs.guru

We can call a restApi using postman and we can use sicure and unsicure API
Unsicure is public and require no auth
Secure require auth like token oath

### Common http code response
- 200 ok
- 201 created
- 304 not modified
- 400 bad request
- 401 unauthorized 
- 404 resource not found 
- 500 server error

### API-LED connectivity (3 layer )
The key is to produce discoverable and consumable assets, creating an API that developers can fins and want to use 

First Take an API design-first approach, getting it right before investin in building it. 

API development life cycle

1. API specification 
	- Design
	- Simulate 
	- Feedback
	- Validate
2. Simulate stage --> Web Service with API (Contract)
	- Build
	- Test
3. Deploying and managing the Web service
	- API Version
	- Policy to secure it
	- Deploy and register the web service
	- Monitoring the operation 
	- Analyze and report on the usage
	- Troubleshoot
	- Scale 
	- Respond to the changing need to restart the life cycle


## Introducing to anypoint platform

Anypoint Platform is a unified platform that has all the components for entire api live circle, to design, build, deploy and manage. 

It includes tools to createt modern APIs and it is formed by
1. **Anypoint Design Center**, where we can create the API
2. **Anypoint Exchange**, that make our API discoverable and accessable
3. **Anypoint Managment Center**, manage for security, scalability and performance 

Anypoint allows you to design and deploy anywhere like costumer custom enviroment, Private Cloud and Mulesoft Hosted Enviroment: **CloudHub**, a fully managed iPaaS Solution. The application mantain the same connectivity option 

### Benefit of Application Network
The application Network build throught API-led connectivity make uses of Integration and API managment and this architecute has different benefits

- Speed of delivery
- Actionable visibility
- Secure by design
- Future proof architecture
- Intentional self-service

### Achieving success with Anypoint Platform: Mulesoft Catalyst 
It is the approch of Mulesoft with the Client's success
and it has 3 core pillars:
1. Identify business Outcomes with KPIs and align stakeholders
2. Technology delivery 
	- Anypoint Platform
	- Project
3. Organization Enablement, ensure your organization is ready to use and adopt the anypoint platform
	- Center for Enablement
	- Internal Support 
	- Training 

For each pillar there're steps achive success: Focus on planning, Establish the foundation, build to scale and measure impact

![Table Achieving Success](/img/Table_Achieving_Success.png)

### Introducing Anypoint Platform's Component

During API development cycle there're different tool the supports each face:

- **API Designer**: Used to describe the contract that provides all the details about operation, input and output
- **API Console & Mocking Service** Interact with and Simulate the API 
- **Exchange** Allows you to publish the API's specification, which automatically create an api portal making discoverable by other stakeholders, which allows them to provide feedback
- **API Notebook** Added to portal to combine documentation with javascript code to demostrate how api can sodisfies different cases. 

The output of this components is a **Validate API Specification**, created using **RAML**

The next face after created the RAML is the **API Implementation** using **Anypoint Studio**.
We can use also Composer, a web-based tool without code 

After the implementation we can go to the last face: **API managment**.

Api Manamgment is formed by: 
- **API Manager**, used to create a proxy application which exstablish an initial version of API specification and then allows you to update it and to manage ands secure API through policy that control access and request.
- **RunTime Manager**, used to deploy and register the web service and to monitor its performance. We can also use **Anypoint Monitoring** that gives us different info like performance visibility, data visualization tool, issues, log analization 
- **API Analytics** pubs analyze and report how the application is used
- **Visualizer** provides you real time view of application network and helps you to catch issues quickly 

The final steps in this cicle is reapet this phases to update the API's Specification 

For reusable assets we have Anypoint Exchange.
It provide all user the able to discover and self-serve this API or other Assets and use them with Studio. We've two Search Method

1. Legacy
2. Functional

When a rest API is publish to exchange, an API portal is automatically created for i.
An API portal has

- Auto-generated API documentation
- Api console for consuming and testing APIs
- An Automatically generated API endpoint that uses a mocking service to allow the API to be testet without having to implement it

API portals can be shared with internal & external users

When we publish a API on Exchangew, a connector is automatically created. It can be used in mule applications to call that API. **Rest Connect** is the technology that perform this conversion

 - Example

		A central IT publish APIs templates on Exchange. The rest of the team create the project using that APIs and then they load their project on Exchange

### Design Center
Design Center contais API Designer and Anypoint Studio, 
Mule Application is Internal Java Application

### Mule Runtime
**Is a Lightweight integration and automation platform** that allows developers to connect apps together quickly and easly, enabling them to exchange data 
- Acts as a transit system for carrying data between apps (the mule)
- Can connect all system including web services, JMS, JDBC, HTTP..

**Decouples point-to-poin integrations** by having all apps talk to a Mule runtime instead of directly to each other

**Enforces policies for API governance**

**Can be deployed anywhere** can integrate and orchestrate events in real time or in batch, and has universal connectivity

## Designing API 

Different method to design API 

Hand coding, 
API BluePrint documentation, markdown, 
OpenAPI Spec json based, descripted, generate osCode, 
AsymcAPI language describe message inteface, supported by Design Center,
RAML

### Introducing RAML
RAML is a simple, structured, and succint way of descrbing RESTful APIs. 

It is open source, it was developed to help out the current API ecosistem and encourage reuse, and auto-generated documentation, mocked endopoints, interfaces for API implementations

It is based on broadly-used standards like JSON and it hses a human-readable data format where **data structure hierarchy is specified by indentation**

Resources are the objects identified by url, all recources begans with /

The method and parameters are nested under a resources and nested resources are used for a subser to narroe it. Finally URI parameters are enclosed in {}

![RAML Example](/img/RAML_Example.png)

### Using RAML to define specification 

Response must be a map of one or more HTTP status codes. For each response, specify possible return data types along with description and example

```
/{ID}:
	get:
		responses:
			200:
				body:
					application/ison:
						type: AmericanFlight
						examples:
						output:
							ID: 1 code: ER38sd
							price: 400
							departureDate: 2017/07/26
						 origin: CLE
							destination: SFO 
							emptySeats: 0
							plane:
								type: Boeing 737
								totalSeats: 150
```

For a request similary specify the possible request data types along with description and examples

```
/{ID}:
	get:
	post:
			body:
				application/ison:
					type: AmericanFlight
					examples:
						input:
						 ID: 1 code: ER38sd
							price: 400
							departureDate: 2017/07/26
						 origin: CLE
							destination: SFO 
							emptySeats: 0
							plane:
								type: Boeing 737
								totalSeats: 150
```

**NB** We can use example for one data or examples to represent multiple instances of data

### Engaging with users
To build a successful API you should define it iteratively, getting feedback from developers on usability and funcionality

To do this we can use API portals in Exchange, in private for internal developers or in public portal for the others

In pratic we publish our RAML API spec and other assets to Exchange from API Designer. When we public them, we can specify their statre: 
- Development: still in the iterative design process
- Stable: ready for consumption

API portals are automatically created for REST APIs added to Exchange

## Building APIs

There're 2 stages to building APIs. The RAML specification can be used to build api implementation

To begin with it we star from **Mule 4 applications**

A mule application is a sequence of **Mule event processors**, organized in **flows**

A flow has 3 main areas: 
1. Source Area controls how a flow is triggered
2. Process Area throught Mule event processor(s)control what flow does
3. Error Handling

A mule application is a series of xml files that have multiple flows

The source initialized the execution of the flow. Next the data and meta-data are processed, transformed, filtered, enriched by Mule event processors

The data structured passed from the data source is called **Mule Event** and has two main elements: **Mule Message** and **Variables**

Mule message is formed by two ohter elements: **Attributes** and **Payload**
1. Attributes are considered to be the metadata describe the details about payload
2. Payolad is the actual data to process

For example if a post HTTP request is sent to the application the payload will contain the data to create new resources while attributes contain the parameters and headers

### Creating Mule applications in Anypoint Studio

Anypoint Studio is based on eclipse IDE and allows you to create Mule application throught graphical elements and XML views. 

It includes Pre-built tooling to connect APIs, protocol and popular services. It has a data transformation framework and laguage and offers the ability to edit and sync APIs specifications with Anypoint Platform; you can also run, debug, deploy Mule Applications

The interface on AS is based on layout concept called Prospectives. Each contains panels and each contains views.

3 Prospective one for development, one for  api and one for design

Mule apps are build using connectors and processors that are contain in the palet. We can load new resources 

We can also implement automatic test using **MUnit** and it's fully integrated in AS

### Connecting Data

- **Database Connector**
	- Can connect almost any JDBC relational database
	- Config url and driver, jdbc driver
	- We must do query to get the data from db

For most operations a lot of the configuration is encapsulated in a separate global element, and it is a reusable configuration that can be used by many operation 

### Trasforming Data

To make data readable we use **DataWeave 2.0**: it is the expression language for mule to access, query and trasform Mule event data.

It is fully integrated with Studio, it has a graphical interface whit payload-aware development. The **Trasform Message** component is used for this type of trasformation

To test we can use DataWeave Playground, an interactive browser enviroment for mocking.

### Creating Restful Interface
We can create them manually or automatically usink **APIkit** and API specification created before

APIkit can automatically create interface from a RAML API def, for new or existing project

It generates a main routing flow and flows for each of the API resources / method 

### Connecting interfaces to implementations 

Large flows can be broken into multiple little flows to promote code reuse. This process make the graphical views and xml more readable and facility the MUnit tests

All flows are identified by name and can be called via **Flow Reference** comoponents in other flows

In the end studio can list all flow references to a flow or subflos

### Synchronizing changes to API specification between Studio and Platform 

**API Sync** feature of Anypoint studio enables you to: 
- Pull Specification from designer center into Studio
	- You can also initiate the cration of API scpecification from scratch in studio
- Edit the specification offline in Anypoint Studio
- Push the updates back to Design Center
- Publish the new API asset version to Exchange

This lets you develop Mule Apps while following API lifecycle development pratices from within Anypoint Studio

If an API spec. changes in Exchanges, the generated API interface in Anypoint Studio can be updated
 - **NB**: Flows that have already been modified aren't overwritten 

**API Design perspective** includes git staging tab, in fact under the hood, **a GIT version control system is used to pull, push and merge branches made to API specification**

If someone modifies the version in Design Center while you're working on the same version locally, a **conflit** is triggered in GIT: We must tell git how to apply the changes over a modified version

## Deploying and Managin APIs

There'are 3 primart options to deploy mule application: 
1. CloudHub: it is used as virtual machine on AWS. It's fully managed, multi-tenanted and very secure
2. Customer-hosted Mule runtimes
3. Anypoint runtime fabric, it's a customer-hosted container sevice of the runtime plane

### **CloudHub benefits**

- Simplicity: no hardware to mantain, provides infrastructures for DNS and load-balancing, continuos software updates
- Highly secure
- Global avaiable

### **Customer-hosted benefits**
- Easy to install
- Require minimal resources
- Can run multiple apps
- Can be managed by Runtime manager in mulesoft-hosted and costumer-hosted Anypoint platform

### **Anypoint Runtime Fabric** 
It's a deployment model of the runtime plane

- Security and reliability through isolation between apps
- Re-deployments with zero downtime
- Automated application failover
- Run multiple version of the mule Runtime
- MuleSoft-supported containerized runtime images

### Viewing Deployed Apps with **Visualizer**

Real time insights into application newtwork. By organizing APIs in different relation diagram provides a view of application architecture suites to our role. This promotes layer-basede architectur consistency and allows to view issues quickly

Diagram data is secure and automatically & dinamically updated

Than we've 

### Anypoint Monitoring

It provides visibility into integrations across your app network. It has different monitor tools designed to reduce the time to identify and resolve issues through

- Aggregate and map metrics 
- Configure dashboards and alert
- Store and search log data 

### Create API proxy

Used to manage access to our web-service, through an **API gateway**.

An API Gateway is a runtime designed and optimized to host an API or to open a coonection to an API deployed to another runtime. It is included as part of Mule runtime and separates orchestatrion form implementation concers

- Determines which traffic is authorized to pass through the API backend services
- Meters the traffic flowing through
- Logs all trnsactions
- Applies runtime policies to enforce governance like rate limiting, throttling and caching

### Restricting Access to api

The API manager is used to manage access to API procies, it define SLA (Service Level Agreement) tiers and apply runtime policies. We can enforce them with API Gateway

**API Autodiscover** is a mechanism that enables a deployed mule application to download policies from API Manager and act as its own proxy

There're **Out-of-the-box policies** for common use case like
- Rate limiting
- Spike control
- Security

We can also define costum policies using xml and YAML and apply multiple policies and set the order; finally we can define automated policies to comply with common requieements 

### Granting access to APIs

To access an APIs tha's restriced by an SLA based policy consumers must Register their application to exchange, with Request Access button, select a TIER and request access. Once approve they've credential and pass their client credentials in calls made to the api

The owner of the api recieve a notification and then can approve or refused the request

### Adding Client ID enforcment to API specifications 

The client_id and client_secret must be added in the head of each calling of our API. So we must modifiy the API specification 

# Anypoint Platform Development - Fundamentals - Part 2

## Viewing information about Mule 4 event

We can view data with 2 method: At the design time with **DataSense** or during the run time 



![MULE Event](/img/Mule_Event.png)

- DataSense is the proactivly discover of metadata from internal and external resources and makes them avaiable through DataSense Explore, through the Transform Message component and also while writing expression using auto-completion

In DataSense we have notification (indicates if DataSense is timing out) and indicator (provides status information and allow DataSense to restart if necessary) for issues

At runtime we can see Mule Event if we do a request and see them in the console window, with browser / postman and with log file:

- trough The **Log componer** helps manage and debug applications by logging important informations as error message, payloads and status notifications. We can also log personalized message

### Debubbing applications with Mule

Debugger is a separate process that communicates with mule runtime using port 6666 (it can be change). While debugging the app can be stop through breakpoints (They can be manage in the breakpoints list)

This allow us to step-trought our mule application 

### Tracking event data with debugger

What happens to event object when calls are made to an external resource from a flow

### Setting request and response data

For the setting we can use

- Payload, we view the Set Payload but we can costumize it also whit Http Listener Responses changing the content of the body, also in Http Request we can changing body, headers, query / UI parameters, 

### Using DataWeave expression to read and write event data

Dataweave is a case-sensitive expression language that allows you to access the content of Mule Event including payload, attributes and variables. 
We can write DataWeave expression in the properties of any processor or global elements 

DataWeave can be evaluated in: 
- **Standalone** scripts using trasform message processor 
- **Inline Expression** properties where're enclosed in #[]

Using Dataweave expression we can access all the parts of mule event: 
- Server
- Mule instance
- Mule Application 
- Mule flow:
	- message: #[message.payload]
	- attributes: #[attributes.queryParams.param1]
	- payload: #[payload]
	- vars: #[vars.foo]

Sometimes we can access to the same value using different Dataweave expression, for example: 
- #[message.attrubutes.mehod] = #[attributes.method] = POST
- #[attributes.headers.host] = mulesoft.org
- #[attributes.header['user-agent']] = Mozilla
- #[message.payload.id] = #[payload.id] = #[payload['id']] = abcdef
- #[payload.itemsTotal] = 200.34

Selector are used to access information in object and arrays for example:
- value of a key:value pair --> #[payload.name]
- value at selectd array index --> #[payload[0].name]
- Array with values of key:value pair --> #[payload.*name]
- Array with values of key: value (Descendent values) --> #[payload..zip]

**Operations**: 

- *Arithmetic* +,-,/,* --> #[payload.age * 2]
- *Equality* ==,!=, ~= --> #[payload.name == "max"]
- *Relational* >,>=,<,<=, is --> #[payload.age > 30]
- *Conditional* and,or,not --> #[payload.name == "max"] and #[payload.sur == "Mule"]
- *Type coercion* as --> [(payload.age as Number) * 2]
- *Default value* default --> #[payloas.type default "student"]

**Variables** can be created with the Set Variable Component and used with the vars keyword


## Structure Mule Applications

### Encapsulating processort into subflows

Makes the graphical more intuitive, xml more readable, code reuse and easy to test

Flows without event source are colled private flows
To create a subflow we can do manually dragging a Scope 
To call a flow to another we can use **FlowReference**, but if we autoextract it do manually the work

FlowReference is Sync

### Asynchronus queues
In asynch method the data doesn't come back 

The **VM Connector** can be used to make async calls between flows. It allow us to increase level of parallelism or communicate with other app using the same domain. 

**NB**: VM Publish Consume has a time wait and it's like a Flowreference, while VM publish is async and the data doesn't come back

### Organizing mule application files

We separate interface and implementation, but we can create anothers files to make the project easy to read/work. Normally we create configutation file that can be used to encapsulate all our global reusable element. 

We can also separate functionality in different file

We can create a **Domain Project** used to share global configuration elements between applications. We create Mule domain project and associate mule application with a domain 

### Organizing and Parameterizing application properties

Mule can be configured to use **properties placeholder** to dinamically replace static values with value stored in .yaml o .properties file 

1. Create file YAML or .properties
2. Set value in hierarchical method
3. Create Configuration properties global element

PlaceHolders have two format: 
- ${db.port} for element configurations and event processore
- {port: Mule::p('db.port')} in Dataweave expression

Properties placeholder can be overriding by system properties when deploying in different enviroments in cloudhub. They can also be set using JVM parameters from 

Anypoint studio or command line

### Organizing Mule project files
**Maven** is a tool for buiding and managing any java-based project

Create correct dir structure

POM (Project object Model) is an xml file

### Managing metadata for a project
It is often beneficial to define metadata for an application. Not always is present so we can define with **Metadata Editor**

In application-types.xml the metadata are defined

## Consuming Web services

### Consume REST web-service

Exist a system that if our API is on Exchange it generates REST Connect Connector (It requires only the operation names and datasense is automatically gives us, errors've the name of the API)

If is not present a connector in Exchange for a particular RESTful web service we can use HTTP request with GET Method. 

With HTTP we must put URL "Stuff" and the datasense must be done manually with example and schema, errors've the HTTP name 

### Consume SOAP web-service
If isn't present a Connector we can use **Web Service Consumer** connector. 

We must: 
- Add it to the project
- Confugure it in global element config,which includes the location of the WSDL
- Use the Consume operation
- Select the SOAP operation to invoke

Some soap operations may required input parameters, We can use Transform Message component to pass it. The avaiable parameters will be detected to Datasense

## Controlling event flow

How create single interface to use the different airlines
There'are two tecnique 

1. To combine the result of all airlines
2. Return flights for single airline or all combine

Multicast events
Route events based on condition and validate events

### Routing Events
Thera are other 4 flow control components that allow us to route events: 

1. **Choice**
	- one route executed based on logial condition - cond 1, 2 .. default
2. **First Successful** 
	- Routes executed sequentially until one is successfully executed
3. **Round Robin**
	- One route executed, which one is selected by iterating through a list maintained across executions, it works as low balance 
4. **Scatter-Gather**
	- All routes executed concurrently, and then normally they are unified in a object of objects. It contains key that rapresent the index

	### Multicasting Events


### Validate Events to catch potential error

We can use the Validation Models. They provide a way to test some condition are met and throw an Validation Error if the validation fails

## Handling Errors

Can be handle a different levels: at application level and a flow level and processor level

### Reviewing the default handling of messagging errors

**Default Behavior**: An error was thrown, the process will stop and the event is passed to the first processor in Error Handler, this is a Flow Error Handler. 

All mule apps have **default error handler**, his behavior is to  stop the execution of the flow and logs information about the error. It cannot be configured

When an error is thrown, an error object is created with different properties like .description and .errorType

ErrorTypes are identidied by a namespace and an identifier: 
- HTTP:UNAUTHORIZED,
- HTTP:CONNECTIVITY,
- VALIDATION:INVALID_BOOLEAN

Each error object has a partent error type that is used to trace the error key

Exist two tipe of error: 
- General (can be handled): 
	- Any
	 	- Unknown
		- Trasformation
		- Routing
		- Connectivity 
			- Retry_Exhausted
		- Expression
		- Security
			- Client_Security
			- Server_Security
- Critical (cannot be handled): 
	- Fatal
	- Overload

### Creating Error Handlers
Add a scope like a flows: there're two types of scope: 
- **On Error Propagate**
	- All processor in the error handling scope are executed
	- At the end of the scope:
		- The rest of the flow that threw the error is not executed
		- The error is *rethrown up to the next level and handled ther*
	- An HTTP listener returns an **error** response
- **On error Continue**
	- All processor in the error handling scope are executed
	- At the end of the scope:
		- The rest of the flow that threw the error is not executed
		- The error *is passed up to the next level as if the flow execution had completed successfully*
	- An HTTP listener returns a **successful** response


### Handling errors at the application level

We can create a default Application error handler executed when no flow Handler avaiable

### Handling specific types of errors
If we have more than one scope we must specify the error that should be executed. If there'arent no match the error would pass to the default Mule error Handler, not to the application default Handler

### Handling errors at the flow level 
All flow except subflows have their own error handlers 

### Handling errors at the process level 
It works as try catch 

### Mapping errors to custom error types
To handle trableshooting we can costiumize each error types. We must use UNIQUE namespace

### Reviewing and integrating with APIkit error handling

### Handling System Errors
- Thrown at the system-level when no Mule event is involved
- Errors that occur durin application start-up and when a connection to an external system fails

They can be handled by a system error handling strategy
- No congigurable
- Logs the error and for coonnection failures, execute the **Reconnection strategy**


## Writing DataWeave Trasformation

**MAP command** to apply a trasformation to each element in an array where the input can be jsno or java and it returns an array of elements.

With map command we can use the $ sign for:
- '$$'  refers to the index or key
- $ refers to the value

**NB** In the map function we can pass parameters, for example: 
- payload map (object, index) -> { lambda function }

	```
	payload map (user, index) -> {
		num: index,
		fname: user.firstname,
		lname: user.lastname
	}
The map function iterates all eleme nts of the array and passes each element to a **lambda** that is an anonymous function 

### Transform complex XML Data stucture

Xml not support array so when mapping array elements (JSON or JAVA) to XML wrap the map funcion in **{()}** where:
- {} are defining the object
- () are trasforming each element in the array as a key/value pair

```
	output application/xml
	---
	users:{(payload map (user, index) -> {
		user: {
			num: index,
			fname: user.firstname,
			lname: user.lastname
		}
	}
	)}
```
### Defining and using variable and functions 
We can create global variable using **var** keyword and assign it a constant or lambda expression. Global variable can be refered anywhare in the body

NB: Dataweave is a functional programming language where variables behave just like functions

Example:
```
output application/xml
var mname = "the"
var mname2 = () -> "other",
var lname = (aString) -> upper(aString)
---
name:{
	first: payload.fName,
	middle1: mname,
	middle2: mname2(),
	lastname: lname(payload.lastname)
}
```
We can also use fun directive, a sintax similar to the classic function
```
output application/xml
fun lname(aString) = upper(aString)
---
name{
	first: payload.fName,
	last: lname(payload.lastname)
}
```
We can also use local variable in the body of Message using the keyword do
```
do { var name = payload.firstname ++ " " ++ payload.lastname --- name}
```

### Formatting and coercing data
We can do it changing the dataType using **as** keyword: it's called Coercion

With particular dataType like DateTime we've a format option: 

someDate as DataTime {format: "yyyyMMddHHmm"}

### Custom Data Types
We can declarete them with **type** keyword in the header
```
output application/json
type Ourdateformat = DateTime {format: "ddMMyyyy"}
---
someDate: payload.departureDate as Ourdateformat
```
We can also use Java classes to corece the data or define custom classes using default class keyword

**Specify inline**

customer: payload.User as Object {class: "my.company.User"}

**Define custom data type to use**
```
type User = Object {class: "my.company.User"}
---
customer:payload.User as User
```

### Using Dataweave functions

Functions with 2 parameters can be envoke with 2 sintax
- #[contains(payload, "max")]
- #[payload contains "max"]

Functions in all other module must be imported 

Import a function in a module
- import dasherize from dw::core::Strings

**Function Examples**
```
planeType: dasherize(upper(replace(object.planeType,/(Boing)/) with "Boeing"))
```

### Looking up data by calling flow

**lookup** keyword allow us to execute another flow within our app.
```
{a: lookup("myFlow", {b:"Hello"})} 
```
- The first argument is the name of the flow to be called (cannot call subflows)
- The second is the payload to send to the flow as a map
- Whatever payload the flow returns is what the expression returns

## Triggering Flows
On different events

### Reading and writing files
4 connettor for working with files (they support file matching, locking, overwriting, appending and generating new files): 
- File (for locally mounted file system)
- FTP
- FTPS
- SFTP 

We can trikker a flow using **On new or Update file** module

### Synchronizing data with watermarks
**WaterMarks** allow us to monitoring if any record is added to file or databases. The first run synchronize all data, then in the other run only the added data are synchronized.

To do this on the first sync, the highest field value for any item in the data set is stored; then in the other syncs, retrieve that value and compare the value of each item and see if it is largest

NB The field with order values is often a RecordID or creation / modification timestamp. This identifier is called **watermark**

Watermarking process can be configuerd to automatically retrieve, compare and store the identifier which determine which data to process. We can do also manually. The app periodically check for new data

### Using liteners with automatic watermarking

Two watermarking in On new and updated file: CREATED_TIMESTAMP and MODIFIED_TIMESTAMP

In db connector on table roe we can specifi table, watermark column (used to filter the contents of the table durinl polling) and id column

### Publishing and consuming JMS
JMS stands for Java Messaging Service. It is a widely used protocol for communicate ashynconasly using middleware called JMS Broker.

A system can communicate 1 to many by subscribing and publishing to topics or with single system in point to point mode.

We can use **JMS Component**

## Processing Records

### Processing Items in a collection with for Each Scope
For Each Scope split a payload collection and process individual elements sequentially 

Then pass each event in a series o processor sequentially 
It's not for data modification!

### Processing Records eith the Batch Job Scope
Enerprice Edition ONLY: 
Split large messages into records that are processed asynchronously in a batch job

It is created especially for processing data sets 
- Splits large or streamed messages into individual records
- Performs action upon each record
- Handles record level failures that occur so batch job is not aborted
- Reports on the result 
- Potentially pushes the processed output to other system or queues

Batch Job contains three phases: 

1. Load and dispath (implicit)
	- Splits payload into a collection of records
	- Creates a persisetent queue and stores each record in it
2. Process (required)
	- Asynchronously process the records
	- Contains one or more batch steps
3. On complete (optional)
	- Reports summary of record processed
	- Provides insight into which records failed so you can address issues

	Batch records are queued and scheduled in blocks of 100 for improves performance 

	Error Handling 
	- Stop processing 
	- continue processing 
	- Continue processing until max number of failed records

### Using filtering and aggregation in a batch step 
Batch step has 2 attributes to filter records
- An accept expression 
- An accept policy [ALL , NO_FAILURE, ONLY_FAILURE] 

