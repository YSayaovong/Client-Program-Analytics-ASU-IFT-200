# Client & Program Analytics – ASU IFT 200

📘 **Course:** ASU – Information Modeling, Storage & Retrieval  
👤 **Student:** Yengkong Sayaovong  
🗓️ **Term:** Summer 2022  
🛠️ **Tools Used:** Python, SQLite, SQL, Jupyter Notebook, Excel

---

## 🔍 Project Overview

This project simulates the design, population, and querying of a real-world relational database for a nonprofit service organization. The goal was to build a normalized schema for tracking clients, programs, enrollments, and staff notes — and then run advanced SQL analytics on the system using Python and Jupyter.

---

## 🧱 Database Schema

The database includes four related tables:
- `Clients` – personal info
- `Programs` – services offered
- `Enrollments` – links clients to programs
- `Case_Notes` – staff records per client

A SQL **VIEW** was created to join all relevant data for easy querying.

---

## 🧠 Key Features

- ✅ Built SQLite database manually from Python
- ✅ Inserted and joined data across 4 normalized tables
- ✅ Created SQL view for unified reporting
- ✅ Used SQL filtering, grouping, subqueries, and JOINs
- ✅ Exported staff-specific reports dynamically to Excel

---

## 📊 Advanced SQL Queries

- Top clients by program enrollment
- Programs with more than one case note per client
- Clients below average program load
- Filter enrollments for 2024 only
- Export notes by staff name to Excel

---

## 📁 Files Included

| File | Description |
|------|-------------|
| `client_program.db` | SQLite database with all tables and data |
| `IFT200_Client_Analytics_Advanced.ipynb` | Full Jupyter Notebook with SQL analysis |
| `Notes_By_Emily.xlsx` | Sample Excel export from query |
| `dbdiagram.io model` | Visual entity relationship model (see below) |

---

## 🔗 ER Diagram (dbdiagram.io)
```dbml
Table Clients {
  ClientID int [pk]
  FirstName varchar
  LastName varchar
  Email varchar
  Phone varchar
}
Table Programs {
  ProgramID int [pk]
  Name varchar
  Type varchar
  StartDate date
  EndDate date
}
Table Enrollments {
  EnrollmentID int [pk]
  ClientID int [ref: > Clients.ClientID]
  ProgramID int [ref: > Programs.ProgramID]
  EnrollmentDate date
}
Table Case_Notes {
  NoteID int [pk]
  ClientID int [ref: > Clients.ClientID]
  NoteDate date
  Staff varchar
  Note text
}
