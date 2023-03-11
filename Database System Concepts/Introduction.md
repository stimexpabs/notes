- A DBMS is a collection of data and programs to access that data.
- The database contains information relevant to an enterprise.
- The primary goal of a DBMS is to store and retrieve database information conveniently and efficiently.
- Database systems are designed to manage large bodies of information.
- Management of data involves defining structures for storage and providing mechanisms for manipulation.
- The system must ensure the safety of the information stored and avoid anomalous results if data are shared among several users.

# 1.1 Database-System Applications
-   Database systems manage collections of valuable, large, and multi-user accessed data.
-   The earliest database applications were simple compared to modern applications.
-   Modern applications include highly sophisticated, worldwide enterprises.
-   All database applications share important common elements and have data as their central aspect.
-   Database applications today include data with complex relationships and a more variable structure.
-   Modern database systems exploit commonalities in the structure of data to gain efficiency, but also allow for weakly structured data and for data whose formats are highly variable.
-   A database system is a large, complex software system whose task is to manage a large, complex collection of data.
-   Abstraction allows a person to use a complex device or system without having to know the details of how that device or system is constructed.
-   Representative applications of database systems are in **enterprise information, manufacturing, banking and finance, universities, airlines, telecommunication, web-based services, document databases, and navigation systems**.
-   Databases form an essential part of every enterprise and a large part of a person’s daily activities.


# 1.2 Purpose of Database Systems

-   The purpose of database systems is to manage data efficiently and provide easy access to it.
-   Storing data in operating system files leads to data redundancy and inconsistency, difficulty in accessing data, data isolation, integrity problems, atomicity problems, and concurrent-access anomalies.
-   Different programmers creating files and application programs may lead to different structures and programming languages.
-   Redundancy leads to higher storage and access costs, and it may lead to data inconsistency.
-   Difficulty in accessing data arises when there is no application program available to retrieve needed data.
-   Data isolation makes it difficult to retrieve appropriate data because it is scattered in various files and may be in different formats.
-   Integrity problems occur when the data values stored in the database must satisfy certain consistency constraints.
-   Atomicity problems occur when a computer system is subject to failure.
-   Concurrent access can cause inconsistencies in data when multiple users update data simultaneously.
-   Examples of concurrent access anomalies include multiple clerks debiting a bank account at the same time, or multiple students registering for a course simultaneously.
-   Maintaining supervision is necessary to prevent concurrent access anomalies, but it is difficult to provide when data is accessed by many different application programs that have not been coordinated previously.
-   Security problems can arise when not every user of the database system should be able to access all the data.
-   Enforcing security constraints is difficult when application programs are added to the file-processing system in an ad hoc manner.
-   Database systems were developed to solve the problems with file-processing systems and enable secure data processing.

# 1.3 View of Data

A database system is a collection of interrelated data and a set of programs that allow users to access and modify these data.
## 1.3.1 Data Models
Underlying the structure of a database is the data model: a collection of conceptual tools for describing data, data relationships, data semantics, and consistency constraints.
1. **Relational Model**: 
	- The relational model represents data and relationships using tables.
	-   Tables have multiple columns with unique names and are also known as relations.
	-   The relational model is a record-based model that structures the database in fixed-format records of several types.
	-   Each table contains records of a particular type that defines a fixed number of fields or attributes.
	-   The columns of the table correspond to the attributes of the record type.
	-   The relational data model is widely used, and most current database systems are based on it.

2. **Entity-Relationship Model**:
	-   The E-R data model uses entities and relationships among them.
	-   Entities are distinguishable objects in the real world.
	-   The E-R model is popular in database design.

3. **Semi-structured Data Model**:
	-   The semi-structured data model allows for data where items of the same type can have different sets of attributes.
	-   This is different from other data models where every item of a particular type must have the same attributes.
	-   JSON and XML are popular examples of semi-structured data representations.

4. Object-Based Data Model:
	-   Object-oriented programming (OOP) has become the dominant software development methodology
	-   This led to the development of an object-oriented data model
	-   Today, the concept of objects is well integrated into relational databases
	-   Standards exist to store objects in relational tables
	-   Database systems allow procedures to be stored in the database system and executed by the database system
	-   This extends the relational model with notions of encapsulation, methods, and object identity

## 1.3.2 Relational Data Model
