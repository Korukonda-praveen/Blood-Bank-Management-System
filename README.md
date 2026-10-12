# Blood Bank Management System using MySQL

## Project Overview

The **Blood Bank Management System** is a database management project developed using MySQL to manage blood donors, patients, donations, blood stock, blood requests, and blood issue records.

The project demonstrates relational database design and SQL programming through tables, constraints, indexes, views, stored procedures, triggers, and basic, intermediate, and advanced SQL queries.

## Features

- Management of blood groups, donors, and patients
- Recording blood donations
- Tracking blood stock and expiry dates
- Managing blood requests and their status
- Recording blood issue transactions
- Viewing available, non-expired blood stock
- Summarizing donations by blood group
- Retrieving pending blood requests
- Automatically updating a donor's last donation date
- Automatically deducting issued units from blood stock
- Improving data retrieval with indexes
- Practicing SQL queries at three difficulty levels

## Database Tables

The project contains seven tables:

1. `blood_group`
2. `donor`
3. `patient`
4. `donation`
5. `blood_stock`
6. `blood_request`
7. `blood_issue`

Primary keys and foreign keys establish relationships between the tables. The schema also includes a unique constraint and ENUM data types.

## SQL Concepts Used

- Database and table creation
- Primary and foreign key constraints
- INSERT and UPDATE statements
- INNER JOIN and LEFT JOIN
- WHERE and DISTINCT
- GROUP BY and HAVING
- Aggregate functions: COUNT, SUM, AVG, and MAX
- Subqueries
- IFNULL and CURDATE functions
- Index creation
- Views
- Stored procedures with input parameters
- AFTER INSERT triggers
- SQL aliases and relational data retrieval

## Views

The project includes four views:

1. `available_blood_stock`: Displays available, non-expired blood stock.
2. `donor_details`: Displays donor information with blood group names.
3. `pending_blood_requests`: Displays pending blood requests with patient and hospital details.
4. `blood_donation_summary`: Summarizes donations and donated units by blood group.

## Stored Procedures

Four stored procedures are implemented:

| Procedure | Purpose |
|---|---|
| `add_donor` | Inserts a new donor record |
| `create_blood_request` | Creates a pending blood request |
| `complete_blood_request` | Marks a blood request as completed |
| `check_blood_stock` | Calculates available units for a blood group |

## Triggers

Two triggers automate database updates:

| Trigger | Purpose |
|---|---|
| `trg_update_donor_last_donation` | Updates the donor's last donation date after a donation record is inserted |
| `trg_deduct_blood_stock` | Deducts issued units from the corresponding stock record after a blood issue is inserted |

## Indexes

Ten indexes are created on selected donor, patient, donation, blood stock, blood request, and blood issue columns to support data retrieval.

## SQL Query Practice

The project contains 19 numbered queries organized into three levels:

- **Basic Queries:** Q1–Q8
- **Intermediate Queries:** Q9–Q15
- **Advanced Queries:** Q16–Q19

These queries cover data retrieval, filtering, joins, grouping, aggregate calculations, and subqueries.

## Technologies Used

- MySQL
- SQL
- MySQL stored procedures and triggers

## How to Run

1. Install MySQL and open MySQL Workbench or another compatible MySQL client.
2. Open the `BLOOD BANK MANAGEMENT SYSTEM.sql` file.
3. Execute the script in sections, starting with database and table creation.
4. Review the sample data, indexes, views, stored procedures, and triggers.
5. Run the query bank to explore the database.
6. Use `SHOW TABLES;`, `SHOW FULL TABLES WHERE TABLE_TYPE = 'VIEW';`, and `SHOW TRIGGERS;` to inspect the created objects.

**Note:** The script begins with `DROP DATABASE IF EXISTS`, so running it from the beginning recreates the database and removes any existing data in that database.

## Learning Outcomes

This project demonstrates practical understanding of relational database design, SQL query writing, data aggregation, indexing, stored procedures, and trigger-based automation using MySQL.
