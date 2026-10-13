# 🩸 Blood Bank Management System (MySQL)

[![MySQL](https://img.shields.io/badge/Database-MySQL_8.0+-blue.svg?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![SQL Practice](https://img.shields.io/badge/SQL-Basic_to_Advanced-orange.svg)]()

A comprehensive MySQL relational database project designed to model, manage, and automate operations for a blood bank. This project demonstrates database schema design, normalization, triggers, stored procedures, views, performance indexing, and analytical SQL querying.

---

## 📌 Table of Contents
- [Overview](#-overview)
- [Key Features](#-key-features)
- [Database Architecture & ER Diagram](#-database-architecture--er-diagram)
  - [Entity-Relationship Diagram](#entity-relationship-diagram)
  - [Database Tables](#database-tables)
- [Advanced SQL Concepts Demonstrated](#-advanced-sql-concepts-demonstrated)
  - [Views](#1-views)
  - [Stored Procedures](#2-stored-procedures)
  - [Triggers](#3-triggers)
  - [Performance Indexing](#4-performance-indexing)
- [Repository Structure](#-repository-structure)
- [Getting Started & Installation](#-getting-started--installation)
- [Usage & Sample Queries](#-usage--sample-queries)
- [Limitations & Future Improvements](#-limitations--future-improvements)
- [Disclaimer & Author](#-disclaimer--author)

---

## 🔬 Overview

Managing a blood bank requires precise tracking of perishable stock, rapid response to urgent patient requests, and consistent record-keeping of donors and donations. 

This project implements a relational schema using **MySQL** that automates core stock deductions and donor date tracking using triggers, simplifies reporting using database views, encapsulates complex operations inside stored procedures, and provides a practice bank of 19 structured SQL queries across **Basic**, **Intermediate**, and **Advanced** difficulty levels.

---

## ✨ Key Features

- **Donor & Patient Management:** Track donor details, contact information, eligibility, and patient hospital requests.
- **Inventory & Expiry Control:** Track available units, collection dates, and expiry dates to prevent usage of expired stock.
- **Automated Workflow Automation:**
  - Automatically updates a donor's `last_donation_date` upon recording a new donation.
  - Automatically deducts issued units from `blood_stock` upon recording a blood issue.
- **Reusable Reporting Views:** Real-time visibility into non-expired stock, pending requests, donor details, and aggregated donation metrics.
- **Optimized Data Access:** Foreign key indexes and targeted query indexes for rapid data retrieval.

---

## 📐 Database Architecture & ER Diagram

### Entity-Relationship Diagram

The database consists of **7 relational tables** linked via primary and foreign key constraints. The ER diagram below outlines the core entities, attributes, and relationships across the system:

<p align="center">
  <img src="Blood%20Bank%20Management%20System.png" alt="Blood Bank Management System ER Diagram" width="100%">
</p>

### Database Tables

| Table Name | Description | Key Relationships |
| :--- | :--- | :--- |
| `blood_group` | Stores standardized blood types (e.g., A+, O-, AB+) | Referenced by `donor`, `patient`, `donation`, `blood_stock`, `blood_request` |
| `donor` | Stores registered blood donors | References `blood_group` |
| `patient` | Stores recipient details and hospital affiliations | References `blood_group` |
| `donation` | Logs historical blood donations per donor | References `donor`, `blood_group` |
| `blood_stock` | Manages physical inventory, quantities, and expiry dates | References `blood_group` |
| `blood_request` | Records incoming hospital/patient blood requests (`Pending`, `Completed`) | References `patient`, `blood_group` |
| `blood_issue` | Records fulfilled blood issue transactions | References `blood_request`, `blood_stock` |

---

## 🛠️ Advanced SQL Concepts Demonstrated

### 1. Views
Pre-built database views for abstracting complex joins and simplifying analytical queries:
- `available_blood_stock`: Filters available stock where `expiry_date >= CURDATE()`.
- `donor_details`: Joins donor profiles with blood group names.
- `pending_blood_requests`: Lists unfulfilled patient requests and hospital details.
- `blood_donation_summary`: Summarizes total donations and units collected per blood group.

### 2. Stored Procedures
- `add_donor(...)`: Standardized insertion of new donor records.
- `create_blood_request(...)`: Generates a new blood request with a default `Pending` status.
- `complete_blood_request(...)`: Updates request status to `Completed`.
- `check_
