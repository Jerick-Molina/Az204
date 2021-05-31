<h1 style="text-align: Center;font-weight: bold;color:" >
Monitor, troubleshoot, and optimize Azure solutions(15-20%)
</h1>
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Caching |
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes !
</h3>

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--CONTENT DELIVERY NETWORK-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Content Delivery Network?~>
</h4>

**Content Delivery Network** allows you to create caches at not only other Azure Regions, but also Azure edge locations, making it so your application or website can promive smooth experiense no matter the location your users are accessing it from. CDNs store cached cotent on edge servers in **point-of-presense** (POP) locations that are close to end users, to minimize latency.

Benefits of using Azure CDN to deliver web site assets include:
- Better performance and improved user experience for end users, espcially when using applications in which multiple roune-trips are required to load content
- Large scaling to better handle instantaneous hgih loads such as the start of a product launch event.
- Distribution of user request and service content directly from edge servers so that less traffic is sent to the origin server,

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Content Delivery Network caching rules~>
</h4>

There are two ways to control how your files are cached:

1. **Caching Rules** - To set and modify default cache expiration behavior both globally and with custom conditions, such as URL path and file extension. Azure CDN prives two types of caching rules
    - *Global caching rules*: You can set one global caching rules for each endpoint in your profile, which affects all request to the endpoint. The global caching rules ovverides any HHTP cache-directive headers, if set

    - *Custom caching rules*: You can set one or more custom caching rules for each endpoint in your profile. Custom caching rules match specific path and file extentions are processed in order, and ovveride the global caching rules, if set

2. **Query Strings** - You can adjust how Azure CDN treats caching for request with query strings, if the file is not cacheable, the query string caching settings has no effect, based on caching rules and CDN default behaviors

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Content Delivery Network caching behavior~>
</h4>

with CDN, you're able to control how files are cached for a web request that contains a query string (``?``). Azure Content Delivery Network provides 3 types of query string modes:

1. **Ignore query strings** - As the default mode, the CDN *point-of-presence* node passes the query strings from the requestor to the origin server on the first quest and caches the asssets. All subsequest request for the asset that are served from POP ignore the query strings until the cached asset expires

2. **Bypass caching** - In this mode, request with query strings are not cached at the CDN POP node. the POP node retrives the asset direcly from the origin server and passes it to the requestor with each request.


3. **Cache every unique url**- Each request with a unique URL, including query string is treated as a unique asset with itsown cache.

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Why use CDN?~>
</h4>

1. Load webpages faster by delivering static content from a location clsoer to the requester

2. Steaming videos to clients on demand

3. Fast connection and control of IoT based devices

**Security**- CDN can deliver content over HTTPS(SSL) by using certificate provided by the CDN, as well as over standard HTTP. CDN is able to add CORS headers to the responses. Origin header supports default (HTTP and HTTPS) ports 80 and 443


&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE CACHE WITH REDIS-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Cache with Redis?~>
</h4>

**Azure Cache for Redis** is a backend in-memory date store. Redis brings critical low latency and high-throughput data storage solutions to mordern applications. Redis can be used a distributed data or content cache, a session storem a message broker and more. Redis offers 2 managed services:

1. Redis open-source

2. Redis Labs.

To add redis to your application you have to:

1. Install a package specific to your application runtime:

```
Install-Package Microsoft.Web.RedisSessionStateProvider
```

2. Configure your application to use your Redis Cache in Azure

```csharp
<add name= type= host= acessKey= ssl= />
```

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE FRONT DOOR-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Azure Front Door?~>
</h4>

**Azure Front Door** is a blobal, scalable entry-point that uses the Mircrosoft global edge netwrok to create fast, secure, and widely scalable web applications It works at a Layer 7 (Https/HTTPS layer) using protocol with split TCP and Microsoft's blobal network to imporve global connectivity. It also uses 2 of the same quiery string behvaior as CDN:

1. Ignore Query Strings
2. Cache Every Unique URL

**FrontDoor** can purge all of its assets with 3 ways:

1. **Single Path Purge** - Purge individual files based on their full path and extension: "/items/cars.jpeg"

2. **Wildcard Purge** -  Purge everything from the endpoint below the wildcard, which is represented as an asterisk: "/items/*"

3. **Root domain purge - Purge all the things from the root "/" of the endpoint

This is purged with http headers 

1. `` Cache-Control: s-maxage=<seconds>``

2. ``Cache-Control: max-age=<seconds>``

3. ``Expires: <http-date>``

&emsp;
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Monitoring and Logging |
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes !
</h3>

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE MONITOR-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is a Azure Monitor?~>
</h4>



***Azure Monitor helps you maximize the availability and performance of your applcations and services. It delivers a comprehensive solutions for collecting , analyzing , and acting on telemetry from your cloud and on-premises environments. This informations helps you understand how your applcaitons are performing and proactively identifying issues affecting them and the resource they depend on. EX:

- Detect and diagnose issues accross applications and dependencies with Application Insights
- Correlate infrastructure issues with VM insights and Container insights.
- Drill into your monitoring data with Log Analytics for troubleshooting and deepp diagnostics.
- Support operations at scale with smart alers and automated actions.
- Create visualizations with Azure dashboards and workbooks.
- Collect data from monitored resources using Azure monitor metrics.

**Azure Monitor Alerts** can help you react quickly or  even automate responses to critical issues.

*EXAMPLE*: "if a vm starts to see an irregular amount of activity that threatens to overwhelm it, you can set actions that will scale the Vm accordingly or have Monitor send a raven to alern an on-cal admin"

 <!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| How is it monitored?~>
</h4>

All data that is pulled in is monitored into two types:

1. **Metricts** - Metrics are numerical values that descripbe some aspect of a system at a particular point in time. theyre lightweight and capable of supporting near real-time scenarios.

2. **Logging** - Contain different kinds of data organized into records with different sets of properties of eachtype. Telemetry such as events and traces are stored as logs in addition to perfomance data so that it can all be combined for analysis. Using a service as Log Analytics. the languague used to query data is called 
**KUSTO QUERY LANGUAGE**


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What data is it consuming?~>
</h4>


**Applications** - App Monitoring Data
 - Perfomance and functionality of your code, regardless of platform.

**Operating System** - Guest OS Monitoring Data
 - Data from the OS of monitored virtual systems

**Azure Resources** - Resource Monitoring Data
 - Data abou the operations of a particular Azure resource

**Azure Subscription** - Subcription Monitoring Data
 - Data regarding the operation and management of your Azure Subcriptions

**Azure Tenant** - Tenant Monitoring Data
 - Data about tenant-level services such as Azure Active Directory


 **Custom Sources** Azure Monitor can also ingest data from any other REST client with the Data Collector API

&emsp;
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--The Commandments-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Azure CLI~>
</h4>

Install a monitoring solution: `` az extension add ``

Install a solution: `` az monitor log-analytics solution create ``


 <!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Powershell~>
</h4>

Install a monitoring solution: ``Install-Module -Name Az.MonitoringSolutions ``

Install a solution: ``New-AzMonitorLogAnalyticsSolution ``


&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE APPLICATION INSIGHTS-->|
</h4>

 <!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Application Insights~>
</h4>

**Application Insights** - is a feature of Azure Monitor. It monitors your live applications and it will automatically detect performance anomalies/issues. The main goal is to help dev teams understand how an app is performing and how it's being used..


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| How to enable?~>
</h4>

You're able to set up Applications Insights when creating or when resource is already created.

 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:pink;" >
|--Availability Alerts--|
</h4

**Url Ping Test** : A simple ping test that can be configured from the console



**Multi-Step Web Test** : A recording of web request in an ordered sequence to test complex scenarios( Only for VS Enterprise)

**Custom Track Availability Test**: Requires use of the TrackAvailability() method to send custom dta to Application Insights.