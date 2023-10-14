# Banking_Transaction_Management_RDBMS_SQL

## Table of Contents
- [Project Objective](#project-objective)
- [Problem Statement](#problem-statement)
- [Business Understanding](#business-understanding)
- [Methodology](#methodology)
- [Business Questions](#business-questions)
- [Entity Relationship Diagram (ER diagram)](#Entity-Relationship-Diagram-(ER diagram))
- [Conclusion](#conclusion)
- [References](#references)
- [File Directory](#file_directory)

## Project Objective

- The objective of this project is to provide an overview on relational database management and how SQL is used to answer simple questions in the real world.

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

- **Create Real Tables:** After building the ER diagram, it's time to turn those entities into actual database tables. You'll create these tables, populate them with test data, and prepare to answer specific business questions.

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

## Entity Relationship Diagram (ER diagram)

The business rules defined above give us an overall process on how company works and develops an intuition how data might be recorded. We were able to develop some intuitions on how there are different types of relationships between various entities. For instance, Each credit account has multiple transactions. In other words, we can also say that, there is one entity 'Credit Account' that has more than single relationship with another entity maybe 'Transaction'. Therefore, it is safe to say that the Credit Account may have one-to-many relationship with Transaction. These types of relationships are used to develop an ER diagram. We will develop ER diagram and I will try to explain the different relationship through the example of an ER diagram. Please note, the verbs (may, must), the pronouns (Each, Every) used have some meaning to be considered, I would suggest to read a good article or book on how these relationships are defined in ER diagram.

Based on the above business rules, think of a table and how each data might be recorded in a table. For instance, after reading a business rule, I can think of a **Customer** table and it can have attributes such as Customer name, customer card details, customer's demographics. Also, think of how can we identify an indiividual customer. Therefore, we need a unique ID for customer, lets call it as may be *Customer ID*. Some of the examples of the tables I can think are given in this figure.

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/tables_attributes.png" width="500" height="300" />
</p>


You can create much more tables like this while you understand how the data is recorded in the company. After creating identify different relationships between these tables, for instance, assume that the "Customer can make multiple transactions but each transaction can be associated with one customer. Therefore, Customer has One-to-Many relationship with Transaction". There are three or four main relationships between tables:

1. One-to-One
2. One-to-Many
3. Many-to-Many

You can find the details of these relationships in the Reference section. Since the relationship between Customer and Trasaction is One-to-Many, we will denote it with the relationship line using Crow's Foot Notation (details in Reference section). It is the widely used technique for defining the relationship in ER diagrams. The pictorial representation is given below:

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/tables_attributes_2.png" width="500" height="300" />
</p>


Now, that you know on how you can built a relationship between tables, we can bulit much more tables and try to relate them with each other. However, you cannot go on building never ending tables and relationships. You also need to think about the storage space and structural issues for maintainance. Therefore, there is a technique used to organize data and data tables while designing a database. Usually, the technique used for DBMS is **Normalization** that helps in keeping data consistent and solves data integrity issues. There are different norm forms like 1NF, 2NF, 3NF and so on. You can find the detail in the Reference section. Following these techniques and collecting the knowledge of the entities-relationship from business rules, I have developed an Enahnced ER diagram (EER) using Lucid Chart. The details for each symbols and boxes representations are given in the References section.

<p align="center">
  <img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/EERD.png" width="500" height="300" />
</p>

