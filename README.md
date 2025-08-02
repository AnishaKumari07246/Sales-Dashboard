# 📘 Retail Sales Analysis-Excel-Sql-PowerBI

_Analyzing multi-country retail performance using Excel, SQL, and Power BI to uncover trends, drive insights, and enable data-driven decision making._

---

## 📑 Table of Contents

<a href="#overview">Overview</a>  
<a href="#business-problem">Business Problem</a>  
<a href="#dataset">Dataset</a>  
<a href="#tools--technologies">Tools & Technologies</a>  
<a href="#project-structure">Project Structure</a>  
<a href="#data-cleaning--preparation">Data Cleaning & Preparation</a>  
<a href="#exploratory-data-analysis-eda">Exploratory Data Analysis (EDA)</a>  
<a href="#research-questions--key-findings">Research Questions & Key Findings</a>  
<a href="#dashboard">Dashboard</a>  
<a href="#how-to-run-this-project">How to Run This Project</a>  
<a href="#final-recommendations">Final Recommendations</a>  
<a href="#author--contact">Author & Contact</a>  

---

<h2><a class="anchor" id="overview"></a>Overview</h2>

This project demonstrates a complete analytics solution for a multinational retail company using real-world tools like Excel, SQL (PostgreSQL), and Power BI. Data from six countries is cleaned, analyzed, and visualized for business stakeholders.

---

<h2><a class="anchor" id="business-problem"></a>Business Problem</h2>

Managers across multiple countries submit inconsistent and delayed sales reports. The goal is to automate this reporting, standardize the data, and deliver a centralized dashboard for leadership to make real-time decisions.

---

<h2><a class="anchor" id="dataset"></a>Dataset</h2>

- 6 CSV files (Canada, US, UK, China, Nigeria, India)  
- 15 Columns: `Transaction_ID`, `Date`, `Country`, `Product_ID`, `Product_Name`, `Price_per_Unit`, `Quantity`, `Cost_Price`, `Discount`, etc.  
- Data simulated to reflect real-world store operations

---

<h2><a class="anchor" id="tools--technologies"></a>Tools & Technologies</h2>

- 🟣 **Excel** – Raw data formatting & CSV conversion  
- 🟢 **PostgreSQL + pgAdmin** – Data cleaning, joins, and analytics  
- 🟡 **Power BI** – Live, shareable dashboard  
- ☁️ **Google Drive** – Backup automation for SQL database exports

---

<h2><a class="anchor" id="project-structure"></a>Project Structure</h2>

1. Prepare and format data in Excel  
2. Import into PostgreSQL  
3. Clean and transform data using SQL queries  
4. Merge data from all regions  
5. Analyze KPIs through SQL  
6. Visualize with Power BI

---

<h2><a class="anchor" id="data-cleaning--preparation"></a>Data Cleaning & Preparation</h2>

```sql
-- Find NULL values in important columns
SELECT * FROM sales_data
WHERE transaction_id IS NULL OR price_per_unit IS NULL;

-- Add and populate total_amount column
ALTER TABLE sales_data ADD COLUMN total_amount NUMERIC(10,2);
UPDATE sales_data SET total_amount = price_per_unit * quantity - discount;

-- Add and populate profit column
ALTER TABLE sales_data ADD COLUMN profit NUMERIC(10,2);
UPDATE sales_data SET profit = total_amount - (cost_price * quantity);
```

---

<h2><a class="anchor" id="exploratory-data-analysis-eda"></a>Exploratory Data Analysis (EDA)</h2>

```sql
-- Sales by Country
SELECT country, SUM(total_amount) AS revenue, SUM(profit) AS profit
FROM sales_data
GROUP BY country
ORDER BY revenue DESC;
```

- Weekly sales trends analyzed
- Category performance compared
- Discounts vs. Profits visualized per region

---

<h2><a class="anchor" id="research-questions--key-findings"></a>Research Questions & Key Findings</h2>

| Business Question | Answered With |
|-------------------|----------------|
| Which country has the most revenue? | SQL Query + Power BI Bar Chart |
| What are the top-selling products? | Quantity Aggregation |
| Where are discounts highest? | Scatter plot by store |
| Who are the top 5 sales reps? | Ranked by Total Profit |

---

<h2><a class="anchor" id="dashboard"></a>Dashboard</h2>

📊 ** Dashboard Preview**:

![Sales Dashboard](Snapshot%20of%20the%20Sales%20Dashboard.png)


### Key Visuals:
- 🌍 Sales by Store Location (Map)
- 📆 Monthly Trends (Line Chart)
- 💸 Total Revenue & Profit (KPIs)
- 🧾 Discount vs Profit (Scatter Plot)
- 🧮 Sales by Payment Method (Donut Chart)
- 🧍 Sales by Category & Month Type

📅 **Date Range Filter**: Jan 1, 2025 – Dec 31, 2025  
🔗 **Dashboard Status**: Ready for deployment via Power BI Service

---

<h2><a class="anchor" id="how-to-run-this-project"></a>How to Run This Project</h2>

1. Clone/download this repository  
2. Install PostgreSQL & Power BI Desktop  
3. Import the CSV files into your PostgreSQL database  
4. Run the provided SQL scripts  
5. Open `.pbix` file and refresh data  
6. Publish dashboard to Power BI Service if needed

---

<h2><a class="anchor" id="final-recommendations"></a>Final Recommendations</h2>

- Schedule weekly data refresh in Power BI  
- Automate Google Drive backups for PostgreSQL  
- Use Power BI bookmarks for different stakeholder views  
- Consider RLS (Row-Level Security) for region-based user access

---

<h2><a class="anchor" id="author--contact"></a>Author & Contact</h2>

**Author**: (Anisha Kumari) 

**Email**:  (anishakr9090@gmail.com) 
 
 **LinkedIn**: (https://www.linkedin.com/in/anisha-kumari-ba543b21b/) 
 

---
