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

emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--COSMO DBs-->|
</h4>