# Automated Overdue Invoice Email Reminder
### Power Automate | Excel Online | Office 365 Outlook | Kaggle Dataset

---

## Business Problem

In commercial collections environments, account managers manually review invoice spreadsheets daily and send follow-up emails to overdue clients one by one. This process is time-consuming, inconsistent, and prone to human error — delays in follow-up directly impact cash flow recovery.

---

## Solution

An automated Power Automate flow that runs on a daily schedule, scans a live B2B invoice dataset, identifies all overdue accounts, and sends personalised payment reminder emails automatically — eliminating manual intervention entirely.

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Power Automate | Flow automation and email trigger |
| Excel Online (OneDrive) | Live data source |
| Office 365 Outlook | Automated email delivery |
| Excel (Desktop) | Data cleaning and preparation |
| Kaggle — Customer Invoices Dataset | Real-world B2B invoice data |

---

## How It Works

```
Recurrence Trigger (Daily 9:00 AM)
        ↓
List Rows from Excel Table
        ↓
Apply to Each Row
        ↓
Condition: Status = "Overdue"?
        ↓
    YES → Send Email Reminder
    NO  → Skip
```

**Email includes:**
- Client name
- Invoice ID
- Amount outstanding
- Due date
- Payment arrangement request

---

## Dataset

- **Source:** Kaggle — [Customer Invoices Dataset](https://www.kaggle.com/datasets/pradumn203/payment-date-prediction-for-invoices-dataset)
- **Size:** 30 rows (cleaned from 50,000 row original)
- **Columns used:** Client Name, Customer No., Invoice ID, Due Date, Amount Outstanding, Payment Terms, Email, Status

---

## Data Cleaning (Excel)

The raw dataset (50,000 rows, 19 columns) required significant cleaning before use in Power Automate:

**Steps performed in Excel:**
- Removed 12 irrelevant columns (e.g. `doc_id`, `posting_id`, `buisness_year`)
- Added a client email column for automation testing
- Replaced binary `isOpen` column (0/1) with human-readable `Status` column (Overdue / Paid)
- Renamed all columns to business-friendly headers (e.g. `name_customer` → `Client Name`)
- Filtered to 30 representative rows (20 Overdue, 10 Paid)
- Formatted data as an Excel Table (`Table1`) for Power Automate compatibility

**Before cleaning:** 50,000 rows × 19 columns, binary status flags, no email column
**After cleaning:** 30 rows × 8 columns, readable status values, email column added, formatted as Table

---

## Results

- Flow runs automatically every day at 9:00 AM
- Successfully tested — flow executes and processes all 30 rows
- Eliminates approximately 45 minutes of daily manual follow-up work
- Scalable to any size invoice dataset

---

## Business Impact

> *"Automating the overdue invoice follow-up process reduces manual processing time by an estimated 45+ minutes per day, ensures consistent and timely client communication, and removes the risk of accounts being missed during high-volume periods."*

---

## Skills Demonstrated

- Business process automation (Power Automate)
- Data cleaning and transformation (Excel)
- End-to-end automation pipeline design
- Real-world dataset sourcing and preparation (Kaggle)
- Microsoft Power Platform (Power Automate, Excel Online, Outlook)
- Business problem identification and solution design

---

## Project Structure

```
overdue-invoice-automation/
│
├── README.md
├── data/
│   └── accounts_receivable_clean.xlsx
└── screenshots/
    ├── flow_diagram.png
    ├── excel_dataset.png
    ├── run_history.png
    └── email_sample.png
```

---

## Author

**Madhumitha Sethuraman**
Master of Business Information Systems — Swinburne University of Technology
[LinkedIn](#) | [GitHub](#)
