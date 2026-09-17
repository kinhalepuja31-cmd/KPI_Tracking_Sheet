# KPI_Tracking_Sheet
📌 Project Overview
This project is a dynamic, automated Sales Tracker and KPI Dashboard built to process and aggregate daily transaction logs cleanly. It separates raw data entry inputs from calculation engines to prevent accidental formula overwriting. It provides instant visibility into high-level business performance, category distribution, and item velocity.
📊 Core Performance KPIs
Based on the validated baseline dataset of 120 transactions (September 01, 2026 – September 30, 2026), the dashboard dynamically tracks:
•	Total Revenue: ₹450,000
•	Total Units Sold: 902
•	Average Order Value (AOV): ₹3,750
•	Top Performing Product: Bluetooth Speaker (Totaling ₹113,840)

🗂 Workbook Architecture & Schema
The workbook is split across isolated tabs to ensure complete structural clarity and data safety:
1. Raw Data
The source transaction ledger. Columns are strictly mapped as:
•	Date (YYYY-MM-DD format)
•	Product / Category (Validated drop-down menus)
•	Quantity (Validated positive integers)
•	Unit Price (Base cost)
•	Amount (Formula-driven engine: =Quantity * Unit Price)
•	Salesperson (Staff mapping)
2. Dashboard
An executive view displaying the 4 core KPI blocks alongside a comprehensive Product Category Performance Breakdown using criteria-filtered array logics (SUMIFS, AVERAGEIFS).
3. Daily / Weekly / Monthly Summaries
Rolling transaction aggregations broken down across individual days, fiscal weeks (Monday–Sunday rollups), and full-month horizons to observe conversion trend velocity.

⚙️ Implemented Formulas & Automation Logic
To keep the dashboard fully scalable without manual modifications, all calculation arrays use open-ended ranges (:) so that appending new rows automatically scales up the statistics:
•	Total Revenue Formula:
excel
=SUM('Raw Data'!F:F)
Use code with caution.
•	Category-Specific Sales:
excel
=SUMIFS('Raw Data'!F:F, 'Raw Data'!C:C, A2)
Use code with caution.
•	Category Average Order Value:
excel
=AVERAGEIFS('Raw Data'!F:F, 'Raw Data'!C:C, A2)
Use code with caution.
•	Dynamic Top Product Selector:
excel
=INDEX('Raw Data'!B:B, MATCH(MAX(SUMIF('Raw Data'!B:B, 'Raw Data'!B:B, 'Raw D

