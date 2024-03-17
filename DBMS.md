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

## Introduction to Database Security

To protect the database from internal and external threats, organizations take various measures. Ensuring these measures is called database security. Since a lot of important information is being sent through the computer network, anyone may hack or breach the security and misuse the data for personal needs. Hence it is necessary to protect the data from possible threats.

We consider database security about the following situations:

- Theft and fraudulent
- Loss of confidentiality or secrecy
- Loss of data privacy
- Loss of data integrity
- Loss of availability of data

## Threats

Any situation or event, whether intentionally or incidentally, can cause damage, which can reflect an adverse effect on the database structure and, consequently, the organization. A threat may occur by a situation or event involving a person or the action or situations that are probably to bring harm to an organization and its database.

Threats to databases can result in the loss or degradation of some or all of the following commonly accepted security goals: integrity, availability, and confidentiality.

### Types of Threats

**Denial of Service attack.** This attack makes a database server greatly slower or even not available to user at all. DoS attack does not result in the disclosure or loss of the database information, it can cost the victims much time and money.

**Sniff attack.** To accommodate the e-commerce and advantage of distributed systems, database is designed in a client-server mode. Attackers can use sniffer software to monitor data streams, and acquire some confidential information. For example, the credit card number of a customer.

**Spoofing attack.** Attackers forge a legal web application to access the database, and then retrieve data from the database and use it for bad transactions. The most common spoofing attacks are TCP used to get the IP addresses and DNS spoofing used to get the mapping between IP address and DNS name.

**Trojan Horse.** It is a malicious program that embeds into the system. It can modify the database and reside in operating system.

**Excessive privileges.** When workers are granted default database privileges that exceed the requirements of their job functions, these privileges can be abused.

**Database injection attacks.** The two major types of database injection attacks are SQL injections that target traditional database systems and NoSQL injections that target “big data” platforms.

**Malware.** A perennial threat, malware is used to steal sensitive data via legitimate users using infected devices.

**Storage media exposure.** Backup storage media is often completely unprotected from attack.

**Exploitation of vulnerable databases.** It generally takes organizations months to patch databases, during which time they remain vulnerable. Attackers know how to exploit unpatched databases or databases that still have default accounts and configuration parameters.

**The human factor.** The root cause for 30 percent of data breach incidents is human negligence.

## Counter Measures

To protect the database system from the above mentioned threats. Here are some counter measures which are as follows:

- Control Measures
- RAID - Redundant Array of Independent Disks
- Authentication
- Backup

### Control Measures

Four main control measures are used to provide security of data in databases:

- **Access control -** The security mechanism of a DBMS must include provisions for restricting access to the database system as a whole. This function is handled by creating user accounts and passwords to control the login process by the DBMS.

- **Inference control -** A method that prevents unauthorized users from drawing conclusions about sensitive information from less sensitive data. This method protects sensitive information from indirect disclosure by preventing users from completing any inference channel.

- **Flow control -** It regulates how data is transferred between system components. It prevents data from being accessed by unauthorized agents, and ensures that data is processed reliably, effectively, and securely.

- **Data encryption -** The data is encoded using some coding algorithm. An unauthorized user who accesses encoded data will have difficulty deciphering it, but authorized users are given decoding or decrypting algorithms (or keys) to decipher the data.

### Specific Counter Measures

- **Excessive Database Privileges**
  - It is advised to deploy and uphold a strict access and privileges control policy.
  - Don’t grant excessive privileges to company employees and revoke outdated privileges in time.

- **SQL Injections**
  - Stored procedure shall be used instead of direct queries.
  - MVC Architecture shall be implemented.

- **Database Backups Exposure**
  - Encrypt both databases and backups.
  - Audit both the database and backups.

- **DB Vulnerabilities and Misconfigurations**
  - Your databases shouldn’t have any default accounts.
  - Your IT personnel should be highly qualified and experienced.

- **Denial of service attack**
  - Harden the TCP/IP stack by applying the appropriate registry settings to increase the size of the TCP connection queue.
  - Decrease the connection establishment period.
  - Employ dynamic backlog mechanisms to ensure that the connection queue is never exhausted.
  - Use a network Intrusion Detection System (IDS).

- **Unmanaged Sensitive Data**
  - Encrypt all sensitive data in your database(s).
  - Apply required controls and permissions to the database.

## Procedural Language / Structured Query Language (PL/SQL)

PL/SQL is a block structured language that enables developers to combine the power of SQL with procedural statements. All the statements of a block are passed to oracle engine all at once which increases processing speed and decreases the traffic. 

### Characteristics

- PL/SQL is basically a procedural language, which provides the functionality of decision making, iteration and many more features of procedural programming languages.
- PL/SQL can execute a number of queries in one block using single command.
- One can create a PL/SQL unit such as procedures, functions, packages, triggers, and types, which are stored in the database for reuse by applications.
- PL/SQL provides a feature to handle the exception which occurs in PL/SQL block known as exception handling block.
- Applications written in PL/SQL are portable to computer hardware or operating system where Oracle is operational.
- PL/SQL Offers extensive error checking.

### Structure

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/pl-sql.jpg">

<br>

- **Declare** section starts with `DECLARE` keyword in which variables, constants, records as cursors can be declared which stores data temporarily. It basically consists definition of PL/SQL identifiers. This part of the code is **optional**.

- **Execution** section starts with `BEGIN` and ends with `END` keyword.This is a mandatory section and here the program logic is written to perform any task like loops and conditional statements. It supports all DML commands, DDL commands and SQL*PLUS built-in functions as well.
- **Exception** section starts with `EXCEPTION` keyword.This section is **optional** which contains statements that are executed when a run-time error occurs. Any exceptions can be handled in this section.

### Identifiers

1. **Variables**: Like several other programming languages, variables in PL/SQL must be declared prior to its use. They should have a valid name and data type as well.

    Example:

        var1 INTEGER := 10;

    > For learning different SQL datatypes, visit https://www.w3schools.com/sql/sql_datatypes.asp

2. **Displaying Output**: The outputs are displayed by using `DBMS_OUTPUT` which is a built-in package that enables the user to display output, debugging information, and send messages from PL/SQL blocks, subprograms, packages, and triggers.
    
    Example:

        dbms_output.put_line('I love PL/SQL');
    
    Output will be: `I love PL/SQL`.

3. **Taking input from user**: Just like in other programming languages, in PL/SQL also, we can take input from the user and store it in a variable.

    Example:

        a number := &a;

Let's see a program to take two numbers as input from user and returning their sum:

    DECLARE

        a integer := &a;
        b integer := &b; 
        
        c integer;
 
    BEGIN

        c := a + b;
        dbms_output.put_line('Sum of '||a||' and '||b||' is = '||c);
 
    END;
    /

Output:

    Enter value for a: 2
    Enter value for b: 3

    Sum of 2 and 3 is = 5

### Control Structures - Conditional Control

PL/SQL allows the use of an `IF` statement to control the execution of a block of code. In PL/SQL, the `IF -THEN - ELSIF - ELSE - END IF` construct in code blocks allow specifying certain conditions under which a specific block of code should be executed.

1. `IF-THEN` Statement

    This is used when user needs to execute statements when condition is true.

    **Syntax:**

        IF <condition>

        THEN

        <Statements to execute>;

        END IF;
    
    

2. `IF-THEN-ELSE` Statement

    This is used to execute one set of statements when condition is TRUE or different set of statements when condition is FALSE.

    **Syntax:**

        IF <condition>

        THEN

        <Statements to execute when condition is TRUE>

        ELSE

        <Statements to execute when condition is FALSE>

        END IF;

3. `IF-THEN-ELSIF` Statement

    This is used to execute a set of statements when first condition is TRUE or a different set of statements when first condition is FALSE and second condition is TRUE, or another set of statements if second condition is FALSE and so on.

    **Syntax:**

        IF <Condition1>

        THEN

        <Statements to execute when condition1 is TRUE>

        ELSIF <condition2>

        THEN

        <Statements to execute when condition2 is TRUE>

        END IF;

4. `IF-THEN-ELS-IF-ELSE` Statement

    This is a modification of the previous one, where `ELSE` block is written in the end which states the statements that are executed when all of the mentioned conditions are FALSE.

    **Syntax:**

        IF <condition1>

        THEN

        <Statements to execute when condition1 is TRUE>

        ELSIF <condition2>

        THEN

        <Statements to execute when condition2 is TRUE>

        ELSE

        <Statements to execute when both condition1 and condition2 are FALSE>

        END IF;

5. `CASE` Statement

    This Statement provides facility to execute a sequence of statements based on a selector. A selector may be variable, function or an expression.

    **Syntax:**

        CASE <expression>

        WHEN <condition1> THEN <result1>

        WHEN <condition2> THEN <result2>

        ......................

        WHEN <condition_n> THEN <result_n>

        ELSE <result>

        END;
    
### Control Structures - Iterative Control (LOOP statements)

LOOP statements let you execute a sequence of statements multiple times. There are three forms of LOOP statements: `LOOP`, `WHILE-LOOP`, and `FOR-LOOP`.

1. **LOOP**

    The simplest form of LOOP statement is the basic (or infinite) loop, which encloses a sequence of statements between the keywords `LOOP` and `END LOOP`.

    **Syntax:**

        LOOP

        <sequence_of_statements>

        END LOOP;

    With each iteration of the loop, the sequence of statements is executed, then control resumes at the top of the loop. You can place one or more EXIT statements anywhere inside a loop, but nowhere outside a loop. There are two forms of EXIT statements: `EXIT` and `EXIT-WHEN`.

    ---

    - The **`EXIT`** statement forces a loop to complete unconditionally. When an EXIT statement is encountered, the loop completes immediately and control passes to the next statement.

            LOOP

            ...

            IF credit_rating < 3 THEN

            ...

            EXIT; -- exit loop immediately

            END IF;

            END LOOP;

    - The **`EXIT-WHEN`** statement lets a loop complete conditionally. When the EXIT statement is encountered, the condition in the WHEN clause is evaluated. If the condition is true, the loop completes and control passes to the next statement after the loop.
 
            LOOP

            FETCH c1 INTO ...

            EXIT WHEN c1%NOTFOUND; -- exit loop if condition is true

            ...

            END LOOP;

            CLOSE c1;

    ---

    Like PL/SQL blocks, loops can be labeled.

    - **Loop Labels:** A label, an undeclared identifier enclosed by double angle brackets, can be used at the beginning of the LOOP statement to put a name to it, as follows:

            <<label_name>>

            LOOP

            sequence_of_statements

            END LOOP;
        
        Optionally, the label name can also appear at the end of the LOOP statement.

---

2. **WHILE-LOOP**

    The WHILE-LOOP statement associates a condition with a sequence of statements enclosed by the keywords `LOOP` and `END LOOP`.

    **Syntax:**

        WHILE <condition> LOOP

        <sequence_of_statements>

        END LOOP;
    
    Before each iteration of the loop, the condition is evaluated. If the condition is true, the sequence of statements is executed, then control resumes at the top of the loop. If the condition is false or null, the loop ends and control passes to the next statement.

    **Example:** Find reverse of given number using while loop

        DECLARE

            num Number(3) := 123;
            ans Number(3) := 0;
            i Number(3) := 0;

        BEGIN

            WHILE num != 0 LOOP

                i := mod(num,10);
                ans := (ans * 10 ) + i;
                num := floor(num/10);

            END LOOP;

            dbms_output.put_line('reverse of given number is: ' || ans);

        END;
        /

---

3. **FOR-LOOP**

    The number of iterations through a FOR loop is known before the loop is entered. FOR loops iterate over a specified range of integers. A double dot `..` serves as the range operator.

    **Syntax:**

        FOR <counter_variable> IN [REVERSE] <lower_bound>..<higher_bound> LOOP

        <sequence_of_statements>

        END LOOP;
    
    The range is evaluated when the FOR loop is first entered and is never re-evaluated.

    **Example:** Calculating value of pi($\pi$) for 500 terms

        DECLARE

        p NUMBER := 0;

        BEGIN

        FOR k IN 1..500 LOOP

        p := p + ( ( (-1) ** (k + 1) ) / ((2 * k) - 1) );

        END LOOP;

        p := 4 * p;

        DBMS_OUTPUT.PUT_LINE( 'pi is approximately : ' || p ); -- print result

        END;
        /
    
---

### Cursors

To execute SQL statements, a work area is used by the Oracle engine for its internal processing and storing the information. This work area is private to SQL’s operations. The **Cursor** is the PL/SQL construct that allows the user to name the work area and access the stored information in it.

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/Untitled-Diagram-6.jpg">

The major function of a cursor is to retrieve data, **one row at a time**, from a result set, unlike the SQL commands which operate on all the rows in the result set at one time. Cursors are used when the user needs to update records in a **singleton fashion** or in a **row by row manner**, in a database table. 

> The Data that is stored in the Cursor is called the **Active Data Set**.

**Cursor Actions**

- **Declare Cursor**: A cursor is declared by defining the SQL statement that returns a result set.
- **Open**: A Cursor is opened and populated by executing the SQL statement defined by the cursor.
- **Fetch**: When the cursor is opened, rows can be fetched from the cursor one by one or in a block to perform data manipulation.
- **Close**: After data manipulation, close the cursor explicitly.
- **Deallocate**: Finally, delete the cursor definition and release all the system resources associated with the cursor.

There are two types of cursors which are listed below:

1. Implicit Cursor
2. Explicit cursor

---

### Implicit Cursors

These are **automatically** created by Oracle whenever an SQL statement is executed, when there is no explicit cursor for the statement. Programmers **cannot control** the implicit cursors and the information in it.

In PL/SQL, you can refer to the most recent implicit cursor as the SQL cursor, which always has attributes such as `%FOUND`, `%ISOPEN`, `%NOTFOUND`, and `%ROWCOUNT`. The SQL cursor has additional attributes, `%BULK_ROWCOUNT` and `%BULK_EXCEPTIONS`, designed for use with the `FORALL` statement.

- **`%FOUND`:** Returns TRUE if an `INSERT`, `UPDATE`, or `DELETE` statement affected one or more rows or a `SELECT INTO` statement returned one or more rows. Otherwise, it returns FALSE.

- **`%NOTFOUND`:** The logical opposite of `%FOUND`.

- **`%ISOPEN`:** Always returns FALSE for implicit cursors, because Oracle closes the SQL cursor automatically after executing its associated SQL statement.

- **`%ROWCOUNT`:** Returns the number of rows affected by an `INSERT`, `UPDATE`, or `DELETE` statement, or returned by a `SELECT INTO` statement.

Any SQL cursor attribute will be accessed as `sql%attribute_name`.

**Example:**

    DECLARE

        total_rows number(2);

    BEGIN

        UPDATE customers
        SET salary = salary + 500;

        IF sql%notfound THEN

            dbms_output.put_line('no customers selected');

        ELSIF sql%found THEN

            total_rows := sql%rowcount;
            dbms_output.put_line( total_rows || ' customers selected ');

        END IF;

    END;
    /

**Output:** If there are six records updated...

    6 customers selected

    PL/SQL procedure successfully completed.

---

### Explicit Cursors

Explicit cursors are **programmer-defined** cursors for gaining more control over the context area. An explicit cursor should be defined in the **declaration** section of the PL/SQL Block. It is created on a `SELECT` Statement which returns more than one row.

**Syntax:**

    CURSOR <cursor_name> IS <select_statement>;

Working with an explicit cursor includes the following steps:

- **Declaring** the cursor for initializing the memory

        CURSOR c_customers IS
        SELECT id, name, address FROM customers;

- **Opening** the cursor for allocating the memory

        OPEN c_customers;

- **Fetching** the cursor for retrieving the data

        FETCH c_customers INTO c_id, c_name, c_addr;

- **Closing** the cursor to release the allocated memory

        CLOSE c_customers;

**Example:** Following is a complete example to illustrate the concepts of explicit cursors by fetching customer data from a relation and printing it:

    DECLARE

        c_id customers.id%type;
        c_name customer.name%type;
        c_addr customers.address%type;

        CURSOR c_customers is
        SELECT id, name, address FROM customers;

    BEGIN

        OPEN c_customers;

        LOOP

            FETCH c_customers into c_id, c_name, c_addr;

            EXIT WHEN c_customers%notfound;

            dbms_output.put_line(c_id || ' ' || c_name || ' ' || c_addr);

        END LOOP;

        CLOSE c_customers;

    END;
    /

When the above code is executed at the SQL prompt, it can produce the following result:

    1 Ramesh Ahmedabad
    2 Khilan Delhi
    3 kaushik Kota
    4 Chaitali Mumbai
    5 Hardik Bhopal
    6 Komal MP

    PL/SQL procedure successfully completed.

---

### Views

Views in SQL are kind of virtual tables. A view also has rows and columns as they are in a real table in the database. We can create a view by selecting fields from one or more tables present in the database. A View can either have all the rows of a table or specific rows based on certain condition.

Creating a view does not take any storage space as only the query is stored in the data dictionary and the actual data is not stored anywhere.

> The maximum number of columns that can be defined in a SQL View are **1000** as in tables.

#### Importances

- Reducing complexity.
- Improving security.
- Renaming the table columns.

#### Syntax

    CREATE VIEW <view_name> AS
    SELECT <column1>, <column2>.....
    FROM <table_name>
    WHERE <condition>;

- `view_name`: Name for the View
- `table_name`: Name of the table
- `condition`: Condition to select rows

#### Example 1: Creating View from a single table

In this example we will create a View named `DetailsView` from the table `StudentDetails`.

    CREATE VIEW DetailsView AS
    SELECT NAME, ADDRESS
    FROM StudentDetails
    WHERE S_ID < 5;

To see the data in the View, we can query the view in the same manner as we query a table. 

    SELECT * FROM DetailsView;

#### Example 2: Creating View from multiple tables

In this example we will create a View named `MarksView` from two tables `StudentDetails` and `StudentMarks`. To create a View from multiple tables we can simply include multiple tables in the `SELECT` statement.

    CREATE VIEW MarksView AS
    SELECT StudentDetails.NAME, StudentDetails.ADDRESS, StudentMarks.MARKS
    FROM StudentDetails, StudentMarks
    WHERE StudentDetails.NAME = StudentMarks.NAME;

To display data of View MarksView:

    SELECT * FROM MarksView;

#### Deleting a View

SQL allows us to delete an existing View. We can delete or drop a View using the `DROP` statement.

    DROP VIEW <view_name>;

#### Updating a View

There are certain conditions needed to be satisfied to update a view. If any one of these conditions is not met, then we will not be allowed to update the view.

1. The `SELECT` statement which is used to create the view should not include `GROUP BY` clause or `ORDER BY` clause.
2. The `SELECT` statement should not have the `DISTINCT` keyword.
3. The View should have all `NOT NULL` values.
4. The view should not be created using **nested queries** or *complex queries*.
5. The view should be created from a **single table**. If the view is created using multiple tables then we will not be allowed to update the view.

We can use the `CREATE OR REPLACE VIEW` statement to add or remove fields from a view.

    CREATE OR REPLACE VIEW <view_name> AS
    SELECT <column1>,<coulmn2>,..
    FROM <table_name>
    WHERE <condition>;

For example, if we want to update the view `MarksView` and add the field `AGE` to this View from `StudentMarks` Table, we can do this as:

    CREATE OR REPLACE VIEW MarksView AS
    SELECT StudentDetails.NAME, StudentDetails.ADDRESS, StudentMarks.MARKS, StudentMarks.AGE
    FROM StudentDetails, StudentMarks
    WHERE StudentDetails.NAME = StudentMarks.NAME;

We can fetch all the data from `MarksView` now as:

    SELECT * FROM MarksView;

#### Inserting a row in a view

We can insert a row in a View in a same way as we do in a table. We can use the `INSERT INTO` statement of SQL to insert a row in a View.

    INSERT INTO <view_name> (<column1>, <column2> , <column3>,..)
    VALUES(<value1>, <value2>, <value3>..);

In the following example we will insert a new row in the View `DetailsView` which we have created in the previous example:

    INSERT INTO DetailsView(NAME, ADDRESS)
    VALUES("Suresh","Gurgaon");

We can fetch all the data from `DetailsView` now as,

    SELECT * FROM DetailsView;

#### Deleting a row from a View

Deleting rows from a view is also as simple as deleting rows from a table. We can use the `DELETE` statement of SQL to delete rows from a view. Also deleting a row from a view first delete the row from the actual table and the change is then reflected in the view.

    DELETE FROM <view_name>
    WHERE <condition>;

In the following example we will delete the last row from the view `DetailsView` which we just added in the above example of inserting rows.

    DELETE FROM DetailsView
    WHERE NAME="Suresh";

We can fetch all the data from `DetailsView` now as,

    SELECT * FROM DetailsView;

#### WITH CHECK OPTION clause

It is applicable to an updatable view. It is used in the `CREATE VIEW` statement.

- The `WITH CHECK OPTION` clause is used to prevent the insertion of rows in the view where the condition in the `WHERE` clause in `CREATE VIEW` statement is not satisfied.

- If we have used the `WITH CHECK OPTION` clause in the `CREATE VIEW` statement, and if the `UPDATE` or `INSERT` clause does not satisfy the conditions then they will return an error.

In the following example we are creating a View `SampleView` from `StudentDetails` Table with `WITH CHECK OPTION` clause.

    CREATE VIEW SampleView AS
    SELECT S_ID, NAME
    FROM StudentDetails
    WHERE NAME IS NOT NULL
    WITH CHECK OPTION;

In this View if we now try to insert a new row with null value in the `NAME` column then it will give an error because the view is created with the condition for `NAME` column as `NOT NULL`.

#### Importances of using Views

A good database should contain views due to the given reasons:

1. **Restricting data access**: Views provide an additional level of table security by restricting access to a predetermined set of rows and columns of a table.

2. **Hiding data complexity**: A view can hide the complexity that exists in a multiple table join.

3. **Simplify commands for the user**: Views allows the user to select information from multiple tables without requiring the users to actually know how to perform a join.

4. **Store complex queries**: Views can be used to store complex queries.

5. **Rename Columns**: Views can also be used to rename the columns without affecting the base tables provided the number of columns in view must match the number of columns specified in select statement. Thus, renaming helps to to hide the names of the columns of the base tables.

6. **Multiple view facility**: Different views can be created on the same table for different users.