# Basics of Databases

A Database is a collection of information -- information that's peferably related, and perferably orgainsed.This means that a database can be in any form or shape. 

But in the most basic terms, a database just helps you store data.

In the digital world, a database consists of physical files on your computer, or in a cloud computer.

A database allows you to record, organise, manage, retrieve, and update that data efficiently. A database is usually structured, organised, and containing related information, otherwise it will just be a pile of random data.

The structure of a database consists of two main parts, the data and the metadata. 

***Data*** : Data is actual information stored in the database.

![Data Example Image](https://cdn.hashnode.com/res/hashnode/image/upload/v1735566678439/3f33f183-ebe5-40a3-98d1-d8462dab9dbb.png)

***MetaData*** : Metadata is the structural description of the data in a database. It describes the names of fields used to store data, the length of those fields, and their datatypes. metadata gives structure and organisation to raw data. 

## How to update a Database

You can make changes to the different parts of a database using various commands. There are two general types of commands:

***Data Definition Language(DDL)*** : It's made up of commands that define or alter the shape or structure of the data in the database.

***These commands affect the metadata part of a database.***

You might make,
* alterations like creating new tables in a relational database
* changing the shape of documents in a document-based database by adding new fields
* removing an entire graph in a graph database

***Data Manipulation Language(DML)*** :  It's made up of commands that interact with the data stored in the database. 

These commands do not effect the structure of the data, but rather the data itself. 

These commands only affect the data part of a database. 

Some of things you can do with DML include reading data from a database, adding new data to the database, editing data and deleting data.

A datatype defines what type of information can be stored in a field. 

So a field in a table with a datatype of date will only be able to store date records, and will throw an error if you try to store something else.

Common datatypes include `varchar` for data that might contain different characters(text + numbers), `date` for data values,  `int` for whole numbers, and so on.


## What is database model?

A database model is a concept used to describe the information stored on a database. 

Think of its a building's blueprint designed by an architect.

It details all the tables, columns, and datatypes of the database. 

A database model determines how data is logically represented and accessed. 

Datbase models define if data is stored in tables using rows and columns, or in JSON-like objects. 

The also define how data relates, how you can query it, and how you manage it.

***Relational Model:*** The Relational Model is the most popular database model. This model uses tables with rows and columns to store data. This model uses the SQL language to manage the data.

Examples of some relational databases include MySQL, PostgreSQL, and SQLite. 


## How do Relational databases work ?

A relational database has the ability to establish links - or relationships - between information by joining tables, which makes it easy too understand and gain insights about the relationship between various data points. 

The tables in a relational DB model are often called relations.

Each row in a database table represents a single record in the table. The row tells the full story of the data. It contains data for all the columns in that table for one specific entity.

Rows are also sometimes referred to as records or tuples in database terminology.

In some contexts, columns are also referred to as fields.

Despite this flexibility with relationships, the data in a table can be accessed directly without having knowledge of related or unrelated tables. 

You can easily access records as long as you know what you’re looking for. Primary and Foreign keys are used in the relational model to manage these relationships.

## What is a Database Management Systems (DBMS) ?
A database management system (DBMS) is a collection of programs for managing and communicating with a underlying database engine. 

In simpler terms, a DBMS is the database engine coupled with whatever additional tools that come with it. 

A DBMS helps you create, manage, and use databases. It provides an abstraction over the database engine and lets you more easily store, update, and retrieve data in a secure way.

The tools that come in a DBMS can include, but are not always limited to:

    frontend tools (like a query interface, or an administration panel) that help you run queries and visualise the resulting data in the database

    backup and recovery tools that work in the background with little to no user interaction

    security tools for user access management (roles and permissions) and data import or export tools.


DBMS are usually model-specific, so there are DBMS focused on the Relational Database Model called RDBMS, where the “R” is for Relational. Examples of popular RDBMS include MySQL, PostgreSQL, Oracle, and Microsoft SQL Server. RDBMS use SQL (Structured Query Language) to interact with the data.

