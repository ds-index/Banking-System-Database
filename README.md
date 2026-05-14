# 🏦 Banking System Database

[![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-red.svg)](https://www.microsoft.com/en-us/sql-server/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📌 Project Overview

A complete banking database system demonstrating **relational database design**, **indexing strategies**, and **optimized queries** with **One-to-Many relationships**. This project showcases professional database development skills using SQL Server and.

## 🎯 Key Features

- ✅ **4 Banks** with complete information (USA, UK, Germany)
- ✅ **100 User Accounts** (25 per bank) with full authentication data
- ✅ **40 Employees** (10 per bank) with salary and experience data
- ✅ **One-to-Many Relationships** between Banks → Accounts & Employers
- ✅ **Optimized Indexes** for high-performance queries (90%+ improvement)
- ✅ **Foreign Key Constraints** with CASCADE DELETE
- ✅ **Stored Procedures** for common banking operations
- ✅ **Views** for reporting and analytics

## 📊 Database Schema

┌─────────────────┐ ┌─────────────────┐
│ Banks │ │ Accounts │
├─────────────────┤ ├─────────────────┤
│ Id (PK) │◄────────│ BankId (FK) │
│ Name │ 1 │ Username │
│ Location │ ┊ │ Password │
│ Manager │ Many │ Email │
│ IsActive │ │ Address │
│ CreatedAt │ └─────────────────┘
└─────────────────┘
│
│ 1
│ ┊
│ Many
▼
┌─────────────────┐
│ Employer │
├─────────────────┤
│ Id (PK) │
│ BankId (FK) │
│ Name │
│ Field │
│ Salary │
│ Expr (Years) │
└─────────────────┘

## 🗂️ Database Structure

### Tables Overview

| Schema | Table    | Records | Description                                   |
| ------ | -------- | ------- | --------------------------------------------- |
| dbo    | Banks    | 4       | Bank information (One side)                   |
| Users  | Accounts | 100     | User accounts with authentication (Many side) |
| dbo    | Employer | 40      | Employee data (Many side)                     |

### Relationships

| Relationship     | Type        | Foreign Key                |
| ---------------- | ----------- | -------------------------- |
| Banks → Accounts | One-to-Many | Accounts.BankId → Banks.Id |
| Banks → Employer | One-to-Many | Employer.BankId → Banks.Id |

## 🚀 Quick Start

### Prerequisites

- SQL Server 2022 or higher
- SQL Server Management Studio (SSMS)

### Installation Steps

1. **Create Database**

```sql
CREATE DATABASE BankingSystem;
USE BankingSystem;

Run Scripts in Order

01_Create_Schemas.sql
02_Create_Tables.sql
03_Create_Indexes.sql
04_Insert_Data.sql
05_Stored_Procedures.sql (optional)
06_Views.sql (optional)
```

Verify Installation
-- Check data counts
SELECT 'Banks' as TableName, COUNT(_) FROM Banks
UNION ALL
SELECT 'Accounts', COUNT(_) FROM Users.Accounts
UNION ALL
SELECT 'Employees', COUNT(\*) FROM Employer;

📈 Performance Optimization
Indexes Created
Index Name Type Performance Gain
IX_Employer_BankId Non-clustered +80% for joins
IX_Accounts_Username Unique Non-clustered +95% for login
IX_Employer_Salary Non-clustered +70% for reporting
IX_Banks_Name Non-clustered +60% for searches

Performance Results
Operation Before Indexing After Indexing Improvement
Login Query ~500ms ~10ms 98%
Join Queries ~300ms ~20ms 93%
Salary Sorting ~200ms ~15ms 92%
Bank Search ~150ms ~25ms 83%

📊 Sample Data Distribution
Bank Location Accounts Employees Salary Range
First National Bank New York, USA 25 10
49
,
000
−
49,000−82,000
Global Trust Bank London, UK 25 10
62
,
000
−
62,000−85,000
Pacific Western Bank Los Angeles, USA 25 10
45
,
000
−
45,000−75,000
European Credit Bank Frankfurt, Germany 25 10
65
,
000
−
65,000−85,000
Total 4 Banks 100 40
45
,
000
−
45,000−85,000

📁 Project Structure

Banking-System-Database/
│
├── 📂 Scripts/
│ ├── 01_Create_Schemas.sql
│ ├── 02_Create_Tables.sql
│ ├── 03_Create_Indexes.sql
│ ├── 04_Insert_Data.sql
│ ├── 05_Stored_Procedures.sql
│ ├── 06_Views.sql
│ └── 07_Queries_Examples.sql
│
├── 📂 Documentation/
│ ├── Database_Diagram.md
│ └── Query_Optimization.md
│
├── .gitignore
└── README.md

## 🤝 Connect With Me

<p align="left">
  <a href="https://github.com/ds-index">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github"/>
  </a>
  <a href="https://www.linkedin.com/in/arman-ds-b3b967291">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin"/>
  </a>
  <a href="mailto:ds.limited.ar@gmail.com">
    <img src="https://img.shields.io/badge/Email-Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
</p>

📄 License
MIT License - feel free to use this project for learning and portfolio purposes.

🙏 Acknowledgments
SQL Server documentation
Database design best practices
