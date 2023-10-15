# Banking_Transaction_Management_RDBMS_SQL

## Table of Contents
- [Project Objective](#project-objective)
- [Problem Statement](#problem-statement)
- [Business Understanding](#business-understanding)
- [Methodology](#methodology)
- [Business Questions](#business-questions)
- [Entity Relationship Diagram](#entity-relationship-diagram)
- [Building Database using SQL](#building-database-using-sql)
- [Quering using SQL](#quering-using-sql)
- [Conclusion](#conclusion)
- [References](#references) 

## Project Objective

The objective of this project is to provide an overview on relational database management and how SQL is used to answer simple questions in the real world.

## Problem Statement

In this project we will assume an imaginary financial services company, XYZ Fintech. 

“XYZ Fintech” is a financial services company offering wide range of financial products like Credit cards, personal loans, auto loans, savings account and checking account all over the USA. One of its major business comes from credit card. The company wants to develop a database to track and monitor the credit card transactions.
You are a Database Administrator. They hired you to seek help on how they can manage their huge transaction database.

## Business Understanding

- Financial transactions are the lifeblood of fintech companies. Whether it's processing payments, executing trades, or managing loans, these actions need to be executed with the utmost precision. RDBMS are the guardians of these transactions, armed with the power of ACID compliance (Atomicity, Consistency, Isolation, Durability). They ensure that a financial transaction, once initiated, is completed successfully and reliably, and that the data remains consistent throughout the process.
- In a world where every dollar counts, RDBMS provides the rock-solid foundation upon which fintech companies build their operations, making sure your financial actions are executed without a glitch.

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/rdbms_image.jpg" width="500" height="300" />
</p>

## Methodology

As a Database Administrator, your role is develop an efficient and scalable database that will help company achieve their goal in terms of managing data. In order to do that first you need to start understanding what the company does, what are they looking for, what services they offer, what data they have, what are the types of data, how they are collecting it, what systems they have, what is their end goal in terms of data output and so on. Some of the questions are given in the **Business Questions** section. You can follow the following steps:

- **Understand the Company**: As a Database Administrator, your first step is to understand the company's operations. This involves learning about the company's services, data types, data collection methods, existing systems, and its data-related goals.

- **Ask Business Questions:** To gain this understanding, ask a series of questions. You can find some of these questions in the "Business Questions" section.

- **Define Business Rules:** After gathering answers to your questions, define business rules. These rules set constraints and guidelines for how data is stored and managed in the database. They are crucial for data integrity and compliance with business requirements.

- **Design the Database Structure:** Think of this as creating a blueprint or diagram of the company's data. One widely used tool for this is the Entity-Relationship (ER) diagram. It visually represents the logical structure of the database, showing how different areas or entities relate to each other.

- **Entities and Attributes:** In the ER diagram, entities represent different areas or tables in the database. Each entity has attributes, which are like the columns in your data tables. You'll define relationships and important features within this diagram.

## Business Questions

We will frame business questions for our client XYZ Fintech. Some of the interesting questions, we can ask them are as follows:

1. What is the goal of the company in terms of database usage?
2. What services do you offer?
3. Who are the stakeholders that you deal with? Can you ellaborate on process on how does the trasactions work with each of these?
4. How much transaction data does your company currently handle, and what is the expected growth rate?
5. What is the peak transaction throughput that your database needs to handle, and what are the performance requirements during high traffic periods?
6. What types of queries and reporting functions do you need to perform on the transaction data?
7. Are you currently using any specific database management system, or do you have preferences for technologies and tools?
8. What specific security and compliance standards do you need to adhere to?

## Business Rules

Business Rules represents the different entities in business and define relationships between them. The ER diagram represents the pictorial representation between these entities. Defining business rules properly helps us to built the database in an organized and hence it is important to focus on every details on how company works.

For this project, we will consider a very simple example of Credit Card transaction in XYZ Fintech company. This will a very basic business rules for XYZ Fintech but note that they are more complex in real word situation. However, I'm hopeful that this will be a basic understanding of how business rules are made and used in ER diagram.

Assume we have collected enough data from the questions and our research on the Credit Trasaction department of XYZ Fintech. We found that the company has different entities and relationships and hence we developed the business rules for the company.

**Business rules**

- Every customer of the XYZ Fintech company must have atleast one credit account in the company. Each Credit Account must be associated with one and only one customer.
- Transactions made by the customers are recorded. Each Credit account can have multiple transactions. Each transaction must be associated with only one credit account. 
- There are different credit card types offered by the company, namely; *Regular Card*, *Premium Card* and *Travel Card*.
- A credit account may have one or more card types but each card type belongs to one and only credit account.
- All card types share common attributes (card type, customer ID, credit limit, and annual fee) but some card type have unique attributes (for instance, minimum pay for Regular, annual cashback for Premium and travel details for Travel card).
- Customers make transactions at different vendors. Every transactions are recorded when customer purchases through a vendor with the company's credit card.
- Every Transaction done must belong to only one Vendor. Each Vendor may have many transactions. A transaction is unique.
- Apart from this, the company also has call center to guide the customers through call center agents. Every agent makes a call to many customers. Each customer can be contacted by many agents.

After defining the business rules, you may notice that there exists different relationship between entities. Note these relationships, we will discuss in detail in the next section.

## Entity Relationship Diagram

The business rules defined above give us an overall process on how company works and develops an intuition how data might be recorded. We were able to develop some intuitions on how there are different types of relationships between various entities. For instance, Each credit account has multiple transactions. In other words, we can also say that, there is one entity 'Credit Account' that has more than single relationship with another entity maybe 'Transaction'. Therefore, it is safe to say that the Credit Account may have one-to-many relationship with Transaction. These types of relationships are used to develop an ER diagram. We will develop ER diagram and I will try to explain the different relationship through the example of an ER diagram. Please note, the verbs (may, must), the pronouns (Each, Every) used have some meaning to be considered, I would suggest to read a good article or book on how these relationships are defined in ER diagram.

Based on the above business rules, think of a table and how each data might be recorded in a table. For instance, after reading a business rule, I can think of a **Customer** table and it can have attributes such as Customer name, customer card details, customer's demographics. Also, think of how can we identify an indiividual customer. Therefore, we need a unique ID for customer, lets call it as may be *Customer ID*. Some of the examples of the tables I can think are given in this figure.

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/tables_attributes.png" width="600" height="200" />
</p>


You can create much more tables like this while you understand how the data is recorded in the company. After creating identify different relationships between these tables, for instance, assume that the "Customer can make multiple transactions but each transaction can be associated with one customer. Therefore, Customer has One-to-Many relationship with Transaction". There are three or four cardinal relationships between tables:

1. One-to-One
2. One-to-Many
3. Many-to-Many

You can find the details of these relationships in the Reference section. Since the relationship between Customer and Trasaction is One-to-Many, we will denote it with the relationship line using Crow's Foot Notation (details in Reference section). It is the widely used technique for defining the relationship in ER diagrams. The pictorial representation is given below:

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/tables_attributes_2.png" width="600" height="200" />
</p>


Now, that you know on how you can built a relationship between tables, we can bulit much more tables and try to relate them with each other. However, you cannot go on building never ending tables and relationships. You also need to think about the storage space and structural issues for maintainance. Therefore, there is a technique used to organize data and data tables while designing a database. Usually, the technique used for DBMS is **Normalization** that helps in keeping data consistent and solves data integrity issues. There are different norm forms like 1NF, 2NF, 3NF and so on. You can find the detail in the Reference section. 

In additon to this, the relational tables possess a properties that needs to be followed while buildiing an ER diagram. **Keys** are one of the most vital elements in a relational database to maintain the relationship between the tables and it also helps in uniquely identifying the data from a table. There are different types of keys such as Primary keys, Foreign keys, etc. You will find details in the reference section.

Following these techniques, properties and collecting the knowledge of the entities-relationship from business rules, I have developed an Enahnced ER diagram (EER) using Lucid Chart. The details for each symbols and boxes representations are given in the References section.

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/EERD.png" width="800" height="400" />
</p>

The above EER diagram is the pictorial representation of the Business Rules. Some of the examples in the EER diagram can be explained as follows:

1. M: N relationship.
In the above EER diagram, for the business rule, “Each agent can make a call to many customers. Each customer can be contacted by many agents”. The relationship between Agent and the Customer is M: N as each agent “may” call many customers and each customer can be contacted by many agents. The relationship can be sub-divided into two one-to-many relationship by building a bridge between the Agent and the Customer as “Agent_customer” composite entity. The relationship on the “many” side is optional since the agent may make a call to customer and customer “may” be contacted by agent. According to business rules the cardinality on the many side is (0, N)


2. Enhanced ER relationship
For the business rule, “All card types share common attributes (card type, customer ID, credit limit, and annual fee) but some card type has unique attributes (for instance, minimum pay for Regular, annual cashback for Premium and travel details for Travel card)” can be implemented using the EER diagram as it follows the concept of “Generalization”. The relationship between Credit Account and the Card Type is 1: M as each credit account “may” many credit account can have one or more card types. The relationship on the “many” sides is optional as it can be optional and mandatory on “one” side since card type can belong only to one credit account. The Credit Account is belonging to one have one or more card type, hence class/subclass relationship for the card types has been created which carries the similar attributes of the superclass Credit account and have unique attributes mentioned in the individual sub-classes. A credit account can have one or more type of credit card type hence “overlapping” constraint has been used. Since, it is given that credit account can have one or more card types, it is partial participation as given in EERD. 

## Building Database using SQL

The above EER diagram can be used to implement in the database system. This can be done by writing SQL queries. You can use Live Oracle SQL or My SQL Workbench, both are open source. I have used Live Oracle platform. 

Before we start, think of how the data hierarchy. The given figure is a pictorial representation takem from Oracle site that represents the data storage. This doesn't hold true for everything. The point is the database can have different tables that are related to each other by some keys. When we want to write a query, we need to think of hierarchy. For this project, we will assume that the these tables are stored under the database 'Credit Department' and we will write a SQL query accordingly.

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/hierarchy.png" width="600" height="200" />
</p>

#### SQL DDL statements

SQL Data Definition Language is a subset of SQL that is used to define, manage, and control the structure of a database. It focuses on the management of database schemas and the objects within a database. It allows you to create database objects such as tables, indexes, views, and schemas. The guide for SQL DDL and DML functions are given in Reference.

- Create a Database

We will start by creating a database **Credit_Dept** and then create tables as given in ER diagram. We will create these tables under the Database Credit_Dept.

```SQL

-- Creating a Database for Credit Department for XYZ Fintech company

CREATE DATABASE CREDIT_DEPT;

```
- Create Tables

Create different tables adn soecify constraints in the table. Following my ER diagram, I will create all the tables and relate thenm by specifying the keys in the constraint. Please note we also need to specify datatypes and their length. The following are the examples for creating a table.

```SQL

-- Using the Credit department database

USE CREDIT_DEPT;

-- Creating a customer table

CREATE TABLE CUSTOMER
    ( CUST ID VARCHAR (50),
      CUST FNAME CHAR (30),
      CUST LNAME CHAR (30),
      CUST PHONE VARCHAR (15),
      CUST LOCATION VARCHAR (30),
      CUST SSN NUMBER (15),
      CONSTRAINT CUST_ID_PK PRIIMARY KEY (CUST_ID)
     );

-- Checking the table

DESC CUSTOMER;

```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/cust_table.png" width="600" height="200" />
</p>


```sql
-- Creating a Agent-customer link table

CREATE TABLE AGENT_CUSTOMER
    ( CUST ID VARCHAR (50),
      AGENT ID VARCHAR(20),
      CONTACT DETAILS VARCHAR (50) ,
      CONTACT_ID VARCHAR2(10),
      CONTACT TIMESTAMP DATE,
      CONSTRAINT CUST_ID_FK FOREIGN KEY (CUST_ID) REFERENCES CUSTOMER (CUST_ID), 
      CONSTRAINT AGENT_ID_FK FOREIGN KEY (AGENT_ID) REFERENCES AGENT_RECORD (AGENT_ID ) )
      ;
      
DESC AGENT_CUSTOMER;

```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/agent_table.png" width="600" height="200" />
</p>


#### SQL DML statements

SQL DML (Data Manipulation Language) functions are a set of SQL commands that are responsible for querying, inserting, updating, and deleting data within a database. 

- Insert values into tables

Now that we have created a database and all the tables as per ER diagram. Now we will begin inserting data into the tables and see how it works. Some of the examples are as follows.

```sql

-- Inserting values into the Agent record table

INSERT INTO AGENT_RECORD (AGENT_ID, AGNT_CONTACT_ID, AGENT_LNAME, AGENT_FNAME, AGENT_DESC)
 VALUES ('A100000', 'C1001', 'Greene', 'Rachael', 'Call Center');
    
INSERT INTO AGENT_RECORD
 VALUES ('A100002', 'C2001','Bing', 'Chandler', 'Customer service');

DESC AGENT_RECORD;

```

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/Insert_agent.png" width="600" height="200" />
</p>


```sql

-- Inserting values in Card Type table

INSERT INTO CARD_TYPE(CARD_TYPE_CODE, CARD_DETAILS)
 VALUES (800200, 'Premium Card');
    
INSERT INTO CARD_TYPE
 VALUES (800100,'Regular Card');

INSERT INTO CARD_TYPE
 VALUES (800300,'Travel Card');

DESC CARD_TYPE;

SELECT* FROM CARD_TYPE;

```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/card_insert.png" width="600" height="200" />
</p>


In this way, we can create database, tables, insert values and specify constraints in the table by using DML and DDL function of SQL. Now its time to see how it works.

## Quering using SQL

After you have done creating tables and insertying all the data. It's time to test it. We will frame some questions which we feel that might be encountered with the end users for business requirment. We will write a query and see how it works.

**1. Business Query 1: As a business analyst, I want to look at the remaining balance of the customers who had made their purchases from the vendor named 'ALDI'.

```sql

-- Joins and Arithmetic operations using SQL

SELECT 
    T.TRANSACTION_ID 
    , T.VENDOR_ID
    , C.CARD_TYPE_CODE
    , CREDIT_LIMIT - TRANSAC_AMT BALANCE
    , V.VENDOR_NAME
FROM 
    transaction_detail T, credit_account C, vendor V
WHERE 
    T.CARD_NO = C.CARD_NO 
AND 
    T.VENDOR_ID = V.VENDOR_ID
AND 
    T.VENDOR_ID LIKE '%2';

```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/Query1.png" width="600" height="200" />
</p>


**2. Business Query 2: As a data analyst, I want to look at the details of the customers whp purchased from "ALDI" and "Walmart" on the 8th of April. Calculates their monthly fee, round up to 2 decimal points.

```sql

-- JOIN with USING and arithmetic operation

SELECT 
      CARD_NO  
    , CUST_ID 
    , CREDIT_LIMIT 
    , ANNUAL_FEE 
    , CARD_TYPE_CODE  
    , TRANSACTION_ID 
    , VENDOR_ID 
    , TRANSAC_TIMESTAMP 
    , TRANSAC_AMT
    , ROUND(ANNUAL_FEE/12 , 2) AS MONTHLY_FEE
FROM 
    CREDIT_ACCOUNT C
JOIN 
    TRANSACTION_DETAIL T
USING 
    (CARD_NO)
WHERE 
    VENDOR_ID IN ('V001','V002') AND TRANSAC_TIMESTAMP = '08-APR-23';
    
```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/Query2.png" width="600" height="200" />
</p>


**Business Query 3: As a data engineer, I want to calculate the average transaction amount of each vendor at different locations.

```sql

-- Subqueries

SELECT 
      V.VENDOR_LOCATION
    , T.VENDOR_ID
    , T.AVG_TRX_AMT
FROM 
    VENDOR V
    , (SELECT 
             VENDOR_ID
           , ROUND(AVG(TRANSAC_AMT),2) AVG_TRX_AMT
       FROM 
             TRANSACTION
       GROUP BY 
               VENDOR_ID) T
WHERE 
    V.VENDOR_ID = T.VENDOR_ID 
    ;

```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/Query3.png" width="600" height="200" />
</p>


**Business Query 4: As an analyst, I want to calculate the average monthly transaction per customer in the year of 2023.

```sql

-- Group by and join functions

SELECT 
    ROUND(AVG(SUM(TRANSAC_AMT)),2) AVG_MONTHLY_TRX_PER_CUSTOMER
FROM
    CUSTOMER C
JOIN 
    CREDIT_ACCOUNT A
ON 
    C.CUST_ID = A.CUST_ID 
JOIN 
    TRANSACTION T
ON 
    T.CARD_NO = A.CARD_NO
WHERE
    TRUNC(TO_DATE(TRANSAC_TIMESTAMP,'DD-MON-YY'), 'YEAR') = '01-JAN-23' 
GROUP BY 
    C.CUST_ID 
   ,TRUNC(TO_DATE(TRANSAC_TIMESTAMP,'DD-MON-YY'), 'MONTH')
    ;
    
```
<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/Query4.png" width="600" height="200" />
</p>


## Conclusion

As we can see, Relational Database Management Systems (RDBMS) is helpful in managing Databases. They provide a structured and organized approach to store and manage data, ensuring data integrity, security, and scalability. RDBMS systems, when used appropriately, act as the bedrock of trust for businesses and applications, particularly in domains like finance, where the precision and reliability of data are paramount.

SQL, the powerful query language designed for RDBMS systems, further accentuates the significance of these databases. SQL is a versatile tool that enables users to retrieve, manipulate, and analyze data with great efficiency and precision. Its ability to construct complex queries, aggregate and filter data, and join tables makes it indispensable in data analysis, reporting, and application development.

## References

1. Ramez Elmasri, Shamkant B. Navathe (2015).Fundamentals of Database Systems, 7th Edition, Pearson ISBN-13: 978-0133970777. ISBN-10: 0133970779
2. Retrieved from: Created in Lucidchart, www.lucidchart.com
3. Retrieved from: Oracle Live SQL, https://livesql.oracle.com/apex/f?p=590:1000
4. Retrieved from: Normalization, https://www.studytonight.com/dbms/database-normalization.php
5. Retrieved from: Oracle SQL Reference, https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/Introduction-to-Oracle-SQL.html#GUID-049B7AE8-11E1-4110-B3E4-D117907D77AC
