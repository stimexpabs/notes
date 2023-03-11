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
	-   This is different from other data models, where every item of a particular type must have the same attributes.
	-   JSON and XML are popular examples of semi-structured data representations.

4. **Object-Based Data Model**:
	-   Object-oriented programming (OOP) has become the dominant software development methodology
	- This led to the development of an object-oriented data model
	-   Today, the concept of objects is well integrated into relational databases
	-   Standards exist to store objects in relational tables
	-   Database systems allow procedures to be stored in the database system and executed by the database system
	-   This extends the relational model with notions of encapsulation, methods, and object identity

## 1.3.2 Relational Data Model
In the relational model, data are represented in the form of tables. Each table has multiple columns, and each column has a unique name. Each row of the table represents one piece of information.

## 1.3.3 Data Abstraction
Since many database-system users are not computer trained, developers hide the complexity from users through several levels of data abstraction, to simplify users’ interactions with the system:

![ThreeLevelsofDataAbstractions](https://raw.githubusercontent.com/stimexpabs/notes/496ffd4daccf529b7941f4143edacaf4f6d4f4be/Database%20System%20Concepts/atcmts/ThreeLevelsofDataAbstractions.png)

- **Physical Level**:
	The lowest level of abstraction describes how the data are actually stored, it describes complex low-level data structures in detail.
- **Logical Level**:
	-   Logical level is the next-higher level of abstraction in database design.
	-   It describes what data are stored in the database and their relationships.
	-   The logical level uses a small number of relatively simple structures to represent the entire database.
	-   Complex physical-level structures may be used to implement the logical level, but the user of the logical level does not need to be aware of this complexity.
	-   This is referred to as physical data independence.
	-   Database administrators use the logical level of abstraction to decide what information to keep in the database.
- **View Level**:
	The highest level of database abstraction is the view level, which describes only a part of the entire database. This level exists to simplify user interaction with the system, as many users only need to access a specific part of the database. The system may provide multiple views for the same database.
	
The database system allows application developers to store and retrieve data using the abstractions of the data model, and converts the abstract operations into operations on the low-level implementation
## 1.3.4 Instances and Schemas

-   A database consists of a schema and one or more instances.
-   The schema defines the overall structure of the database, while instances contain the actual data at a given moment.
-   The physical schema describes the physical design of the database, while the logical schema describes its logical structure.
-   Applications typically use the logical schema, which can be changed without affecting them, providing physical data independence.
-   Poorly designed schemas can cause problems, such as unnecessarily duplicating information.
-   Newer database applications often require more flexible logical schemas, allowing for variations in attribute values within a relation.

# 1.4 Database Languages
-   A database system provides a data-definition language (DDL) to specify the database schema and a data-manipulation language (DML) to express database queries and updates.
-   In practice, DDL and DML are parts of a single database language, such as SQL.
-   Almost all relational database systems use the SQL language.
## 1.4.1 Data-Definition Language
- We specify a database schema by a set of definitions expressed by a special language called a data-definition language (DDL). The DDL is also used to specify additional properties of the data.
- We specify the storage structure and access methods used by the database system by a set of statements in a special type of DDL called a data storage and definition language. These statements define the implementation details of the database schemas, which are usually hidden from the users.
- The data values stored in the database must satisfy certain consistency constraints.
- Constraints that can be tested with minimal overhead include:
	- **Domain Constraints**: A domain of possible values must be associated with every attribute.
	- **Referential Integrity**: A value that appears in one relation for a given set of attributes must also appear in a certain set of attributes in another relation.
	- **Authorization**: We may want to differentiate among the users as far as the type of access they are permitted to various data values in the database. **read authorization**, which allows reading, but not modification, of data; **insert authorization**, which allows insertion of new data, but not modification of existing data; **update authorization**, which allows modification, but not deletion, of data; and **delete authorization**, which allows deletion of data. We may assign the user all, none, or **a combination of these types of authorization**.
- The processing of DDL statements generates output that is placed in the data dictionary, which contains metadata about the data. The data dictionary is a special type of table that can be accessed and updated only by the database system itself.
## 1.4.2 The SQL Data-Definition Language
- the following **SQL DDL** statement defines the department table:
```SQL
CREATE TABLE department (
	dept_name    char(20),
	bulding      char(15),
	budget       numeric(12,2)
	);
```
creates the department table with three columns: dept name, building, and budget, each of which has a specific data type associated with it.

- The SQL DDL also supports a number of types of integrity constraints. For example, one can specify that the dept name attribute value is a primary key, ensuring that no two departments can have the same department name. As another example, one can specify that the dept name attribute value appearing in any instructor record must also appear in the dept name attribute of some record of the department table.

## 1.4.3 Data-Manipulation Language

- A data-manipulation language (DML) is a language that enables users to access or manipulate data as organized by the appropriate data model. The types of access are:
	- Retrieval of information stored in the database.
	- Insertion of new information into the database.
	- Deletion of information from the database.
	- Modification of information stored in the database.
- There are basically two types of data-manipulation language:
	- **Procedural DMLs** require a user to specify what data are needed and how to get those data.
	- **Declarative DMLs** (also referred to as **nonprocedural DMLs**) require a user to specify what data are needed without specifying how to get those data.
- Declarative DMLs are usually easier to learn and use than are procedural DMLs. However, since a user does not have to specify how to get the data, the database system has to figure out an efficient means of accessing data.
- A query is a statement requesting the retrieval of information. The portion of a DML that involves information retrieval is called a query language. Although technically incorrect, it is common practice to use the terms query language and data-manipulation language synonymously.
- The levels of abstraction that we discussed in Section 1.3 apply not only to defining or structuring data, but also to manipulating data. At the physical level, we must define algorithms that allow efficient access to data. At higher levels of abstraction, we emphasize ease of use. The goal is to allow humans to interact efficiently with the system.
- The query processor component of the database system (which we study in Chapter 15 and Chapter 16) translates DML queries into sequences of actions at the physical level of the database system.

## 1.4.4 The SQL Data-Manipulation Language
- The SQL query language is nonprocedural
- A query takes as input several tables (possibly only one) and always returns a single table
- an SQL query that finds the names of all instructors in the History department:
```SQL
	SELECT instructor.name
	FROM instructor
	WHERE instructor.dept_name = 'history';
```
The query specifies that those rows from the table instructor where the dept name is History must be retrieved,and the name attribute of these rows must be displayed. The result of executing this query is a table with a single column labelled name and a set of rows, each of which contains the name of an instructor whose dept name is History.

## 1.4.5 Database Access from Application Programs
The SQL language is not as powerful as a universal Turing machine and lacks the ability to perform certain computations and actions such as input/output and network communication. To overcome this limitation, application programs are used that interact with the database by embedding SQL queries in a host language such as C/C++, Java, or Python. These programs are used for various tasks, such as registering for courses, generating class rosters, calculating student GPA, and generating payroll checks. To execute DML statements, they are sent from the host to the database using an application program interface such as ODBC for C and JDBC for Java.
# 1.5 Database Design
- Database systems are essential for managing large amounts of data that are part of an enterprise's operations. The design of a complete database application environment involves several factors, including the database schema, the enterprise's needs, and the end product. In database design, the primary focus is on designing the schema to meet the enterprise's data requirements. A high-level data model provides a conceptual framework for specifying the data requirements and how the database will be structured to fulfill them.

- The initial phase of database design involves characterizing the data needs of the prospective users and developing a specification of user requirements. The next step is to choose a data model and translate the user requirements into a conceptual schema. The conceptual schema provides a detailed overview of the enterprise and includes a review of the schema to ensure that all data requirements are satisfied and that there are no conflicts. In terms of the relational model, the designer decides which attributes to capture in the database and how to group them to form tables. This process can be done using the entity-relationship model or normalization algorithms.

- A fully developed conceptual schema indicates the functional requirements of the enterprise, and users describe the kinds of operations or transactions that will be performed on the data. In the logical-design phase, the designer maps the high-level conceptual schema onto the implementation data model of the database system that will be used. In the subsequent physical-design phase, the designer specifies the physical features of the database, including the form of file organization and internal storage structures.

# 1.6 Database Engine
- A database engine is a software system designed to manage and manipulate data in a database. The functional components of a database engine can be broadly divided into three categories: the storage manager, the query processor components, and the transaction management component.
## 1.6.1 Storage manager
- The storage manager is responsible for storing, retrieving, and updating data in the database. It provides an interface between the low-level data stored in the database and the application programs and queries submitted to the system. The components of the storage manager include an authorization and integrity manager, a transaction manager, a file manager, and a buffer manager.
	- **Authorization and integrity manager**, which tests for the satisfaction of integrity constraints and checks the authority of users to access data.
	- **Transaction manager**, which ensures that the database remains in a consistent (correct) state despite system failures, and that concurrent transaction executions proceed without conflicts.
	- **File manager**, which manages the allocation of space on disk storage and the data structures used to represent information stored on disk.
	- **Buffer manager**, which is responsible for fetching data from disk storage into main memory, and deciding what data to cache in main memory. The buffer manager is a critical part of the database system, since it enables the database to handle data sizes that are much larger than the size of main memory.
- The storage manager implements several data structures as part of the physical system implementation:
	- **Data files**, which store the database itself.
	- **Data dictionary**, which stores metadata about the structure of the database, in particular the schema of the database.
	- **Indices**, which can provide fast access to data items. Like the index in this textbook, a database index provides pointers to those data items that hold a particular value. For example, we could use an index to find the instructor record with a particular ID, or all instructor records with a particular name.
## 1.6.2 The Query Processor
- The query processor components include:
	- **DDL interpreter**, which interprets DDL statements and records the definitions in the data dictionary.
	- **DML compiler**, which translates DML statements in a query language into an evaluation plan consisting of low-level instructions that the query-evaluation engine understands. 
	
		A query can usually be translated into any of a number of alternative evaluation plans that all give the same result. The DML compiler also performs **query optimization**; that is, it picks the lowest cost evaluation plan from among the alternatives.
	- **Query evaluation engine**, which executes low-level instructions generated by the DML compiler.
## 1.6.3 Transaction Management
The transaction management component allows application developers to treat a sequence of database accesses as if they were a single unit that either happens in its entirety or not at all. It ensures that the database remains in a consistent (correct) state despite system failures, and that concurrent transaction executions proceed without conflicts. The components of the transaction management component include the transaction manager and the concurrency control manager.



