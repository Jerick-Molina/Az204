<h1 style="text-align: Center;font-weight: bold;color:" >
Connect to and consume Azure services and third-party services(15-20%)
</h1>
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Logic Apps |
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

The Azure-204 exam will expect you how to:
1. Create a Logic App
2. Build a Custom Templates
3. Build a Custom Connector

&emsp;
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes |
</h3>

 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--Logic Apps-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Logic App?~>
</h4>


**Azure Logic App** is a cloud-based platform for creating and running automated workflows that integrate your apps, data, services, and systems.Creating high scalables integration solutions for your enterprise and *business-to-business* (B2B) scenarios. **Logic Apps** simplifies the way that you connect legacy,modern, cutting-edge systems accross cloud, on-premises, and hybrid enviroment.

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--Editing your workflow-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Edit your choices~>
</h4>

***Logic Apps Designer*** is a GUI to build you logic triggers and actions.

***Code View Editor*** can be used to edit your **Logic Apps** if you dont like to use the GUI

*Business-To-Business* workflows are built automated scalable enterprise integrations workflows by using ***Enterprise Integration Pack*** (EIP) to create solutions and seamless communication between organizations with Azure Logic Apps

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--Connecting your connections-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a 'Custom Connector' for Logic Apps?~>
</h4>

A **Custom Connector** is used to create connections through REST or SOAP APIs to allow communicaiton to and from **Logic Apps** for applications where Microsoft doesn't have a pre-built template.

&emsp;
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--The Commandments-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Azure CLI~>
</h4>

**Creating a Logic App** : ``az logic workflow create``
- *Parameters*: ``--definition / --location /--name / --resource-group `` *etc.*

&emsp;
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| API's are your friends |
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

The Azure-204 exam will expect you how to:
1. Create an APIM instance
2. Configure authenticaiton for APIs
3. Define policies for APIS

&emsp;
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes |
</h3>

 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--API Management-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a API Managemnt?~>
</h4>


***API Management*** is a way to create consistent and modern API gateways for existing back-end Services. Proving the core competencies to ensure a succesful API program through developer engagement, business insights, analytics, security, and protections.


&emsp;

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| How do you Manage these APIs' ?~>
</h4>

There are **3** ways to manage your APIs

1. **Developer portal** - Serves as the main web presense for developers where they can:
     - Read API documentation
     - Try out an API VIA interactive Console
     - Create an account and subscribe to get API keys
     - Access analytics on their own usage


2. **Azure Portal** - The administrative interface where you can set up your API program to use:
    - Defining or importing API shema
    - Packaging APIs into products
    - Setting up policies like quotas or transformations on the APIs
    - Getting insights from analytics
    - Managing Users

3. **API gateway** - The endpoint that:
    - Accepts API calls and routes them to your backends
    - Verifies API keys, JWT Tokens, certificates, and other credentials
    - Enforces usage quotas and rate limits
    - transforms your APi on the fly without code modificaitons
    - Caches backend responses where set up
    - Logs call metadata for analytics purposes


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Configuring authentication~>
</h4>

`` Settings > Custom domains > Gateway(add) > Negotiate client certificate``


&emsp;

<!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--GOP-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Groups~>
</h4>

**Groups** are used to manage the visibility of products to developers. Which API management offers system groups such as:

1. **Administators** - Azure subscription admin are members of this gorup. Admins manage API managemnet service instances, creating the APIs ,operations, and products that are used by developers.

2. **Developers** - Authenticated developer portal users fall into this group. Devs are the customers that build apps using your APIs. Devs are granted acces to the **Developer Portal** and build applications that call the operations of an API.

3. **Guest** -  Unauthenticated developer portal users, such as prospective customers visiting the developer portal of an API Management instance fall into this group. They can be granted certain read-only access, such as the ability to view APIs but not call them.

&emsp;

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Operations~>
</h4>
 
**Operations** in API Management are highly configurable, with control over URL mapping, query and path parameters, request and response content, and operations response caching. API are foundations of an API management service instance.

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Products~>
</h4>

**Products** are how APIs are surfaced to developers. Products in API management have one or more APIs, and are configured with a title, descriptions, and terms of use. Either it can be *Opened* or *Protected*

- **Opened** - Open can be used without a subcription

- **Protected** - Developers must 'subcribe' before they can use the API

&emsp;
<!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--Following the Policy-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What are policies in API Management?~>
</h4>

**Policies** Allow Azure portal to change the behavior of the API through configuration. They're a colection of statements that are executed sequentially on request or response of an API. They're written in XML and can be seen as follow:

```XML
<policies>
    <inbound> 
        <base /><!-- statements to be applied to the request go here -->
    </inbound>
    <backend>
        <base /><!-- statements to be applied before the request is forwarded to 
         the backend service go here -->
    </backend>
    <outbound>
        <base /><!-- statements to be applied to the response go here -->
    </outbound>
    <on-error>
        <base /><!-- statements to be applied if there is an error condition go here -->
    </on-error>
</policies>
```


&emsp;
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--The Commandments-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Azure CLI~>
</h4>

Creating a service : ``az apim create``
 - parameters: `` --name / --resource-group / --publisher-name /--publisher-email / --no-wait ``

 <!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Powershell~>
</h4>

Creating a service: `` New-AzApiManagement``

Creating a api management api:  ``New-AzApiManagementApi``


&emsp;
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Event-based solutions|
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

**Event hubs**: 

1. **Event Hubs** can be configured to retain data from 1-7 days. Any longer, it would be stored somewhere else
2. **Event Hubs** are identical to ***Apache Kafka*** but not the same. Look out for questions that say "Event hubs for Apache Kafka" when taking the exam, as there are nuances between the two
3. When storing data, you can enable ***Event hub CAPTURE*** to specify time or size intervals when storing data in either Azure blob storage or Azure data lake storage (Gen1/2)

<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes !
</h3>


 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE EVENT GRID-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Azure Event Grid?~>
</h4>

**Azure Event Grid** allows yout to builds apps with event-based architectures.Its also considered as a "**Publisher/Subscriber**" service. Events pushed through Event Grid can be consumed by "Handlers" to monitor or act on data sent from Event Grid.Theres 5 concepts you need to aknowledge:

1. **Events** - What happened?
2. **Event sources** - Where the event took place.
3. **Topics** - The endpoint where publishers send events
4. **Event subscriptions** - The endpoint of built-in mechanism to route events, sometimes to more than one handler.
5. **Event handlers** - The app or service reacting to the event

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What can Azure Event Grid even do?~>
</h4>

There are 3 examples Azure Event Grid can provide:

1. Application intergrations
2. OPs Automation
3. Serverless app architectures

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| The 5 Commandments of Azure Event Grid~>
</h4>
 
 1.**Events** Are the data messages passing thorugh Event Grid that describe what has taken place. Each event is self contained , can be up to 64KB
 ```JSON
[
  {
    "topic": string, // The full resource path to the event source, Event Grid Provides this value
    "subject": string, // Publisher-defined path to the event subject
    "id": string,// The unique identifier for event
    "eventType": string, // One of the registered types for this event source. Ex: "CustomerCreated", "BlobDeleted", "HttpRequestReceived"
    "eventTime": string, // The time the event was generated based on the providers UTC time
    "data":{
      object-unique-to-each-publisher //Optional but Specififc information that is relevant to the type of the event. Ex: An event about a new file being created in Azure storage
    },
    "dataVersion": string, // Schema Version of the data object, Publisher defines the schema version
    "metadataVersion": string // Shema version of the event metadata, Event grid defines the schema of the top-level properties, Event grid provided the value
  }
]
 ```
 2.**Event sources** are responsible to for sending events to Event Grid. Each event source is related to one or more events. Its the upblisher and the specific Service generating the event for that publisher.

 3.**Event Topics** Categorize events into groups. Theyre represented by a public endpoint and are where the event source sends events to. Topics are divided into :

- **System Topics** - They're built-in topics provided by Azure Services, only way to see is by Subcribing to them. To subcribe, you provide information about the resource you want to receive evnets from. As long as you have access to the resource, you can subcribe to its events.
- **Custom Topics** - Are applications and third-party topics. When you create or are assigned access to a custom topic, you can see that custom topic in your subcription.

 4. **Event Subcription** - Define events on a topic an event handler wants to receive.

 5. **Event handler** - Is referred to as the ""Subcribers" theyre able to decide which events they want to handle and Event Grid will efficiently notify each interested subscriber when a new event is available.

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Event Grid Features~>
</h4>

Use event grid when in need of these features:

 - *Simplicity*: Its straight-forward to connect sources to subcribers in Event Grid

 - *Advanced filtering*: Subscriptions have close control over the ends they receive from a topic

 - *Fan-out*: You can subscribe to an unlimited number of endpoints to the same events and topics.

 - *Reliability*: Event Grid retries event delivery for up to 25 hours for each subscription

 - *Pay-per-event*: Pay only for the number of eevnts that you transmit
 


<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--The Commandments-->|
</h4>

**Azure CLI**:

- Creating topic: ``az eventgrid topic create ``
- Enable event grid resource provider: `` az provider register``

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE EVENT HUB-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Azure Event Hub?~>
</h4>

**Azure Event Hubs** is a big data streaming platform and event igestions service. Able to receive and process millions of events per second. Data send to an event hub can be transformed and stored by using any real-time analytics provider or batching/storage adapters.

When publishing a Event you have two choices **AMQP** or **HTTPS**.

- **AMQP**: requires the establishement of persistent bidirectional socket addition to Transport level security or SSL.

- **HTTPS**: requires additional TLS overhead for every request.

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| The 5 commandments of Azure Event Hubs~>
</h4>

1. **NamesPlace** - Provides DNS integrated network endpoints and range of access control and network integration managment featuers as *IP filtering*, *virtual network service endpoint*, *Private Link*

2. **Event Publishers** - Event publishers use Azure Active Directory based authorization with  OAuth2- issued JWT tokens or event Hub-specififc Shared Access Signature(SAS) tkane gain publishing access. Any entity that sends data to an Event Hub is an event publisher.

3. **Event Retention** - Published events are removed from an Event Hub based on configurable, time-based retention policy , here are some key points:

    - **Default** - shortest possible retention perios is 1 day(24 hours)
    - **Standard**, the max retention period is 7 days
    - **Dedicated**, max retention period is 90 days
    - if you cahnge the retention period, it applices to all messages including messages that are already in the event hub.

4. **Capture** - enables you to automatically capture the sreaming data in Event hubs and save it to your choice of **Blob storage account** or **Azure Data lake Service Account**. You cannot set a Message retention nor Capture feature with the basic tier you must upgrade your subscription.

5. **Partitions** - Can be thought as a "commit log". Partitions hold event data that container body of the event, a user defined property bad describing the event, metadata such as its offset in the partition, its number in the stream sequence, and service-side timestamp at which it was accepted.

&emsp;
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--The Commandments-->|
</h4>

**Azure CLI**:

- Event hub namespace: `` az event hubs namespace create``
- Creating Event Hub: ``az eventhubs eventhub create``

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE NOTIFICATION HUB-->|
</h4>

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Notification Hubs?~>
</h4>

**Azure Notification Hubs** is a PaaS Solution providing a simple cross-platform method for using push notifications in your applications. It works great for both enterprise and consumer scenarios.

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Push notifications?~>
</h4>

Push notifications are form of app-to-user communication where users of mobile apps are notified of certain desired informations.ANH is the best app-to-user communication because it is energy-effietient for mobile devices, flexible for the notfication senders and available when corresponding apps are not active. theyre usually sent to these 3 devices:

1. Apple
2. Android
3. Windows

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| How do 'push notifications' work?~>
</h4>

**Push notifications** are delivered through platform-specifi infrastructures called *Platform Notification Systems* (PNS). Offering basic push functionalities to deliver a message to a device with a provided handle and have no common interface. The simple way it works is as follow:

1. Retrive PNS handle(which device it is)
2. Store PNS handle
3. Send Notification to PNService
4. From PNS send notificaiton to device.


<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--The Commandments-->|
</h4>

**Azure CLI**:

- **Create Notification Hub namespace**: ``az notification-hub namespace check-vailability``

- **Create Notificaiton Hub**: ``az notification-hub create``

&emsp;

&emsp;
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Message-Based solutions|
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>
&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE STORAGE QUEUES->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Azure Storage Queue?~>
</h4>

**Azure Storage Queue** - is a service for storing large numbers of messages. Where you can call or access these messages via authenticated HTTP  or HTTPS calls. A queue message can be up to 64KB in size. The only limit how many messages is up to the total capacity of the storage accounts.

- Its designed for **asyncchronous** messaging between services
- Fast, simple, scalable soluition providing:
    - Simple REST accessibility (HTTPS or HTTPS), providing GET/PUT/PEEK
    caparabilities

- Doesnt support advanced messaging such as 
    - First in first out delivery
    - Automatic duplicate detection
    - AMQP standard-based messaging

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE STORAGE BUS->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Azure Storage Bus?~>
</h4>

**Azure Service Bus** is a fully managed enterprise message broker with message queues and publish-subcribe topics. **Service Bus** is used to decouple applications and services from each other, with the benefits of:

- Load-balancing work across competing workers
- Safely routing and transferring data and control across serivce and application boundaries
- Coordinating transactional work that requeries a high-degreee reliability

Common use scenerarios can be:

- *Messaging* -  Transfer business data, such as sales or purchase order, journals, or inventory movements.

- *Decouple applications* - Imporve reliability and scalability of application and services. Producer and consumer dont have to be online or readily available at the time.

- *Load Balancing* - Allow for multiple competing consumers to read from a queue at the same time, each safely obtaining exclusive ownership to specific messages.

- *Transactions* - Allows you to do several operations, all in the scope of a ATOMIC transaftion

- *Message sessions* - Implement high-scale coordiantion of workflows and miltiplexed transfers that require strict messages ordering or message deferall.

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Advanced features~>
</h4>

**Message sessions** - To create a first-in , first out guarantee in service bus.

**Security** - Supports AMQP and HTTP or REST protocols and their respective securit facilities, including transport-level security(TLS). Clients can be authorized for access using SHARED ACCES SIGNATURE or  Azure Active Directory role based security.


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Service Bus filters?~>
</h4>

Service bus supports 3 filter conditions:

1. **Boolean filters** - The **TrueFilter** and the **FalseFilter**  either cause all arriving messages (true) or none of the arriving messages (false) to be selected for the subcriptions. these two filters derive from the SQL filter

2. **SQL Filters** - A **Sqlfilter** holds a SQL-like conditional expression that is evaluated in the broker against the arriving messages' user defined properties and system properties.

3. **Correlation Filters** -  A **CorrelationFilter** holds a set of condidtions that are matched against one or more of an arriving message user and system properties.


