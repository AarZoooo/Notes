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

