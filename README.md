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

## Database Architecture

### ER Diagram

The entity-relationship model and relational database design are illustrated below:

<p align="center">
  <img src="Blood%20Bank%20Management%20System.png" alt="Blood Bank Management System ER Diagram" width="100%">
</p>

### Database Tables

The project contains seven tables linked via primary and foreign key constraints:

1. **`blood_group`**: Stores blood group identifiers and names.
2. **`donor`**: Stores donor details, contact information, and blood group references.
3. **`patient`**: Stores patient details, hospital information, and required blood groups.
4. **`donation`**: Records blood donation history, units donated, and dates.
5. **`blood_stock`**: Tracks available blood inventory, collection dates, and expiry dates.
6. **`blood_request`**: Stores patient blood requests, required units, and request status (`Pending` / `Completed`).
7. **`blood_issue`**: Tracks blood issued against specific requests and stock records.

---

## SQL Concepts Used

- Database and table creation
- Primary key and foreign key constraints
- `INSERT` and `UPDATE` statements
- `INNER JOIN` and `LEFT JOIN`
- `WHERE` and `DISTINCT`
- `GROUP BY` and `HAVING`
- Aggregate functions: `COUNT`, `SUM`, `AVG`, and `MAX`
- Subqueries
- `IFNULL` and `CURDATE` functions
- Index creation
- Views
- Stored procedures with input parameters
- `AFTER INSERT` triggers
- SQL aliases and relational data retrieval

---

## Database Objects

### Views

| View Name | Description |
|---|---|
| `available_blood_stock` | Displays available, non-expired blood stock. |
| `donor_details` | Displays donor information merged with blood group names. |
| `pending_blood_requests` | Displays pending blood requests with patient and hospital details. |
| `blood_donation_summary` | Summarizes total donations and donated units by blood group. |

### Stored Procedures

| Procedure Name | Purpose |
|---|---|
| `add_donor` | Inserts a new donor record. |
| `create_blood_request` | Creates a new blood request with pending status. |
| `complete_blood_request` | Marks a pending blood request as completed. |
| `check_blood_stock` | Calculates available units for a specific blood group. |

### Triggers

| Trigger Name | Purpose |
|---|---|
| `trg_update_donor_last_donation` | Updates the donor's `last_donation_date` after a donation record is inserted. |
| `trg_deduct_blood_stock` | Deducts issued units from the corresponding stock record after a blood issue is inserted. |

### Indexes

Ten indexes are created on selected donor, patient, donation, blood stock, blood request, and blood issue columns to optimize data retrieval and query execution.

---

## Repository Structure

```text
Blood-Bank-Management-System/
├── BLOOD BANK MANAGEMENT SYSTEM.sql   # Complete SQL script containing tables, views, procedures, triggers & queries
├── Blood Bank Management System.png   # ER Diagram reference image
└── README.md                          # Documentation
