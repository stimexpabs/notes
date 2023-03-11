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
	creates the department table with three columns: dept name, building, and budget,
	each of which has a specific data type associated with it.

- The SQL DDL also supports a number of types of integrity constraints. For example, one can specify that the dept name attribute value is a primary key, ensuring that no two departments can have the same department name. As another example, one can specify that the dept name attribute value appearing in any instructor record must also appear in the dept name attribute of some record of the department table.

## 1.4.3 Data-Manipulation Language







