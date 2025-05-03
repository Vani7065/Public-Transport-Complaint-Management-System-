# 🚍 Public Transport Complaint Management System

An academic DBMS mini-project to manage and resolve public transport complaints efficiently.

## 📘 Overview

This project is designed to manage complaints related to public transport through a centralized database system. It handles complaint registration by users, administrative responses, and transport-related details using structured SQL and PL/SQL logic.

## ✨ Features

- User registration and login
- Complaint submission with category and description
- Complaint tracking with status updates
- Admin panel to reply to complaints
- Database triggers and procedures to automate processes

## 🗃️ Database Design

### Tables:
- `User(UserID, Name, Gender, PhoneNumber, Email, Password)`
- `Complaint(ComplaintID, UserID, Type, Description, ComplaintDate, Status)`
- `Transport(TransportID, VehicleType, VehicleNumber, Route, DriverName)`
- `Admin(AdminID, Name, Email, Password)`
- `Reply(ReplyID, ComplaintID, AdminID, ReplyText, ReplyDate)`

### PL/SQL:
- Triggers to auto-update complaint status
- Procedures to handle complaint resolution and logging

## 💻 Sample Queries

```sql
-- Fetch all unresolved complaints
SELECT * FROM Complaint WHERE Status = 'Pending';

-- List complaints with user and vehicle info
SELECT U.Name, C.Type, C.Description, T.VehicleNumber
FROM Complaint C
JOIN User U ON C.UserID = U.UserID
JOIN Transport T ON C.Type = T.VehicleType;

How to Use
1. Run the SQL scripts to create tables.

2. Execute the PL/SQL scripts for triggers and procedures.

3. Insert test data or use the UI (if available).

4. Query the database using SQL tools or a frontend app.

