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

![Table Achieving Success](/Table_Achieving_Success.png)

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

![RAML Example](/RAML_Example.png)

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

- DataSense is the proactivly discover of metadata from internal and external resources and makes them avaiable through DataSense Explore, through the Transform Message component and also while writing expression using auto-completion

In DataSense we have notification (indicates if DataSense is timing out) and indicator (provides status information and allow DataSense to restart if necessary) for issues

At runtime we can see Mule Event if we do a request and see them in the console window, with browser / postman and with log file:

- trough The **Log componer** helps manage and debug applications by logging important informations as error message, payloads and status notifications. We can also log personalized message
