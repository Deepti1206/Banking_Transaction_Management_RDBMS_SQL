# Banking_Transaction_Management_RDBMS_SQL

## Table of Contents
- [Project Objective](#project-objective)
- [Problem Statement](#problem-statement)
- [Business Understanding](#business-understanding)
- [Background](#background)
- [Business Questions](#business-questions)
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

<img src="https://github.com/Deepti1206/Banking_Transaction_Management_RDBMS_SQL/blob/main/Images/rdbms_image.jpg" width="600" height="200" align="center">

## Background

As a Database Administrator, your role is develop an efficient and scalable database that will help company achieve their goal in terms of managing data. In order to do that first you need to start understanding what the company does, what are they looking for, what services they offer, what data they have, what are the types of data, how they are collecting it, what systems they have, what is their end goal in terms of data output and so on. Some of the questions are given in the ##Business Questions## section.

After you record all the answers to your question, you need to define business rules. Business rules in the context of an Entity-Relationship (ER) diagram are constraints and guidelines that define how data is stored, processed, and managed within a database system. These rules are essential for maintaining data integrity, ensuring accuracy, and adhering to business requirements. For instance, #An employee can only be assigned to one department#. We will explore more further in the project.

Now, you have your business rules, you need to start working on designing a structure on how data will be stored. Think this like a blue print or diagram of the company. The best method that people feel that data and organisation is represented by the Entity Relationship diagram (commonly known as ER or Enhanced-ER diagram). An Entity-Relationship (ER) diagram is a visual representation used in database design to illustrate the logical structure of a database. It is a modeling technique that helps in defining and representing the relationships between entities (also known as tables) within a database. ER diagrams are a fundamental tool in database design, allowing database designers and stakeholders to visualize the database schema and its relationships. In this project, the entities are the different areas where the XYZ Fintech is doing business with. This diagram is so powerful that it represents how the relationships are between these different areas. We will go in details in the upcoming sections.

Once you build an ER diagram, it's time to define each entities. Now think of this like each entities are tables and each table has some attributes that represent columns in your data. Based on this, we will define relations and important features and then go on to create real tables, fill in dummy data and solve some interesting business questions.

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


