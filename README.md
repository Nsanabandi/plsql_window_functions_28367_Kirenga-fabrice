SQL JOINs and Window Functions Analysis
KIFA Technology Company
Project Overview

This project applies SQL JOINs and Window Functions to analyze business data for KIFA, a technology company that develops fully featured web and mobile applications. The goal of the project is to demonstrate correct database design, relational querying, and analytical SQL techniques using Oracle Database.

The analysis focuses on understanding customer activity, product performance, and sales trends in order to support informed business decisions.

Step 1: Problem Definition
Business Context

KIFA operates in the technology industry, providing web and mobile application development services to clients across different regions. The analysis is conducted from a business analytics perspective to support sales and customer performance evaluation.

Data Challenge

KIFA collects transactional data from multiple customers and products, but raw data alone does not provide insight into performance trends, customer behavior, or revenue contribution. Without structured analysis, it is difficult to identify top customers, inactive customers, or sales patterns over time.

Expected Outcome

The analysis aims to generate insights that help management:

Identify top-performing customers and products

Understand revenue distribution across regions

Track sales trends over time

Segment customers for strategic decision-making

Step 2: Success Criteria

The following five measurable goals are implemented using SQL window functions:

Identify top customers by revenue using RANK()

Calculate running totals of sales using SUM() OVER()

Compare current and previous sales periods using LAG()

Segment customers into quartiles using NTILE(4)

Analyze trends using moving aggregate calculations

Each goal is directly linked to a specific SQL analytic function.

Step 3: Database Schema Design
Tables and Attributes

KIFA_CUSTOMERS

customer_id (Primary Key)

customer_name

region

KIFA_PRODUCTS

product_id (Primary Key)

product_name

product_type

KIFA_TRANSACTIONS

transaction_id (Primary Key)

customer_id (Foreign Key)

product_id (Foreign Key)

amount

transaction_date

Relationships

One customer can have multiple transactions

One product can be associated with multiple transactions

An ER diagram (Chen notation) is included to illustrate entities, attributes, and relationships.

Step 4: SQL JOINs Implementation

The following JOIN types were implemented and tested using Oracle SQL:

INNER JOIN

Used to retrieve transactions that have valid customer and product records. This ensures only confirmed business activity is analyzed.

LEFT JOIN

Used to identify customers who have never made a transaction. This helps detect inactive or potential customers.

FULL OUTER JOIN

Used to compare customers and products while including unmatched records. This reveals missing relationships in the data.

SELF JOIN

Used to compare customers within the same region, enabling intra-regional analysis.

Each JOIN includes:

SQL query with comments

Screenshot of the result

Brief business interpretation

Step 5: Window Functions Implementation
Ranking Functions

RANK() is used to rank customers based on total revenue, allowing identification of top contributors.

Aggregate Window Functions

SUM() OVER() is used to compute running totals, enabling trend analysis over time.

Navigation Functions

LAG() is used to compare sales between consecutive periods, supporting growth and decline analysis.

Distribution Functions

NTILE(4) is used to divide customers into quartiles based on revenue, enabling customer segmentation.

Each function includes:

SQL query

Result screenshot

Interpretation of the output

Step 7: Results Analysis
Descriptive Analysis (What happened?)

The data shows that revenue is unevenly distributed, with a small number of customers contributing a large share of total sales.

Diagnostic Analysis (Why did it happen?)

High-value customers tend to purchase premium services more frequently, while some customers remain inactive or make low-value transactions.

Prescriptive Analysis (What should be done?)

KIFA should focus on retaining high-value customers, re-engage inactive customers through targeted offers, and monitor sales trends to improve forecasting and planning.

Repository Structure
plsql_window_functions_28367_Kirenga-fabrice/
│
├── README.md
├── sql/
│   ├── create_tables.sql
│   ├── insert_data.sql
│   ├── joins.sql
│   └── window_functions.sql
└── screenshots/
    ├── erd.png
    ├── join_results.png
    └── window_function_results.png

References

Oracle Corporation. Oracle Database SQL Language Reference.
https://docs.oracle.com/en/database/oracle/oracle-database/

Oracle Corporation. Analytic Functions.
https://docs.oracle.com/en/database/oracle/oracle-database/21/sqlrf/Analytic-Functions.html

Silberschatz, A., Korth, H. F., & Sudarshan, S. Database System Concepts.

Integrity Statement

I confirm that this project is my original work. All SQL queries, database design, and analysis were completed independently and in accordance with academic integrity requirements.
