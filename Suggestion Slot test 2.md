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

**3.	Explain the reference architecture of DDMS .**

**Ans: **

<br/>

**4.	What are the various concurrency control techniques? Compare Lock based Concurrency Control strategies in detail.**

**Ans:**

<br/>
**5.	Explain the phases of query processing in distributed database.**

**Ans:**

<br/>
**6.	What is horizontal and vertical fragmentation? What are the types of horizontal fragmentation.**

**Ans:**

<br/>
**7.	Explain the characteristics of distributed transaction management system & its goals.**

**Ans:**

<br/>

**8.	What problem can occur in a distributed system due to the failure of link and partitioning of the network? What are the ways by which recovery can take place?**

**Ans:**

<br/>
