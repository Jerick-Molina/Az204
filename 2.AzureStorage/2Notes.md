
<h1 style="text-align: Center;font-weight: bold;color:" >
Develop for Azure Storage(15-20%)
</h1>
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Cosmos |
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
|<--COSMO DBs-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Cosmo DB?~>
</h4>

**Cosmo DB** is a fully managed scalability, No SQL database for modern app development. It offers Single-digit millisecond response times, and automatic and instant scalability, guarantee speed at any scale. **Azure Cosmos DB** is a PaaS offering that takes database administration off your hands with automatic management, updates and patching. Advantages for using **Cosmos DB**:

1. PaaS Offering
2. Multiple Development APIs
    - SQL

        - Best for when migrating from a SQL platform

        - Data is stored as JSON

        - Can be queried using SQL-esque queries

        - Dedicated SDK for developing with this API
    - MongoDB
        - Best when migrating from MongoDB

        - Seamless import and migration
    - Cassandra
        - Allows for quick conversion from Apache Cassandra

        - Connection string is all that needs updating

        - CQL is fully supported
    - Gremlin
        - More advanced form of Azure Storage Tables
        
        - Allows for global replication & high availability

    - Table
        - Fully managed graph databases
        
        - Allows for global repllicaiton, quick scaling and high availability


3. Highly Available
4. Guaranteed Low Latency

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Elements for CosmosDB?~>
</h4>

**Cosmos DB** has 3 types of elements that make up its database:

1. **Database Accounts** - Managing data and provisioned throughput.

2. **Database** - Is the unit of management for a Set of Azure Cosmos Containers

3. **Containers** -is the unit of scalability both for provisioned throughput and storage. 


 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--BILLING & PRICING-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Request Units?~>
</h4>

Azure Cosmos DB cost of all database operations with "**RUs**" Or **Request Units**. Its a performance currency abstratcing the system resources such as CPU, IOPS, and memmory required to perform database oparations supported by Azure Cosmos DB. The type of Account you use determines the way consumed RU get charged. Most important are these 2:

1. **Provisioned throughput mode** - Cost and performance are based on pre-set threshhold, if needed you can scale up or down. Being able to scale automatically or manually in increments of 100/RUs. **Best for consistent and predictable workloads.**

2. **Serverless mode** - You dont set a provision throughput, if not you get billed for the amountof Request Units that has been consumed by your database operations.
**Best for inconsistent, unpredictable workloads**


<!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--CONSISTENCY IS KEY-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What's the important of Consistency levels?~>
</h4>

**A | B | C = DATA**

**Consistency Levels** are ways to keep your Databases for high availiability, low latency, or both. There are 5 levels of Consistency:

- **Strong**
  - Involve Perfect Consistency
  - Higher write latency
  - Reduced availibality in failovers
  - Offers a linearizability guarantee
  - Red are guaranteed to return the most recent version of an item.

|STRONG | 1pm| 2pm | 3pm | 4pm | 5pm| 6pm |  
|:-:     |:-: |:-: |:-:  |:-: | :-: |:-:|
|**WestUS 2** (Reads) | A| B| C|| |
|**WestUS 2** (Writes) | A| B| C|| |
|**EastUS 2** (Reads) | A| B| C|| |
|**Japan 2** (Reads) | A| B| C|| |

&emsp;
- **Boundless Staleness**
   - Choose a method in which reads lag behind writes
  - When reads are performed against a region that accepts writes , guarantees are the same as with STRONG

|Boundless Staleness | 1pm| 2pm | 3pm | 4pm | 5pm| 6pm |  
|:-:     |:-: |:-: |:-:  |:-: | :-: |:-:|
|**WestUS 2** (Reads) | A| B| C|| |
|**WestUS 2** (Writes) | A| B| C|| |
|**EastUS 2** (Reads) | | | | A|  B| C
|**Japan 2** (Reads)  | | | | A|  B| C

&emsp;
- **Session**
  - Those in the same session read the same data at the same time
  - Other sessions recive it later, but in the same order
  - Most  widely-used choice for both single and multi-region application
  - Great for applications written to operate in context of a user

|Boundless Staleness | 1pm| 2pm | 3pm | 4pm | 5pm| 6pm |  
|:-:     |:-: |:-: |:-:  |:-: | :-: |:-:|
|**WestUS 2** (Reads) | A| B| C|| |
|**WestUS 2** (Writes) | A| B| C|| |
|**EastUS 2** (Reads) | A | B | C| |  | 
|**Japan 2** (Reads)  | | |A  ||  B| C

&emsp;

- **Consistent Prefix**
   - Reads never see out-of order writes
   - Regions may receive writes at diffrent times, but always in order

|Boundless Staleness | 1pm| 2pm | 3pm | 4pm | 5pm| 6pm |  
|:-:     |:-: |:-: |:-:  |:-: | :-: |:-:|
|**WestUS 2** (Writes) | A| B| C|| |
|**WestUS 2** (Reads) | A| B| || |C
|**EastUS 2** (Reads) |  | A |  B| | C | 
|**Japan 2** (Reads)  |  | |A  ||  B| C

&emsp;
- **Eventual**
  - No ordering guarantee
  - The replicas eventually converge
  - Clients may read values that are older than the ones it read before.
  - Ideal where order isnt important. I.E (retweets, likes)



|Boundless Staleness | 1pm| 2pm | 3pm | 4pm | 5pm| 6pm |  
|:-:     |:-: |:-: |:-:  |:-: | :-: |:-:|
|**WestUS 2** (Writes) | A| B| C|| |
|**WestUS 2** (Reads) | C| B| || |A
|**EastUS 2** (Reads) |  | B |  B| | A | 
|**Japan 2** (Reads)  |  | |A  ||  B | C
 

 &emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--PROGAMMING COSMOS-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What's are Cosmo Containers~>
</h4>

**Containers are scalable objects within your *CosmoDB databases*. They can be looked at like Cassadra namespaces or tables in relational databases. Theyre access via SDK from an application, or web explorer on the console. Theyre not just able to only store data, they can also store :

1. **Scale Settings**
2. **Functions**
3. **Triggers**
3. **Stored procedures**


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What's are Partitioning Keys~>
</h4>

Azure Cosmos DB uses **partitioning** to scale individual containers in a database to meet the performance needs of your application.

1. **Logical** - are how your data is organized which are using a Partition key. A Partition key is part of the containers index for data.   They're are two types of partitions. Its used in parallel with data items' unique "item id"

2. **Physical** - an internal implementation of the system and they are entirely managed by Azure Cosmos DB. When developing your solutions, don't focus on physical partitions because you can't control them. Instead, focus on your partition keys


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Scaling?~>
</h4>

**Scaling** is how big or how small your Cosmo DB is. Scaling must be set at the **Database** or **Container** Level. **Database Scaling** must be set at creating time as this will share provisioned throughput in all containers in that database.
**Container Scaling** can be set in the Container menu, but can be adjusted at any point. Theyre are two ways to scale:

1. *Manual* - You decide what your RUs max will be to ensure predictable pricing and scale

2. *AutoScale* - You pay for the highest RU/s in use for the hour. So if you use 100 RU/s for most of day, but then peak at 600 RU/s for an hour, you pay that hour 600 RU/s rate


 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--ServerSide Programming-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Scaling?~>
</h4>
Uses 3 options (Stored Procedures Functions, and Triggers) with mostly SQL API.
Written in Javascript. And all can be executed using the Azure Portal, JavaScript integrated query API, or the Cosmos DB SQL API Clients SDK's.

&emsp;

**Benefits**:
- **Procedural Logic** - JavaScript programming allows for sequencing complex data

- **Atomic Transactions**: All transactions performed in store procedures and triggers are Atomic
- **Performance** : Using JavaScript with JSON formattions allows for low-latency bulk data operations in addition to being able to pre-compile code and sequence updates based off triggers
- **Encapsulation**- Store procedures allows you to group logic in a single place

&emsp;

3 types of serverside programming:

1. **Stored Procedure**
    - ties to a container and executes inside the database engine.
    - Can read,update and delete documents
    - Can have input parameters 
    - Executed by applicaiton code calls or within the Azure Portal
    - Execute only on the primary replica

2. **Trigger**
     - same as SP
    - Same as SP
    - Cannot have input paramaters
    - Executed either explicitly before or explicitly after defined operations

3. **User-Defined Function**
    - same and SP
    - Can only read documents
    - Can have input parameters
    - Only called within queries
    - Executes on the primaty and secondary

 &emsp;
 <!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Cosmos |
</h2> 

 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--ServerSide Programming-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What are Blobs?~>
</h4>

**Blob Containers** are object-oritented storage, which is good for unstructured data. Theyre assentially data stored inside containers.(Videos,Files,Disk,Photos) and they come in 3 types:

1. Block Blobs
    - General user storage optimized for Text and binary data
    - Made up of blocks of data that can be manage individually
    - Can store up to 4.75TB

2. Append Blobs
     - Like block blobs but better optimized for append operations(loggign type data)
     - Can store up to 4.5TB

3. Page Blobs
     - Used for Rnadom Access files
     - Used for files such as virtual hard drives(VHD FILES)
     - Can store up to 8 TiB

&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What Types Storage Accounts?~>
</h4>

1. **General Purpose v2** - Basic account type for all storage types(blob,file store ,table,queues. Most versatile and recommended type).

2. **General-Purpose v1** - Kegacy account type, essentially the same purpose as v2. This should be used if necesarry, for legacy services.
3. **BlockBobStorage Account**  - Optimized for block and append blobs.Mostly for high transaction rates,large ammounds of small objects, or ciritial low-latency requirements. No support for hot/cool/archive access. Not usable with Page blobs,tables, or queues.

4. **FileStorage** - for creating enterprise premium file shares.Support for file store only.Not blobs
5. **BlobStorage Account**- Legacy account type, only usable with older azure service models.

*Note*: Storage account names must be between 3 & 24 characters can only contain numbers and lowercase letters only. it also must be universally unique.


&emsp;
<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Access tiers~>
</h4>


1. **Hot**  - Best for when frequent Access is required.Cost-Effective transfer rates. However, space used cost more, this is the default tier.

2. **Cool** - best for data that is accessed once every 30 days/ Cost effective space usage but transfer rates bill higher

3. **Archive** - Only available for block blobs best for when data can take large amount of time to retrive and reamain unused for 180+ days. Most cost effective in terms of space, most expensive when retreiving. When archiving theres two types of Priorities:

    - **Standard Priority** - The rehydration request will be processed in the order it was received and may take up to 15 hours.

    - **High Priority** - The rehydration request will be prioritized over standard request and may finish in under 1 hours for objects under 10 GB 
    

*Note*: you can change your tiers . Hot to cold or cold to hot. But with Archive you gotta change it to Hot or coll but it will take a long while.
&emsp;


 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--Blobs-->|
</h4>


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
|  Moving blobs~>
</h4>

``az-copy``

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
|  Blobs Lifecycle~>
</h4>

**Azure Blob Lifecycle**- Enables a irch, rule-based policy for GPv2 & blob storage accounts. Use the policy to transition your data to the apporpriate access tiers or expire at the end of the data's lifecyle. Its only availble for General purpose v2 accounts, blob storage accounts, premium block blobs storage accounts, and azure Data Lake Storage Gen2 Accounts. in addition Lifecycle management policy lets you:

1. Transition blobs from cool to hot imediately if access optimize for performance

2. Transitions blobs, blob versions, and blob snapshots to a cooler storage tier (hot to cool, ot to archive, or cool to archive) f not accessed or modified for a period of time to optimize for cost

3. Delete blobs, blobs versions, and blob snapshots at the end of their lifecyles

4. Define rules to be run once per day at the storage account level

5. Apply rules to containers or subset of blobs
