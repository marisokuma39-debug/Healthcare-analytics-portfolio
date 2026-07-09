# Project 2 : Pharmacy Inventory Analysis (Nigerian Hospital Dataset)

![Excel](https://img.shields.io/badge/Tool-Excel%20365-green) ![Domain](https://img.shields.io/badge/Domain-Healthcare%20Analytics-blue) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## Problem Statement

A Nigerian hospital with 5 branches needed a comprehensive review of its pharmacy inventory. Management wanted to understand stock levels, identify expired and expiring drugs, flag restocking needs, and assess total inventory value across branches and drug categories.

---

## Dataset

| Detail | Description |
|---|---|
| Records | 150 drug records (after duplicate removal) |
| Branches | Ikeja, Lekki, Yaba, Surulere, Abuja |
| Drug Categories | 15 categories across 30 unique drugs |
| Suppliers | 5 suppliers |
| Files | `raw_pharmacy.xlsx` / `cleaned_pharmacy.xlsx` |

---

## Tools Used

- **Microsoft Excel 365** — data cleaning, IF/IFERROR/TODAY() functions, COUNTIF/SUMIF/AVERAGEIF, pivot tables, conditional formatting, charts

---

## Data Cleaning Process

| Step | Action |
|---|---|
| 1 | Removed 3 duplicate drug records using Drug_ID as unique identifier |
| 2 | Standardised Stock Status from 7 inconsistent versions to 4 clean categories: In Stock, Low Stock, Out of Stock, Expired |
| 3 | Flagged 6 missing Unit Prices and 6 missing Stock Quantities instead of deleting affected rows |
| 4 | Calculated Days Until Expiry using TODAY() function to dynamically track expiry against current date |
| 5 | Created Expiry Risk flag: Expired / Expiring Soon (within 90 days) / OK |
| 6 | Calculated Stock Coverage Ratio (Stock Quantity ÷ Monthly Demand) to identify critically low and overstocked items |
| 7 | Calculated Inventory Value (Unit Price × Stock Quantity) per drug record |

---

## Analysis & Key Findings

### Finding 1 : 77% of Drug Records Are Expired
**116 out of 150 drug records (77%)** have passed their expiry date as of the analysis date. This represents a catastrophic stock management failure, the vast majority of current inventory cannot be safely dispensed to patients.

### Finding 2 : Only 16 Drug Records Have Safe Stock
With 116 expired and 18 expiring within 90 days, only **16 drug records** have genuinely safe, usable stock with more than 90 days remaining before expiry.

### Finding 3 : 19 Drugs Below Reorder Level
**19 drug records** are below their reorder level and require urgent restocking, including critical medicines:

| Critical Drug | Category |
|---|---|
| Ceftriaxone 1g | Antibiotic |
| Ciprofloxacin 500mg | Antibiotic |
| Paracetamol 500mg | Analgesic |
| Azithromycin 500mg | Antibiotic |
| Gentamicin Eye Drops | Ophthalmic |

### Finding 4 : Lekki Branch Has Highest Inventory Value
| Branch | Total Inventory Value (₦) |
|---|---|
| Lekki | 184,410,011 |
| Yaba | 175,491,834 |
| Surulere | 160,750,365 |
| Abuja | 150,745,195 |
| Ikeja | 137,891,944 |
| **Total** | **809,289,349** |

### Finding 5 : Antibiotics Dominate Drug Portfolio
Antibiotics account for **35 out of 150 drug records** and carry the highest total inventory value at **₦186,586,686** across all branches.

### Finding 6 : Stock Coverage Risk
- **21 drugs** have less than 0.5 months of stock remaining (critical stockout risk)
- **3 drugs** have more than 20 months of stock (overstocking risk)

---

##  Dashboard Preview

> ![Dashboard](dashboard_screenshot.png)

---

##  Recommendations

1. **Immediate stock audit** : Conduct a physical audit across all 5 branches and quarantine all expired drugs per NAFDAC guidelines.
2. **Emergency procurement** : Urgently reorder the 19 drugs below reorder level, prioritising antibiotics.
3. **Expiry management protocol** : Implement FIFO dispensing and monthly expiry checks.
4. **Overstock review** : Redistribute the 3 overstocked drugs to branches with critical shortages before expiry.
5. **Supplier review** : Evaluate NovaDrugs Abuja's reliability given the scale of expired stock.

---

##  Data Story

*Analysis of 150 drug records across 5 hospital branches reveals a pharmacy in serious inventory crisis. The most critical risk is expiry, 116 out of 150 drug records (77%) have already passed their expiry date, meaning the vast majority of current stock cannot be safely dispensed to patients. A further 18 drugs are expiring within the next 90 days, leaving only 16 drug records with safe stock levels. Compounding this, 19 drugs are below their reorder level, including essential antibiotics and analgesics, with 6 additional drugs showing no recorded stock quantity at all. Lekki Branch carries the highest inventory value at ₦184 million, but given the scale of expired stock across all branches, a significant portion of the total ₦809 million inventory value may represent worthless expired drugs rather than usable assets. We recommend an immediate physical stock audit across all branches, quarantine of all expired drugs per NAFDAC guidelines, and urgent procurement of the 19 drugs below reorder level, prioritising antibiotics, which dominate the hospital's drug portfolio at 35 records across all branches.*

---

##  New Skills Demonstrated

- TODAY() function for dynamic date calculations
- Inventory Value calculation (Price × Quantity)
- Stock Coverage Ratio, a real pharmacy KPI
- Multi-condition conditional formatting using formula-based rules
- Expiry risk flagging using nested IF logic

---

##  About

**Ogoma Okuma** | Biochemistry Graduate → Healthcare Data Analyst  
Building a portfolio in healthcare analytics using Excel, SQL, and Power BI.  
Email [marisokuma39@gmail.com] | Linkedin [www.linkedin.com/in/ogoma-okuma-a09ba4344] 

---

*This project is part of an ongoing Healthcare Analytics Portfolio. Dataset is simulated for learning purposes.*
