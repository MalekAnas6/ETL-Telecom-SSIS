# 📊 ETL – Telecom Data Pipeline (Practice Project with SSIS)

📌 **Disclaimer:** This project is for **educational and practice purposes only**.  
It uses **dummy data** to simulate a telecom scenario.  
No real company data or sensitive information is included.  

---

## 🚀 Project Overview
This project demonstrates how to design and implement an **ETL (Extract, Transform, Load) pipeline** using **SQL Server Integration Services (SSIS)**.  

The goal was to simulate a telecom use case where customer activity data is stored in a CSV file every 5 minutes, then processed and loaded into SQL Server.

---

## 🛠 ETL Steps
1. **Extract**: Load data from CSV files.  
2. **Transform**:
   - Reject rows with missing mandatory values.
   - Perform lookups to map IMSI → Subscriber ID.
   - Split IMEI into `TAC` (first 8 chars) & `SNR` (last 6 chars).
   - Handle invalid or short values by replacing with `-99999`.
   - Validate timestamps.
   - Route invalid rows to a **Rejected Records** table with source filename.  
3. **Load**: Store clean data into the target SQL Server database.

---

## 📂 Repo Structure
- `docs/` → Project documentation (PDF).  
- `sql/` → SQL scripts (e.g., table creation).  
- `ssis/` → SSIS package file (.dtsx).  
- `samples/` → Example CSV input file.  

---

## 🖼 Example Data
| Column      | Description                                |
|-------------|--------------------------------------------|
| ID          | Transaction ID (primary key)               |
| IMSI        | Subscriber IMSI (reject if null)            |
| IMEI        | Device IMEI, split into TAC + SNR          |
| CELL        | Cell tower ID (reject if null)             |
| LAC         | Location area code (reject if null)        |
| EVENT_TYPE  | Event type (nullable)                      |
| EVENT_TS    | Event timestamp (validate format)           |

---

## 📑 Documentation
📄 Full details: [ETL_Telecom_Documentation.pdf](docs/ETL_Telecom_Documentation.pdf)

---

## ⚙️ Tools & Technologies
- SQL Server 2019  
- SQL Server Management Studio (SSMS)  
- SQL Server Integration Services (SSIS)  
- Visual Studio (for SSIS development)

---

## 🙋 About This Project
This is a **practice project** to learn ETL concepts and SSIS workflows.  
It does not represent real production data.  

---
