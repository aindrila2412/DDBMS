##Suggestion slot test 2(DDBMS)

                              
**1.	A distributed database has which of the following advantages over a centralized database?**

A.Software cost
B.Software complexity
C.Slow Response
D.Modular growth

**Ans: d.**

<br/>

**2. Location transparency allows for which of the following?**

A.Users to treat the data as if it is at one location
B.Programmers to treat the data as if it is at one location
C.Managers to treat the data as if it is at one location
D.All of the above.

**Ans: d.**

<br/>


**3.A heterogeneous distributed database is which of the following?**

A. The same DBMS is used at each location and data are not distributed across all nodes.
B. The same DBMS is used at each location and data are distributed across all nodes.
C. A different DBMS is used at each location and data are not distributed across all nodes.
D. A different DBMS is used at each location and data are distributed across all nodes.

**Ans: d.**

<br/>


**4. Which of the following is true concerning a global transaction?**

A. The required data are at one local site and the distributed DBMS routes requests as necessary.
B. The required data are located in at least one nonlocal site and the distributed DBMS routes requests as necessary.
C. The required data are at one local site and the distributed DBMS passes the request to only the local DBMS.
D. The required data are located in at least one nonlocal site and the distributed DBMS passes the request to only the local DBMS.

**Ans: b.**

<br/>


**5. Storing a separate copy of the database at multiple locations is which of the following?**

A. Data Replication
B. Horizontal Partitioning
C. Vertical Partitioning
D. Horizontal and Vertical Partitioning

**Ans: a.**

<br/>


**6. A homogenous distributed database is which of the following?**

A. The same DBMS is used at each location and data are not distributed across all nodes.
B. The same DBMS is used at each location and data are distributed across all nodes.
C. A different DBMS is used at each location and data are not distributed across all nodes.
D. A different DBMS is used at each location and data are distributed across all nodes.

**Ans: b.**

<br/>


**7. Which of the following is not one of the stages in the evolution of distributed DBMS?**

A. Unit of work
B. Remote unit of work
C. Distributed unit of Work
D. Distributed request

**Ans: a.**

<br/>
 

**8. Which of the following is a disadvantage of replication?**

A. Reduced network traffic
B. If the database fails at one site, a copy can be located at another site.
C. Each site must have the same storage capacity.
D. Each transaction may proceed without coordination across the network.

**Ans: c.**

<br/>

**Descriptive :-**

**1.	What are advantages and disadvantages of Distributed DBMS**

**Ans: The distributed database management system contains the data in multiple locations. That can be in different systems in the same place or across different geographical locations.

As shown in the below example −



The database is divided into multiple locations and stores the data in Site1, Site2,Site3 and Site4.

The advantages and disadvantages of Distributed database management systems are as follows −

Advantages of DDBMS

The database is easier to expand as it is already spread across multiple systems and it is not too complicated to add a system.
The distributed database can have the data arranged according to different levels of transparency i.e data with different transparency levels can be stored at different locations.
The database can be stored according to the departmental information in an organisation. In that case, it is easier for a organisational hierarchical access.
there were a natural catastrophe such as fire or an earthquake all the data would not be destroyed it is stored at different locations.
It is cheaper to create a network of systems containing a part of the database. This database can also be easily increased or decreased.
Even if some of the data nodes go offline, the rest of the database can continue its normal functions.

Disadvantages of DDBMS

The distributed database is quite complex and it is difficult to make sure that a user gets a uniform view of the database because it is spread across multiple locations.
This database is more expensive as it is complex and hence, difficult to maintain.
It is difficult to provide security in a distributed database as the database needs to be secured at all the locations it is stored. Moreover, the infrastructure connecting all the nodes in a distributed database also needs to be secured.
It is difficult to maintain data integrity in the distributed database because of its nature. There can also be data redundancy in the database as it is stored at multiple locations.
The distributed database is complicated and it is difficult to find people with the necessary experience who can manage and maintain it.** 

<br/>

**2.	What are the objectives of Distributed Query Processing?**

**Ans: A Query processing in a distributed database management system requires the transmission of data between the computers in a network. A distribution strategy for a query is the ordering of data transmissions and local data processing in a database system. Generally, a query in Distributed DBMS requires data from multiple sites, and this need for data from different sites is called the transmission of data that causes communication costs. Query processing in DBMS is different from query processing in centralized DBMS due to this communication cost of data transfer over the network. The transmission cost is low when sites are connected through high-speed Networks and is quite significant in other networks. 

1. Costs (Transfer of data) of Distributed Query processing :

In Distributed Query processing, the data transfer cost of distributed query processing means the cost of transferring intermediate files to other sites for processing and therefore the cost of transferring the ultimate result files to the location where that result’s required. Let’s say that a user sends a query to site S1, which requires data from its own and also from another site S2. Now, there are three strategies to process this query which are given below:

We can transfer the data from S2 to S1 and then process the query
We can transfer the data from S1 to S2 and then process the query
We can transfer the data from S1 and S2 to S3 and then process the query. So the choice depends on various factors like, the size of relations and the results, the communication cost between different sites, and at which the site result will be utilized.
Commonly, the data transfer cost is calculated in terms of the size of the messages. By using the below formula, we can calculate the data transfer cost:

Data transfer cost = C * Size

Where C refers to the cost per byte of data transferring and Size is the no. of bytes transmitted.

Example: Consider the following table EMPLOYEE and DEPARTMENT.

Site1: EMPLOYEE 

EID	NAME	SALARY	DID
EID- 10 bytes
SALARY- 20 bytes
DID- 10 bytes
Name- 20 bytes
Total records- 1000
Record Size- 60 bytes

Site2: DEPARTMENT

DID	DNAME
DID- 10 bytes
DName- 20 bytes
Total records- 50
Record Size- 30 bytes

Example : Find the name of employees and their department names. Also, find the amount of data transfer to execute this query when the query is submitted to Site 3.

Answer : Considering the query is submitted at site 3 and neither of the two relations that is an EMPLOYEE and the DEPARTMENT not available at site 3. So, to execute this query, we have three strategies:

Transfer both the tables that is EMPLOYEE and DEPARTMENT at SITE 3 then join the tables there. The total cost in this is 1000 * 60 + 50 * 30 = 60,000 + 1500 = 61500 bytes.
Transfer the table EMPLOYEE to SITE 2, join the table at SITE 2 and then transfer the result at SITE 3. The total cost in this is 60 * 1000 + 60 * 1000 = 120000 bytes since we have to transfer 1000 tuples having NAME and DNAME from site 1,
Transfer the table DEPARTMENT to SITE 1, join the table at SITE 2 join the table at site1 and then transfer the result at site3. The total cost is 30 * 50 + 60 * 1000 = 61500 bytes since we have to transfer 1000 tuples having NAME and DNAME from site 1 to site 3 that is 60 bytes each.
 Now, If the Optimisation criteria are to reduce the amount of data transfer, we can choose either 1 or 3 strategies from the above.

2. Using Semi join in Distributed Query processing :

The semi-join operation is used in distributed query processing to reduce the number of tuples in a table before transmitting it to another site. This reduction in the number of tuples reduces the number and the total size of the transmission that ultimately reducing the total cost of data transfer. Let’s say that we have two tables R1, R2 on Site S1, and S2. Now, we will forward the joining column of one table say R1 to the site where the other table say R2 is located. This column is joined with R2 at that site. The decision whether to reduce R1 or R2 can only be made after comparing the advantages of reducing R1 with that of reducing R2. Thus, semi-join is a well-organized solution to reduce the transfer of data in distributed query processing.

Example : Find the amount of data transferred to execute the same query given in the above example using semi-join operation.

Answer : The following strategy can be used to execute the query.

Select all (or Project) the attributes of the EMPLOYEE table at site 1 and then transfer them to site 3. For this, we will transfer NAME, DID(EMPLOYEE) and the size is 25 * 1000 = 25000 bytes.
Transfer the table DEPARTMENT to site 3 and join the projected attributes of EMPLOYEE with this table. The size of the DEPARTMENT table is 25 * 50 = 1250
Applying the above scheme, the amount of data transferred to execute the query will be 25000 + 1250 = 26250 bytes.**

<br/>

**3.	Explain the reference architecture of DDBMS .**

**Ans: Reference Architecture of Distributed DBMSs

Data is distributed system are usually fragmented and replicated.Considering this fragmentation and replication issue

2.The reference architecture of DBMS consist of the following schemas:-

●A set of global external schema.

●A global conceptual schema.

●A fragmentation schema and allocation schema.

●A set of schemas for each local DBMS.

Global external schema- In a distributed system,user applications and user accesseto the distributed database are represented by a number of global external schemas.This is the topmost level in the reference architecture of DBMS.This level describes the part of the distributed database that is relevant to different users.

Global conceptual schema- The GCS represents the logical discription of entire database as if it is not distributed.This level contains definitions of all entities,relationships among entities and security and integrity information of whole databases stored at all sites in a distributed system.

Fragmentation schema and allocation schema- The fragmentation schema describes how the data is to be logically partitioned in a distributed database.The GCS consists of a set of global relations,and the mapping between the global relations and fragments is defined in the fragmentation schema.

The allocation schema is a description of where the data(fragments)are to be located,taking account of any replication.The type of mapping in the allocation schema determined whether the distributed database is redundant or non redundant.In case of redundant data distribution,the mapping is one to many,whereas in case of non redundant data distribution is one to one.

Local schemas- In a distributed database system,the physical data organization at each machine is probably different,and therefore it requires an individual internal schema definition at each site,called local internal schema.

To handle fragmentation and replication issues,the logicalorganization of data at each sites is described by a third layer in the architecture called local conceptual schema.

The GCS is the union of all local conceptual schemas thus the local conceptual schemas are mappings of the global schema onto each site.This mapping is done by local mapping schemas.

This architecture provides a very general conceptual framework for understanding distributed database.**

<br/>

**4.	What are the various concurrency control techniques? Compare Lock based Concurrency Control strategies in detail.**

**Ans: There are three concurrency control techniques which are as follows:

Locking method

Database systems equipped with lock-based protocols use a mechanism by which any transaction cannot read or write data until it acquires an appropriate lock on it. Locks are of two kinds −

• Binary Locks − A lock on a data item can be in two states; it is either locked or unlocked.

• Shared/exclusive − This type of locking mechanism differentiates the locks based on their uses. If a lock is acquired on a data item to perform a write operation, it is an exclusive lock. Allowing more than one transaction to write on the same data item would lead the database into an inconsistent state. Read locks are shared because no data value is being changed.

There are four types of lock protocols available −

i. Simplistic Lock Protocol

Simplistic lock-based protocols allow transactions to obtain a lock on every object before a 'write' operation is performed. Transactions may unlock the data item after completing the ‘write’ operation.

ii. Pre-claiming Lock Protocol

Pre-claiming protocols evaluate their operations and create a list of data items on which they need locks. Before initiating an execution, the transaction requests the system for all the locks it needs beforehand. If all the locks are granted, the transaction executes and releases all the locks when all its operations are over. If all the locks are not granted, the transaction rolls back and waits until all the locks are granted.

enter image description here

iii. Two-Phase Locking 2PL

This locking protocol divides the execution phase of a transaction into three parts. In the first part, when the transaction starts executing, it seeks permission for the locks it requires. The second part is where the transaction acquires all the locks. As soon as the transaction releases its first lock, the third phase starts. In this phase, the transaction cannot demand any new locks; it only releases the acquired locks.

enter image description here

Two-phase locking has two phases, one is growing, where all the locks are being acquired by the transaction; and the second phase is shrinking, where the locks held by the transaction are being released.To claim an exclusive (write) lock, a transaction must first acquire a shared (read) lock and then upgrade it to an exclusive lock.

iv. Strict Two-Phase Locking

The first phase of Strict-2PL is same as 2PL. After acquiring all the locks in the first phase, the transaction continues to execute normally. But in contrast to 2PL, Strict-2PL does not release a lock after using it. Strict-2PL holds all the locks until the commit point and releases all the locks at a time.

enter image description here

Strict-2PL does not have cascading abort as 2PL does.

Timestamp method i. The most commonly used concurrency protocol is the timestamp based protocol. This protocol uses either system time or logical counter as a timestamp.

ii. Lock-based protocols manage the order between the conflicting pairs among transactions at the time of execution, whereas timestamp-based protocols start working as soon as a transaction is created.

iii. Every transaction has a timestamp associated with it, and the ordering is determined by the age of the transaction. A transaction created at 0002 clock time would be older than all other transactions that come after it. For example, any transaction 'y' entering the system at 0004 is two seconds younger and the priority would be given to the older one.

iv. In addition, every data item is given the latest read and write-timestamp. This lets the system know when the last ‘read and write’ operation was performed on the data item.

Optimistic method

i. In optimistic concurrency control techniques, it is assumed that the transactions do not directly update the data items in the database until they finish their execution.

ii. Instead, each transaction maintains local copies of the data items it requires and updates them during execution.

iii. All the data items in the database are updated at the end of the transaction execution. In this technique, each transaction Ti proceeds through three phases, namely, read phase, validation phase, and write phase, depending on whether it is a read-only or an update transaction. The execution of transaction Ti begins with read phase, and the three timestamp values are associated with it during its lifetime. The three phases are explained here.

Read phase: At the start of this phase, transaction Ti is associated with a timestamp Start (Ti). Ti reads the values of data items from the database and these values are then stored in the temporary local copies of the data items kept in the workspace of Ti. All modifications are performed on these temporary local copies of the data items without updating the actual data items of the database.

Validation phase: At the start of this phase, transaction Ti is associated with a timestamp Validation (Ti). The system performs a validation test when Ti decides to commit. This validation test is performed to determine whether the modifications made to the temporary local copies can be copied to the database. In addition, it determines whether there is a possibility of Ti to conflict with any other concurrently executing transaction. In case any conflict exists, Ti is rolled back, its workspace is cleared and Ti is restarted.

Write phase: In this phase, the system copies the modifications made by Ti in its workspace to the database only if it succeeds in the validation phase. At the end of this phase, Ti is associated with a timestamp Finish (Ti).


**

<br/>
**5.	Explain the phases of query processing in distributed database.**

**Ans: Query processing refers to the range of activities involved in extracting data from a database. The activities include translation of queries in high-level database language, into expressions that can be used at the physical levelof the file system, a variety of query-optimization transformations, and actual evaluation of queries. The step involved in processing a query appear in figure below:

enter image description here

1) Parsing and translation.

2) Optimization.

3) Evaluation.

The first action, the system must take in query processing is to translate a given query into its internal form. This translation process is similar to the work performed by the parser of a compiler. In generating the internal form of the query, the parser checks the syntax of the user's query, verifies that the relation names appearing in the query are names of the relations in the database, and so on. The system constructs a parse-tree representation of the query, which it then translates into a relational-algebra expression.

Furthermore, the relational-algebra representation of a query specifies only partially how to evaluate a query. As an illustration, consider the query:

select balance from account where balance < 2500

This query can be translated into either of the following relational-algebra expressions:

• a ',Amer., 2500 (il bita„ce (account)) • n manc• (a Mance < 2500 (account))

To implement the preceding selection, we can search every tuple in account to find tuples with balance less than 2500. If a 13+-tree index is available on the attribute balance, we can use the index instead to locate the tuples. To specify fully how to evaluate a query, we need to provide not only the relational-algebra expression, but also to annotate it with instructions specifying how to evaluate each operation.

A relational-algebra operation annotated with instructions on how to evaluate it is called an evaluation primitive. A sequence balance of primitive operations that can be used to evaluate a query is a query-execution plan or query-evaluation plan. Figure illustrates an evaluation plan for our account example query, in which a particular index (denoted in the figure as "index 1") is specified for the selection operation. The query-execution engine takes a query-evaluation plan, executes that plan, and returns the answers to the query. The different evaluation plans for a give query can have different costs.

enter image description here**

<br/>
**6.	What is horizontal and vertical fragmentation? What are the types of horizontal fragmentation.**

**Ans: Horizontal fragmentation

It refers to the division of a relation into subsets (fragments) of tuples (rows). Each fragment is stored at a different node, and each fragment has unique rows. However, the unique rows all have the same attributes (columns). In short, each fragment represents the equivalent of a SELECT statement, with the WHERE clause on a single attribute.

Vertical fragmentation

It refers to the division of a relation into attribute (column) subsets. Each subset (fragment) is stored at a different node, and each fragment has unique columns—with the exception of the key column, which is common to all fragments.

Types of horizontal fragmentation

i. Primary Horizontal Fragmentation

It is the fragmentation of primary relation

e.g. Employee table is fragmented for Department No.

ii. Derived Horizontal Fragmentation

Fragmentation of the secondary relations that are dependent on the primary relation; related with foreign keys.**

<br/>
**7.	Explain the characteristics of distributed transaction management system & its goals.**

**Ans: Distributed Systems is an upcoming area in computer science and has the ability to have a large impact on the many aspects in  the medical, scientific, financial and commercial sector.

The most commonly used definition for a distributed system is, a system comprised of geographically dispersed computing components interacting on a hardware or software level. The rise in interest for distributed computing can be attributed to two major factors. The first factor is the creation and advancements in local and wide area networks which allow for large amounts of data to be transmitted over great distances in a short period of time.

The second factor is the new craze of the Internet of Things (IoT), where nearly every physical device manufacture having some sort of internet connectivity allowing for the possibility of tens of billions of devices that are able to interact. This large network of interconnected devices can be utilized to compute large amounts of data in a fraction of the time it would currently take to process.


The four important goals that should be met for an efficient distributed system are as follows:

1. Connecting Users and Resources:

The main goal of a distributed system is to make it easy for users to acces remote resourses and to share them with others in a controlled way.
It is cheaper to le a printer be shared by several users than buying and maintaining printers for each user.
Collaborating and exchanging information can be made easier by connecting users and resource.
2. Transparency:

It is important for a distributed system to hide the location of its process and resource. A distributed system that can portray itself as a single system is said to be transparent.
The various transparencies need to be considered are access, location, migration, relocation, replication, concurrency, failure and persistence.
Aiming for distributed transparency should be considered along with performance issues.
3. Openness:

Openness is an important goal of distributed system in which it offers services according to standard rules that describe the syntax and semantics of those services.
Open distributed system must be flexible making it easy to configure and add new components without affecting existing components.
An open distributed system must also be extensible.
4. Scalable:

Scalability is one of the most important goals which are measured along three different dimensions.
First, a system can be scalable with respect to its size which can add more user and resources to a system.
Second, users and resources can be geographically apart.
Third, it is possible to manage even if many administrative organizations are spanned.**

<br/>

**8.	What problem can occur in a distributed system due to the failure of link and partitioning of the network? What are the ways by which recovery can take place?**

**Ans: DSM implements distributed systems shared memory model in an exceedingly distributed system, that hasn’t any physically shared memory. The shared model provides a virtual address space shared between any numbers of nodes. The DSM system hides the remote communication mechanism from the appliance author, protecting the programming ease and quality typical of shared-memory systems.



These are explained as following below.

1. Method failure :
In this type of failure, the distributed system is generally halted and unable to perform the execution. Sometimes it leads to ending up the execution resulting in an associate incorrect outcome. Method failure causes the system state to deviate from specifications, and also method might fail to progress.

Behavior –
It may be understood as if incorrect computation like Protection violation, deadlocks, timeout, user input, etc is performed then the method stops its execution.
Recovery –
Method failure can be prevented by aborting the method or restarting it from its prior state.
2. System failure :
In system failure, the processor associated with the distributed system fails to perform the execution. This is caused by computer code errors and hardware issues. Hardware issues may involve CPU/memory/bus failure. This is assumed that whenever the system stops its execution due to some fault then the interior state is lost.

Behavior –
It is concerned with physical and logical units of the processor. The system may freeze, reboot and also it does not perform any functioning leading it to go in an idle state.
Recovery –
This can be cured by rebooting the system as soon as possible and configuring the failure point and wrong state.
3. Secondary storage device failure :
A storage device failure is claimed to have occurred once the keep information can’t be accessed. This failure is sometimes caused by parity error, head crash, or dirt particles settled on the medium.

Behavior –
Stored information can’t be accessed.
Errors inflicting failure –
Parity error, head crash, etc.
Recovery/Design strategies –
Reconstruct content from the archive and the log of activities and style reflected disk system. A system failure will additionally be classified as follows.
Associate cognitive state failure
A partial cognitive state failure
a disruption failure
A halting failure
4. Communication medium failure :
A communication medium failure happens once a web site cannot communicate with another operational site within the network. it’s typically caused by the failure of the shift nodes and/or the links of the human activity system.

Behavior –
A web site cannot communicate with another operational site.
Errors/Faults –
Failure of shift nodes or communication links.
Recovery/Design strategies –
Reroute, error-resistant communication protocols.**

<br/>
