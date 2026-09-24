# 📊 Sales & Products Performance Analysis Dashboard

An interactive Power BI analytical report designed to monitor sales volume, revenue breakdown, order statuses, product category performance, and regional sales distribution. This repository includes custom DAX metrics and a specialized report-page Tooltip for enhanced drill-down exploration.

---

## 🖼️ Dashboard Overview

![Products Analysis Dashboard](products%20analysis%20dashboard.png)

---

## 💡 Custom Report Page Tooltip Feature

To deliver an interactive user experience without cluttering the main visual layout, this project incorporates a **Custom Report-Page Tooltip (`ToolTip page`)**.

![Tooltip Feature](tooltip%20in%20products%20analysis%20dashboard.png)

### 🎯 How It Works:
* Hovering over regional data points or status metrics triggers an overlay card dynamically filtering key metrics for that specific context.
* **Featured Metrics in Tooltip:**
  * **Count of TotalDue:** Quick aggregated value for the selected segment (e.g., **8.01K** for Canada).
  * **# of Orders:** Total order volume supporting that metric (e.g., **448 Orders**).
  * **Territory Breakdown:** A quick horizontal bar chart contextualizing regional share instantly.

---

## 📈 Key Executive Metrics (KPIs)

* **# of Order Details:** **24K** individual order line items.
* **# of Orders:** **1K** total sales orders processed.
* **Total Due:** **$33.93 Million** total revenue collected.
* **Total Freight:** **$915.97K** shipping & logistics costs.
* **Total Subtotal:** **$30.09 Million** net sales before tax and shipping.
* **Total Tax:** **$2.93 Million** paid in taxation.

---

## 🔍 Analytical Insights

### 1. Order Trends Over Time (`# of Orders by Year, Quarter, Month and Day`)
* Steady sales volume through **2011–2012**, followed by a steep increase throughout **2013** and early **2014**, demonstrating rapid business growth before stabilizing.

### 2. Order Fulfillment Status (`# of Orders by Status`)
* **Approved:** Accounts for **27.03% (396 orders)**.
* **In Process:** Represents **26.76% (392 orders)**.
* **Shipped:** Makes up **25.53% (374 orders)**.
* **Cancelled, Rejected, & Backordered:** Comprise the remaining **20.68%** combined.

### 3. Category Share (`Count of OrderQty by ProductCategory`)
* **Bikes** and **Components** account for the largest proportion of ordered quantities, followed by **Clothing** and **Accessories**.

### 4. Geographic Distribution (`Count of TotalDue and # of Orders by Territory`)
* **Canada** leads in revenue volume and order count, closely followed by **Northwest**, **France**, and **United Kingdom**.

---

## 🛠️ Data Model & DAX Measures

Calculations created within the `Dax Measures` table:

```dax
# of Order Details = COUNT(FactSales[OrderDetailID])
# of Orders        = DISTINCTCOUNT(FactSales[SalesOrderID])
Total Due          = SUM(FactSales[TotalDue])
Total Freight      = SUM(FactSales[Freight])
Total Subtotal     = SUM(FactSales[SubTotal])
Total Tax          = SUM(FactSales[TaxAmt])
