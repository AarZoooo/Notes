# UNIT 1

## Introduction

### Database

A collection of structured data. This structuring makes the data easily accessible, thus making tasks like storing, retreiving and manipulating data easy.

### Database Management System (DBMS)

A software that facilitates usage of a database. This acts as an interface between the user and the database stored directly in storage.

**Advantages:**

- Allows changing aspects or data of a database without affecting applications using the data
- Provides mechanisms to control access to the data and maintain data integrity
- Allows consistency of data accross the database

**Disadvantages:**

- Implementation and Maintenance of a database can be expensive
- DBMS can be complex to implement, thus demanding specialised skills

### ANSI-SPARC Architecture

This defines a three-level framework for database systems. They are:

- **External Level:** Consists of how users view the data
- **Conceptual Level:** Consists of a logical view of the entire database
- **Internal Level:** Consists of how data of a database is physically stored in the storage devices

### Data Independence

This means that changes made to a database should not affect access or manipulation to the database by other applications at a higher level.

**1. Logical Data Independence:** It allows changes in the conceptual level of a database, without affecting the application programs accessing it.

**2. Physical Data Independence:** It allows changes in the internal level of a database without affecting the conceptual and external level.

### Database Administrator (DBA)

This is a person of a group of people responsible for design, implementation, maintenance and repair of an organisation's database.

**Responsibilities of DBA:**

- Designing database
- Implementing Security measures
- Implementing Data backup and recovery measures
- Monitoring performance and tuning
- Managing user accounts, permissions and privileges
- Maintaining data through consistency, accuracy and integrity of data

</br>

## Relational Database structure

In this method, data is stored in **Tables** (relations). Tables have **Rows** (tuples) and **Columns** (attributes). Each row represents a record, and each column represents an attribute of a record.

### Keys

Keys are attributes or a set of attributes (basically columns) that identify each row within a table. Keys can be one of these three types:

- **Candidate Key:** This is a basic key in a table. There can be multiple candidate keys in a table. Example: Name, Address, Phone number, Date of Birth etc.
- **Primary Key:** A candidate key that does not allow duplicate values. A primary key in a table is used to uniquely identify each record in the table. Example: Employee ID, Student ID etc.
- **Foreign Key:** A candidate key in a table that is the primary key in some other table. These two keys in two different tables with same data establish a relationship between the two tables. Example: Student ID as primary key in student table, and as foreign key in Library Book Issue table.

### Relations

A relation is a table consisting of data. Relations consist of columns and rows where data is stored. Example: Student table, Employee table etc.

### Attributes

Attributes are columns in a relation. They represent each characteristic of the data stored in the relation. Example: Name, Age, Date of Birth etc.

### Schema

It defines the skeleton structure of a relational database. In other words, it includes the tables, their attributes, relationships, and constriants of a database. It basically provides a blueprint for creating and managing a database.

### Instances

These refer to the actual data stored in a database at a point of time.They are represented as rows and columns with the actual data.

### Referential Integrity

It ensures the integrity or consistency of data between related tables. For example, when a foreign key of a table represents the primary key of another table, Referential integrity ensures that every value in the foreign key corresponds to some value in the primary key. This prohibits irregular data manipulation such as inserting a record without proper foreign key etc.

### Entity Integrity

It ensures that each record (row) in a table is uniquely identified by some attribute (column) in the table. In other words, there must be a Primary key in a table which uniquely identifies every record in it.

---

### Relational Model

A database model based on the mathematical concept of Relations.

- Introduced by Edgar F. Codd in 1970
- Most widely used database model

In this model, data is organized in into tables (relations), where each table consists of rows and columns. 

### Network Model

An older database model that represents data as a collection of records connected by links.

- Developed in late 1960s and early 1970s
- An improvement over the Hierarchical model

In this model, data is organised into a graph-like structure, where records (nodes) are connected by pointers (edges) to form a network.

### Hierarchical Model

A database model in which data is stored in tree-like structure with a root. It consists of parent-child relationship.

- Each record is a node
- A Child node can have only one parent
- A Parent node can have multiple children
- Traversal in this node is done using Navigation methods

## ER Model

A conceptual data model used to describe the data and its relationships in a database system.

- Introduced by Peter Chen in 1976
- Allows visualisation and representation of the structure of a database system

In this model, entities or tables are represented as **objects** (rectangles), attributes are represented as **Ovals**, and relationships between entities are represented by **Lines** connecting them.

<img src = "https://www.simplilearn.com/ice9/free_resources_article_thumb/ERDiagramsInDBMS_1.png" height = 400></img>

**Challenges:**

- Representing complex relationships can be challenging
- Representing certain aspects of the real-world domain can lead to Ambiguity
- Limited Semantics for specifying constraints and behaviour
- Overhead in case of creating and maintaining ER Diagram for large and complex databases

### Mapping Constraints

It contains the rules or conditions that are followed in the mapping of conceptual schema (ER Diagram) and the logical schema (Relational Schema) of a database. These ensure that the keys, attributes and relationships in the ER Diagram can be effectively mapped to Columns, Rows and Tables of the Relational Dataset.

**Examples:**

- **Entity-Attribute mapping:** Each entity should correspond to a table, and each attribute should correspond to a column in the relational database.
- **Relationship mapping:** Each relationship in the ER diagram should be represented by Foreign Key relationships between corresponding tables.
- **Cardinality constraints:** Cardinality ratios mentioned in the ER Diagram (such as **one-to-one**, **one-to-many** etc.) should be reflected in the design of the Relational Schema.

## Relational Algebra

It is a **procedural query language** used to perform operations in a relational database. Basically it focusses on how to obtain a desired result from a database.

### Syntax

- `σ` **(Selection)** : Selects records from a relation that satisfy the given condition

- `π` **(Projection)** : Selects a subset of attributes from a relation

- `∪` **(Union)** : Combines records from two relations, removing duplicates

- `∩` **(Intersection)** : Retrieves only common records from two relations

- `-` **(Difference)** : Retrieves records from a relation that don't exist in another relation

- `×` **(Cartesian Product)** : Combines records from two relations and creates a new relation with all possible combinations

- `⋈` **(Join)** : Combines records from two relations based on a common attribute

  - `⨝` **(Inner Join)** : Combines records from two relations only when the condition is fulfilled in both relations

  - `⟕` **(Left Join)** : Combines records from two relations based on a condition, but also includes all records from left relation even if they don't have matching values with the right relation. In that case **NULL** will be used to fill the gap

  - `⟖` **(Right Join)** : Combines records from two relations based on a condition, but also includes all records from right relation even if they don't have matching values with the left relation. In that case **NULL** will be used to fill the gap

  - `⟗` **(Outer Join)** : Combines records from two relations based on a condition, but also includes all records from both relations if condition is not satisfied. In that case **NULL** is used to fill the gap.

### Properties

- Each operation in Relational Algebra produces a new relation, which can be used as an input to other operations
- Operations are performed sequentially, meaning than the output of one serves as an input to the next one
- The result of multiple subsequent operations is also a relation

### Example

Consider two relations:

    Students (StudentID, Name, Age)
    Courses (CourseID, Title)

    Enrollment(StudentID, CourseID)


To retrieve the names of students who have enrolled in a specific course, let's say the course with ID "C001", using Relational Algebra:

> **Result = π<sub>Name</sub> (σ<sub>StudentID=Enrollment.StudentID ∧ CourseID='C001'</sub> (Students ⨝ Enrollment))**

</br>

## Relational Calculus

Unlike Relational Algebra, Relational Calculus is a **non-procedural query language** used to specify the desired result from a database without specifying the sequence of operations to retrieve it. Basically, it focusses on what to expect, rather than how to obtain it.

**1. Tuple Calculus:** The result is in the form of a set of tuples

**2. Domain Calculus:** The result is in the form of a set of values for attributes

Relational Calculus uses mathematical logic (e.g. `∀` for **"for all"** and `∃` for **"there exists"**)

### Example

Consider the same two relations:

    Students (StudentID, Name, Age)
    Courses (CourseID, Title)

**1. Tuple Calculus:** To retrieve the names of students who are older than 20:

> **{ s.Name | ∃ s ∈ Students (s.Age > 20) }**

**2. Domain Calculus:** To retrieve the titles of courses:

> **{ Title |< Title > ? Courses }**

</br>

## Grouping and Ungrouping Operators

Grouping allows for the aggregation of data based on specific attributes. Aggregate functions compute summary statistics like sum, average, count etc. on grouped data.

Ungrouping operators reverse the grouping process, returning its data to its original format.

### Examples

Consider a relation containing sales data:

    Sales(ProductID, SalesDate, Amount)

To compute the total sales amount for each product:

> TotalSalesByProduct = π<sub>ProductID, SUM(Amount)</sub>(GroupBy<sub>ProductID</sub>(Sales))

To return the total sales amount for each product to the original format:

> OriginalSales = Ungroup(TotalSalesByProduct)

</br>

# UNIT 2

## Normalization

The process of analyzing the relations, their attributes, keys and functional dependencies among them.

- Reduces redundancy among relations
- Makes relations more effective and operational
- Reduces insertion, deletion and update anomalies

### Functional Dependency

The association between two or more attributes in a relation.

    A ---> B

Here,

- A = Determinant relation
- B = Determined relation

Thus,

- A is functionally determining B, or
- B is functionally determined by A, or
- B is functionally dependent on A
- For same value of A, there is same value of B

e.g.

    1)  A  |  B     2)  A  |  B
        ---+---         ---+--- 
        1  |  3         1  |  2
        2  |  7         2  |  4
        3  |  9         3  |  6
        4  |  5         2  |  3
        6  |  2         4  |  5
        3  |  9         6  |  9

In 1<sup>st</sup> example: A --> B, whereas in 2<sup>nd</sup> example: A not --> B.