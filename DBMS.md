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

## Keys in Databases

The keys in the database play a vital role in identifying the data present in it. Using keys, you can find any data from the table quickly and easily. The large tables are divided into smaller ones, and keys are used to connect the smaller tables.

### Types of Keys

- Primary Key
- Candidate Key
- Super Key
- Alternate Key
- Foreign Key
- Partial Key
- Composite Key

---

### Primary Key

The primary key is an attribute of the table that identifies any row or tuple uniquely. You must choose the primary key that will uniquely find any data from the table. 

**Example**

Consider a relation `Employee`. It has attributes like `Emp_ID`, `Emp_Name`, `Emp_Add`, `Passport_Number`, and `License_Number`.

The primary key of the `Employee` relation will be the **`Emp_ID`**, as it will uniquely identify every employee’s data. Additionally, the `Passport_Number` and `License_Number` can also serve as primary keys as they are unique for every employee.

### Candidate Key

The candidate key of any table is a set of minimal attributes and can uniquely identify any row in the relation. There can be single or more candidate keys for a single relation. 

**Example**

Consider the above relation of `Employee`. We saw that the primary key is the `Emp_ID`, which is unique and non-repetitive for every employee. The other two attributes, `Passport_Number` and `License_Number`, are also non-repetitive. So, they both can serve as candidate keys.

### Super Key

As the primary key and candidate key identifies every tuple uniquely, the **super key** also helps find the table’s unique tuple. The candidate key is the subset of the super key. There can be one or many super keys.

**Example**

We can use the same Employee relation to have a clear idea about the super key. The `Emp_ID` attribute can uniquely find out any employee’s data. The `Emp_Name` attribute cannot be used as the primary key, as two employees can have the same name. But, the combination of the `Emp_ID` and `Emp_Name` can find employee’s data uniquely. So, `(Epm_ID, Emp_Name)` serves as super keys for the Employee relation.

The `Passport_Number` and `License_Number` are also super keys of the Employee relation.

### Alternate Key

**Candidate keys** that are left unimplemented or unused after implementing the primary key are called as alternate keys.

### Foreign Key

The foreign key is quite different from the above three keys. It is used to establish a connection between two relations. Consider two relations `A` and `B`. Suppose any attribute in the relation `A` is the **primary key** of the relation B; that attribute is referred to as the **foreign key**.

**Example**

We shall look at the simple example to understand the foreign key concept. Let us take the example of employees in the company. Every employee is assigned to different departments. Hence, we use two relations, `Employee` and `Department`. 

We define Employee relations as:

    Employee (Emp_ID, Emp_Name, Passport_Number, License_Number, Dept_ID)

and Department relation as:

    Department (Dept_ID, Dept_Name). 

In the `Employee` relation, `Emp_ID` is the primary key, whereas `Dept_ID` is the `Department` relation’s primary key. The attribute `Dept_Id` is one attribute in the `Employee` relation, which is the primary key in the `Department` relation. Hence, the `Dept_ID` serves as the foreign key in the `Employee` relation.

### Partial Key

Partial key is a key using which all the records of the table can not be identified uniquely. However, a bunch of related tuples can be selected from the table using the partial key.

**Example**

Consider the following schema:

<table>
<tr>
<th>Emp_no</td>
<th>Dependent_name</td>
<th>Relation</td>
</tr>
<tr>
<td>E1</td>
<td>Suman</td>
<td>Mother</td>
</tr>
<tr>
<td>E1</td>
<td>Ajay</td>
<td>Father</td>
</tr>
<tr>
<td>E2</td>
<td>Vijay</td>
<td>Father</td>
</tr>
<tr>
<td>E2</td>
<td>Ankush</td>
<td>Son</td>
</tr>
</table>


Here, using partial key `Emp_no`, we can not identify a tuple uniquely but we can select a bunch of tuples from the table.

### Composite Key

A composite key is a group of attributes that uniquely finds every employee’s data from the relation. The composite key is the combination of two or more than two attributes.  

**Example**

From the above `Employee` relation:

    Emp (Emp_ID, Emp_Name, Passport_Number, License_Number)
    
the composite key is `(Emp_name, Emp_ID)`.

<br>

## Normalization

The process of analyzing the relations, their attributes, keys and functional dependencies among them.

- Reduces redundancy among relations
- Makes relations more effective and operational
- Reduces insertion, deletion and update anomalies

### Types of Normalization

- First Normal Form (1NF)
- Second Normal Form (2NF)
- Third Normal Form (3NF)
- Boyce-Codd Normal Form (BCNF)
- Fourth Normal Form (4NF)
- Fifth Normal Form (5NF)

## Functional Dependency

A relationship between attributes of a table dependent on each other. For example, if:

    A -> B

Then,

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

In 1<sup>st</sup> example: `A -> B`, whereas in 2<sup>nd</sup> example: `A not -> B` (For same value of A, B should be same).

### Advantages

- Functional Dependency avoids data redundancy. Therefore same data do not repeat at multiple locations in that database
- It helps you to maintain the quality of data in the database
- It helps you to define meanings and constraints of databases
- It helps you to identify bad designs
- It helps you to find the facts regarding the database design

### Fully Functional Dependency

If `X` and `Y` are an attribute set of a relation and `X -> Y`, then Y is functionally dependent on X but not on any proper subset of X.

**Example:** In the relation `ABC -> D`, attribute `D` is fully functionally dependent on ABC and not on any proper subset of `ABC`. That means that subsets of `ABC` like `AB`, `BC`, `A`, `B`, etc cannot determine `D`.

### Partial Functional Dependency

A functional dependency `X -> Y` is a partial dependency if `Y` is functionally dependent on `X` and `Y` can be determined by any proper subset of `X`.

**Example:** We have a relationship  `AC -> B`, `A -> D`, and `D -> B`. Here `A` is alone capable of determining `B`, which means `B` is partially dependent on `AC`.

### Transitive Functional Dependency

Suppose:
- `A -> B`, `B not -> A`
- `B -> C`

Therefore, we can say:
- `A -> C`

For example:

    Book | Author | Age
    -----+--------+----
     B1  |   A1   | 79
     B2  |   A2   | 56
     B3  |   A3   | 56
     B4  |   A4   | 43
 
In this relation:
- `Book -> Author`
- `Author not -> Book`
- `Author -> Age`

Therefore,
- `Book -> Age`

### Join Dependency

A table has a JD if it can be recreated by joining multiple related tables that each have fewer columns and contain a subset of the original table's attributes.

<img src = "https://www.scaler.com/topics/images/join-dependency-in-dbms-thumbnail.webp">

### Multi-valued Dependency

Multivalued dependency (MVD) deals with complex attribute relationships in which an attribute may have many independent values while yet depending on another attribute or group of attributes. It improves database structure and consistency and is essential for data integrity and database normalization.

MVD or multivalued dependency means that for a single value of attribute `A` multiple values of attribute `B` exist. We write it as:

    A -> -> B

## Normal Forms

### First Normal Form (1NF)

A relation will be in 1NF if it contains an **atomic value**. It states that an attribute of a table cannot hold multiple values. It must hold only single-valued attributes.

First normal form disallows the multi-valued attribute, composite attribute, and their combinations.

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/20231102134515/Normalisation_normalforms_1.jpg" height = 300>

<br>

Before we learn **Second Normal Form**, we need to know a couple of things.

> **Prime attribute** − An attribute which is a part of the primary key.

>  **Non-prime attribute** − An attribute which is not a part of the primary key, but is a part of the candidate key.

### Second Normal Form (2NF)

A relation is said to be in 2NF if:
- It is in **First Normal Form**
- Every non-prime attribute is fully functionally dependent on a prime attribute.

<img src = "https://cdn.educba.com/academy/wp-content/uploads/2019/09/Second-Normal-Form-1.png" height = 400>

### Third Normal Form (3NF)

For a relation to be in Third Normal Form:

- It must be in **Second Normal form**
- No non-prime attribute is transitively dependent on prime key attribute.
-For any non-trivial functional dependency `X -> A`, then either:
    - X is a superkey or,
    - A is prime attribute.

<img src = "https://files.codingninjas.in/article_images/3nf-third-normal-form-4-1639819884.webp" height = 400>

### Boyce-Codd Normal Form

Boyce-Codd Normal Form (BCNF) is an extension of **Third Normal Form** on strict terms. BCNF states that:

- For any non-trivial functional dependency `X -> A`, `X` must be a **super-key**.

### Fourth Normal Form (4NF)

A table is said to be in the fourth normal form if it holds all the below conditions:

- The relation should comply with the **Boyce Codd Normal Form**.
- There should be no multi-valued dependencies between the table’s attributes.

<img src = "https://cdn.educba.com/academy/wp-content/uploads/2020/01/Fourth-normal-form.jpg" height = 400>

<br>

**Example**

We shall talk about the fourth normal form using `Students` relation. The `Students` relation has three attributes. `Stud_ID`, `Stud_Course`, and `Stud_Hobby`. The relation is not in the fourth normal form (4NF), as it has multi-valued dependencies in it. The attributes `Stud_Course` and `Stud_Hobby` are dependent on the `Stud_ID` attribute, which ends in multi-valued dependency. Therefore, to make the relation in 4NF, we need to break the relation into two different relations: `Students_Course` and `Students_Hobby`. These two relations are in the fourth normal form. 

### Fifth Normal Form (5NF)

A relation R is in 5NF if and only if it satisfies following conditions:

- R should be already in **4NF**.
- It cannot be subdivided into any smaller tables without losing some form of information (join dependency).

## Denormalization in Databases

Denormalization is a database optimization technique in which we add redundant (extra) data to one or more tables. This can help us avoid costly joins in a relational database. Note that denormalization does **not** mean not doing normalization. It is an optimization technique that is applied after doing normalization. 

In a traditional normalized database, we store data in separate logical tables and attempt to minimize redundant data. We may strive to have only one copy of each piece of data in database. 

For example, in a normalized database, we might have a `Courses` table and a `Teachers` table. Each entry in `Courses` would store the `teacherID` for a Course but not the `teacherName`. When we need to retrieve a list of all Courses with the Teacher name, we would do a join between these two tables. In some ways, this is great; if a teacher changes his or her name, we only have to update the name in one place. The drawback is that if tables are large, we may spend an unnecessarily long time doing joins on tables. Thus Denormalization is introduced.

## 