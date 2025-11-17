# 🍫 Chocolate Sales Analysis – Power BI Dashboard

## 📌 Project Overview

This project is a **comprehensive end-to-end Power BI analysis** of a global chocolate sales dataset covering **1,094 sales transactions** across **6 countries** and **25 salespersons**.

The dashboard provides a **business-focused view** of:

* Revenue performance
* Product profitability patterns
* Country-level insights
* Salesperson efficiency
* Seasonal trends

This project is designed to look like an **MNC-style sales performance BI solution**, focusing on **business decision-making**, not just visuals.

---

## 🧾 Dataset Summary

The dataset includes:

* **Sales Person**
* **Country**
* **Product**
* **Date**
* **Amount ($)**
* **Boxes Shipped**

After cleaning and transformations, the dataset allows analysis across:

* Monthly trends
* Product categories
* Regional performance
* Salesperson contributions

---

## 🎯 Business Objectives

The dashboard answers key business questions such as:

### 🔹 **Sales Performance**

* What is the total global revenue?
* Which products generate the highest revenue?
* What countries perform best?

### 🔹 **Operational Efficiency**

* Which regions ship the most boxes?
* What is the **Average Revenue per Unit (ARPU)**?
* How do shipments compare across geographies?

### 🔹 **Sales Team Insights**

* Who are the top-performing salespersons?
* Which salesperson is driving box shipments vs revenue?

### 🔹 **Time-Based Trends**

* How does revenue change month-to-month?
* Which months show peak sales?

---

## 🛠️ Data Cleaning & Transformations

Performed using **Power Query**:

### ✔ Removed currency symbols and converted `Amount` → Number

### ✔ Converted `Date` to proper date format

### ✔ Added new columns:

* **Year**
* **Month**
* **Month Name**
* **Quarter**
* **ARPU = Amount / Boxes Shipped**

### ✔ Ensured data types:

* Amount → Decimal
* Boxes Shipped → Whole Number
* Date → Date

---

## 📐 Data Model

The data model is a simple **star schema**:

* **Fact Table** → Sales
* **Dimension Tables** → Date (Calendar), Country, Product, Salesperson

The Calendar table allows accurate **time-intelligence DAX**.

---

## 📊 Dashboard Pages

Below are the four major report pages included in the PBIX file.

### 1️⃣ **Overview (Executive Summary)**

Includes:

* Total Revenue (6.2M+)
* Total Boxes Shipped (177K+)
* Avg Revenue per Box
* Count of Countries
* Count of Salespersons
* Revenue by Product (Treemap)
* Revenue by Salesperson
* Sales Distribution by Country
* Monthly Revenue Trend

🖼️ *Screenshot: Overview*

<img width="669" height="376" alt="OVERVIEW" src="https://github.com/user-attachments/assets/ad5354d1-9191-41f8-ae35-4f38fc8c0f2a" />


---

### 2️⃣ **Product Performance Analysis**

Includes:

* Scatter plot of Revenue vs Boxes
* Revenue by Product (Bar Chart)
* Product × Country Performance Matrix
* Monthly Box Delivery Trends

🖼️ *Screenshot: Product Performance*

<img width="669" height="377" alt="PRODUCT PERFORMANCE ANALYSIS" src="https://github.com/user-attachments/assets/5d206a08-b32a-4f83-bf7e-1d1e72d819fe" />

---

### 3️⃣ **Country & Regional Insights**

Includes:

* Total Revenue by Country (Map Visual)
* Country-wise ARPU
* Total Revenue by Product & Country
* Average Boxes Shipped by Country
* Country and Month Slicers

🖼️ *Screenshot: Country Insights*

<img width="669" height="377" alt="COUNTRY and REGIONAL INSIGHTS" src="https://github.com/user-attachments/assets/4ded5237-e1f5-4269-a2fe-ddae42eab777" />


---

### 4️⃣ **Salesperson Performance**

Includes:

* Total Revenue by Salesperson
* Total Boxes by Salesperson
* Product Contribution per Salesperson (Matrix)
* Scatter Plot (Boxes vs Revenue)

🖼️ *Screenshot: Salesperson Performance*

<img width="668" height="376" alt="SALESPERSON PERFORMANCE" src="https://github.com/user-attachments/assets/0378977c-f29d-48f1-bc77-35bf9d6d72cc" />


---

## 🧮 Key DAX Measures

```DAX
Total Revenue = SUM('Sales'[Amount])

Total Boxes = SUM('Sales'[Boxes Shipped])

ARPU = DIVIDE([Total Revenue], [Total Boxes])

Revenue by Month =
CALCULATE([Total Revenue],
    VALUES('Calendar'[MonthName])
)

Boxes Delivered = SUM('Sales'[Boxes Shipped])
```

---

## 🔍 Insights Generated

### ⭐ Top 3 Performing Countries (Revenue)

1. Australia
2. India
3. USA

### ⭐ Top Products By Revenue

* Smooth Silky Salty
* 50% Dark Bites
* White Choc

### ⭐ Salesperson Performance

* Ches Bonnell & Oby Sorrel lead in revenue
* Multiple mid-tier performers show strong consistency in box shipments

### ⭐ Seasonal Trend

* Revenue peaks around **March** & **July**
* Lowest sales observed in **April**

---

## 💼 Business Recommendations

✔ Focus marketing efforts on **high-ARPU regions** like USA & India
✔ Increase inventory for top 5 fastest-selling products
✔ Improve promotions in low-shipment months (April & June)
✔ Encourage high-efficiency salespersons to cross-train others
✔ Expand premium product lines in high-value markets

---

## 🧰 Tools Used

* **Power BI Desktop**
* Power Query (ETL)
* DAX (Measures & Time Intelligence)
* Map Visuals
* Matrix, Treemap, Line & Bar Charts

---

## 📁 Project Structure

```
📦 Chocolate Sales Analysis
 ┣ 📄 CHOCOLATE SALES ANALYSIS.pbix
 ┣ 🖼️ OVERVIEW.png
 ┣ 🖼️ COUNTRY and REGIONAL INSIGHTS.png
 ┣ 🖼️ product performace anamysis.png
 ┣ 🖼️ SALESPERSON PERFORMANCE.png
 ┗ 📄 README.md (this file)
```

---

## 🙌 Acknowledgements

Dataset cleaned and visualized as part of a Power BI learning & portfolio development project.

If you like the project, feel free to ⭐ the repo!
