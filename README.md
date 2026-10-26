# 🏦 Bank Customer Analysis Using Python and SQL

## Customer Accounts, Transaction Analysis & Banking Insights

## 📌 Project Overview

This project analyzes sample banking data to understand customer account details, account balances, transaction activities, account relationships, and banking trends.

The analysis was performed using **Python, SQLite, Pandas, Matplotlib, and Seaborn**. SQL queries were used to retrieve, filter, aggregate, and combine data from multiple relational tables, while Python libraries were used to process query results and visualize key patterns.

The main goal of this project is to organize banking data, solve practical SQL problems, explore account and transaction patterns, and present the results through meaningful visualizations and business-oriented insights.

---

## 🎯 Objectives

The project aims to:

- Analyze customer details and account information
- Calculate average account balances for each customer
- Examine account types and account statuses
- Retrieve transaction records for specific date ranges
- Analyze deposits, withdrawals, and transaction amounts
- Identify relationships between savings accounts, credit cards, and add-on credit cards
- Handle missing balance values using transaction data where applicable
- Calculate adjusted balances by accounting for negative transactions
- Analyze monthly transaction trends
- Explore customer distribution across states
- Visualize banking data and derive useful insights

---

## ❓ Business Questions

1. What is the average account balance maintained by each customer?
2. How can transaction amounts be used when a credit card balance is missing?
3. Which transactions occurred during March and April 2020?
4. Which transactions occurred outside March 2020?
5. Which accounts recorded transactions during the first quarter of 2020?
6. Which savings accounts are associated with specific customer messages and events?
7. What are the adjusted balances of primary accounts after accounting for negative transactions?
8. How are accounts connected to their corresponding linked accounts?
9. What transaction amounts are associated with linked accounts?
10. Which savings account holders have credit cards and add-on credit cards?
11. What is the aggregate transaction amount for credit cards linked to savings accounts?
12. Which customers maintain the highest average account balances?
13. Which account types are most common in the dataset?
14. How do total transaction amounts vary by month?
15. How are customers distributed across different states?
16. How do total account balances compare between active and inactive accounts?

---

## 🗂️ Dataset

The project uses sample banking data organized into relational database tables.

### Main Tables

| Table | Description |
|---|---|
| `BANK_CUSTOMER` | Stores customer IDs, names, addresses, state codes, and telephone numbers |
| `BANK_CUSTOMER_EXPORT` | Stores exported customer records |
| `BANK_ACCOUNT_DETAILS` | Contains customer account numbers, account types, balances, statuses, and relationship types |
| `BANK_ACCOUNT` | Stores account-level information, including balances and statuses |
| `BANK_ACCOUNT_RELATIONSHIP_DETAILS` | Records relationships between linked accounts |
| `BANK_ACCOUNT_TRANSACTION` | Contains transaction amounts, transaction channels, provinces, and transaction dates |
| `BANK_CUSTOMER_MESSAGES` | Stores customer messages and event information |
| `BANK_INTEREST_RATE` | Stores banking interest rate information |

### Key Columns

| Column | Description |
|---|---|
| `customer_id` | Unique customer identifier |
| `customer_name` | Customer name |
| `Account_Number` | Bank account number |
| `Account_type` | Type of account, such as savings or recurring deposit |
| `Balance_amount` | Account balance |
| `Account_status` | Indicates whether an account is active or inactive |
| `Relationship_type` | Identifies primary (`P`) or secondary (`S`) relationships |
| `Transaction_amount` | Transaction value, which may be positive or negative |
| `Transaction_Date` | Date on which a transaction occurred |
| `Linking_Account_Number` | Account number associated with another account |

> Note: The notebook contains sample records with transactions primarily dated in 2020. The analysis reflects the supplied sample data rather than a live banking system.

---

## 🛠️ Tools & Technologies

- **Python** — Data processing and analysis
- **SQLite** — Relational database creation and management
- **SQL** — Data retrieval, filtering, aggregation, and joins
- **Pandas** — Query result handling and tabular analysis
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical charts and visual exploration
- **Google Colab** — Notebook development and execution
- **GitHub** — Project version control and documentation

---

## 🔄 Project Workflow

```text
Database Setup
      ↓
Table Creation
      ↓
Data Insertion
      ↓
Data Validation
      ↓
SQL Query Development
      ↓
Data Filtering and Aggregation
      ↓
Table Joins and Relationship Analysis
      ↓
Data Visualization
      ↓
Insight Generation
      ↓
Business Recommendations
```

---

## 🗄️ Database Setup and Data Preparation

The project uses SQLite to create and manage a relational database.

The following steps were performed:

- Connected Python to an SQLite database
- Configured the database file location in Google Colab and Google Drive
- Created database tables for customers, accounts, transactions, messages, and interest rates
- Inserted sample customer, account, relationship, and transaction records
- Used parameterized SQL statements to insert records
- Retrieved table names and checked row counts to verify database contents
- Used Pandas to execute SQL queries and display the results

---

## 🔍 SQL Analysis and Query Development

### 1. Average Account Balance per Customer

Joined customer and account tables to calculate the average account balance for each customer.

**Purpose:** Compare average account balances across customers who maintain one or more accounts.

### 2. Handling Missing Credit Card Balances

Used `COALESCE()` with a `LEFT JOIN` to return the available account balance or use the corresponding transaction amount when the balance is `NULL` for credit card accounts.

**Purpose:** Demonstrate how SQL can handle missing values while retrieving account information.

### 3. Transactions During March and April 2020

Filtered transaction records using date conditions and joined account details with transaction data.

**Purpose:** Retrieve account numbers, balances, transaction amounts, and transaction dates for the specified period.

### 4. Transactions Excluding March 2020

Used date filters to retrieve transactions occurring before March or from April onward.

**Purpose:** Practice date-based filtering and exclusion of a specific month.

### 5. First-Quarter Transaction Analysis

Filtered transactions between January 1 and March 31, 2020, and retrieved the associated customer and account details.

**Purpose:** Identify accounts with recorded transactions during the first quarter.

### 6. Customer Messages and Account Events

Combined savings account records with customer message records and filtered for the `Adhoc` event.

**Purpose:** Practice combining tables and applying conditions to retrieve relevant account and event information.

### 7. Adjusted Balances for Primary Accounts

Used `CASE`, `SUM()`, and `COALESCE()` to account for negative transaction amounts when calculating adjusted balances for primary accounts (`P`).

**Purpose:** Demonstrate conditional aggregation and balance calculations using SQL.

### 8. Account and Relationship Analysis

Used `LEFT JOIN` to retrieve account details, account types, transaction amounts, and linked account information.

**Purpose:** Understand how different accounts are connected and how transaction records can be combined with relationship data.

### 9. Transactions for Linked Accounts

Extended the account relationship query by joining transaction data for both the original account and its linked account.

**Purpose:** Compare transaction information across related accounts.

### 10. Savings Accounts with Credit Cards and Add-on Cards

Used multiple joins to identify savings accounts linked to credit cards and add-on credit cards.

**Purpose:** Explore account relationships and identify connected banking products.

### 11. Aggregate Transactions for Linked Credit Cards

Used `SUM()` and `GROUP BY` to calculate aggregate transaction amounts for credit cards linked to savings accounts.

**Purpose:** Analyze transaction activity across related banking products.

---

## 📊 Data Visualization

The notebook includes six visualizations created using Matplotlib and Seaborn.

### 1. Average Account Balance per Customer

A bar chart compares the average account balance across customers.

**Purpose:** Highlight differences in average account balances.

### 2. Number of Accounts by Account Type

A bar chart displays the number of accounts in each account category.

**Purpose:** Compare the representation of savings accounts, recurring deposits, credit cards, and other account types present in the data.

### 3. Monthly Transaction Amount

A line chart shows the net transaction amount for each month.

**Purpose:** Explore monthly changes in transaction activity and identify periods with positive or negative net transaction amounts.

### 4. Distribution of Transaction Amounts

A histogram with a density curve displays the distribution of transaction values.

**Purpose:** Examine the spread of transaction amounts and compare positive and negative values.

### 5. Customer Distribution by State

A pie chart visualizes the proportion of customers associated with each state code.

**Purpose:** Understand the geographical distribution of customers represented in the sample.

### 6. Total Balance by Account Status

A bar chart compares the total account balance for active and inactive accounts.

**Purpose:** Examine how account balances are distributed across account statuses.

---

## 💡 Key Insights

Based on the analyses and visualizations included in the notebook, the project explores the following areas:

- **Customer balances:** Compares average account balances across individual customers.
- **Account distribution:** Identifies the number of accounts across different account types.
- **Transaction trends:** Examines monthly changes in net transaction amounts.
- **Transaction behavior:** Visualizes the distribution of positive and negative transaction values.
- **Customer geography:** Compares customer counts across state codes.
- **Account status:** Evaluates total balances associated with active and inactive accounts.
- **Account relationships:** Identifies savings accounts connected to credit cards and add-on credit cards.
- **SQL-based data retrieval:** Demonstrates how joins, aggregations, conditional expressions, and date filters can answer practical banking questions.

*Note: Specific numerical findings and rankings should be reported only after validating the relevant query outputs and charts.*

---

## 📈 Business Recommendations

Based on the types of analysis performed, the following are potential recommendations for a banking business:

### 1. Monitor Account Balances

Use customer-level balance summaries to identify account balance patterns and determine where further customer or product analysis may be useful.

### 2. Review Account Distribution

Analyze account counts by type to understand the composition of the account portfolio and guide further product-level investigation.

### 3. Track Transaction Trends

Monitor monthly transaction activity to identify unusual changes and periods that may require closer examination.

### 4. Improve Data Quality

Validate missing balances, inconsistent account types, duplicate records, and incomplete customer-account relationships before using the data for operational decisions.

### 5. Understand Connected Banking Products

Analyze the relationships between savings accounts, credit cards, and add-on cards to better understand how customers use connected banking products.

### 6. Compare Active and Inactive Accounts

Review account statuses and associated balances to support account monitoring and identify records that require further investigation.

### 7. Strengthen Transaction Reporting

Use SQL aggregations and date filters to create consistent transaction summaries for monthly and quarterly reporting.

---

## 🧠 What I Learned

Through this project, I practiced the following skills:

- Creating and connecting to SQLite databases
- Creating relational database tables and inserting records
- Retrieving data using SQL queries
- Applying `WHERE`, `ORDER BY`, and date filters
- Using aggregate functions such as `SUM()`, `AVG()`, and `COUNT()`
- Applying `GROUP BY` and conditional logic with `CASE`
- Handling missing values with `COALESCE()`
- Combining tables using `INNER JOIN`, `LEFT JOIN`, and multiple joins
- Analyzing relationships between customers, accounts, and transactions
- Executing SQL queries through Pandas
- Creating bar charts, line charts, histograms, and pie charts
- Interpreting query outputs and translating analysis into potential business recommendations

---

## 📁 Project Structure

```text
Bank-Customer-Analysis-Python-SQL/
│
├── bank_practise.ipynb
├── my_database.db
└── README.md
```

*The database file is optional if the notebook creates and populates the database during execution. Include it in the repository only if you intend to share the database itself.*

---

## 🚀 Future Improvements

The project can be extended by adding:

- A Power BI dashboard for interactive banking reports
- Customer segmentation based on account and transaction behavior
- More detailed deposit and withdrawal analysis
- Customer-level transaction summaries
- Data quality checks for missing, duplicate, or inconsistent records
- Account balance and transaction reconciliation
- Profitability analysis, where suitable data is available
- More advanced SQL queries and performance optimization
- Automated reporting and scheduled data updates

---

## 👩‍💻 About Me

**Lina Rushvana**  
BCA Graduate | Aspiring Data Analyst

### Skills Practiced

Python · SQL · SQLite · Pandas · Matplotlib · Seaborn · Data Analysis · Data Visualization · Exploratory Data Analysis

---

## ⭐ Project Purpose

This project was developed as part of my learning journey toward becoming a Data Analyst.

The focus was to practice an end-to-end data analysis workflow using relational banking data, write SQL queries to answer practical account and transaction questions, visualize important patterns, and understand how structured data can support business reporting and decision-making.
