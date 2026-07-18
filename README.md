# 📊 Sales Dashboard - Power BI Project

## 📌 Project Overview

This project is an interactive **Sales Dashboard** developed with **Microsoft Power BI desktop**. It demonstrates the complete Business Intelligence workflow, including data preparation, data modeling, DAX calculations, dashboard design, navigation, tooltips, security, and report publishing.

The dashboard enables users to monitor sales performance, analyze cancelled orders, and explore sales data using interactive filters and visualizations.

---

# 📂 Dataset

The project uses the **sales_2.csv** dataset containing information about:

- Orders
- Customers
- Products
- Product Categories
- Regions
- Quantities
- Prices
- Order Status
- Order Dates

---

# 🛠 Technologies Used

- Microsoft Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)
- Power BI Service

---

# 📋 Project Workflow

## 1. Data Import

- Imported the `sales_2.csv` dataset into Power Query.
- Verified data types.
- Checked:
  - Column Quality
  - Column Distribution
  - Column Profile

---

## 2. Data Cleaning

Renamed columns to more meaningful names:

| Original Column | New Name |
|-----------------|----------|
| OrderID | Order ID |
| CustomerID | Customer ID |
| CompanyName | Customer Name |
| ProductID | Product ID |
| ProductName | Product Name |
| Category | Product Category |
| RegionID | Region ID |
| RegionName | Region Name |
| OrderDate | Order Date |
| Quantity | Quantity |
| UnitPrice | Unit Price |
| TotalPrice | Total Price |
| OrderStatus | Order Status |

---

## 3. Data Normalization

Created separate reference tables:

- Customers
- Products
- Regions
- Sales (Fact Table)

Additional steps:

- Removed duplicate values
- Removed unnecessary columns
- Sorted reference tables
- Disabled loading for the raw table

---

## 4. Data Modeling

Created a Star Schema model with relationships between:

- Sales ↔ Customers
- Sales ↔ Products
- Sales ↔ Regions

Relationships were verified and recreated manually when necessary.

---

# 📈 Dashboard Features

## Page 1 – Sales Overview

### KPI Cards

- Total Sales
- Number of Orders
- Quantity Sold
- Average Order Value

### Visualizations

- Sales Trend Over Time
- Revenue by Region
- Revenue by Product Category
- Detailed Orders Table

### Interactive Filters

- Order Date
- Order Status
- Region

---

## Page 2 – Cancelled Orders Analysis

Dedicated dashboard for cancelled orders including:

### KPI Cards

- Total Cancelled Orders
- Cancelled Revenue
- Cancellation Rate

### Visualizations

- Cancellation Trend Over Time
- Cancelled Orders by Region
- Cancelled Revenue by Category (Treemap)
- Quarterly Product Cancellation Analysis (Ribbon Chart)

---

# 📐 DAX Measures

Main measures created:

```DAX
Total Sales =
SUM(Sales[Total Price])

Number of Orders =
DISTINCTCOUNT(Sales[Order ID])

Quantity Sold =
SUM(Sales[Quantity])

Average Order =
DIVIDE([Total Sales], [Number of Orders])
```

Cancelled order measures:

```DAX
Cancelled Orders =
CALCULATE(
    COUNT(Sales[Order ID]),
    Sales[Order Status] = "Cancelled"
)

Cancelled Revenue =
CALCULATE(
    SUM(Sales[Total Price]),
    Sales[Order Status] = "Cancelled"
)

Cancellation Rate =
DIVIDE([Cancelled Orders], [Number of Orders])
```

---

# 🎨 Dashboard Design

The report includes:

- Custom Power BI Theme
- Dark dashboard layout
- Consistent color palette
- Interactive navigation menu
- Responsive visual arrangement

---

# 🧭 Navigation

A left-side navigation menu allows users to switch between report pages using interactive buttons.

---

# 💡 Tooltips

Custom tooltip pages were created to provide additional insights:

- Sales trend tooltip for regional analysis
- Product evolution tooltip for category analysis

---

# ⭐ Bonus Features

Implemented advanced Power BI features:

- Bookmark navigation
- Product category bookmarks
- Filter reset button
- Row-Level Security (RLS)
- Mobile layout
- Power BI Service publishing

---

# 📷 Dashboard Preview

📄 [Sales_Report](Sales_Report.pdf)

---

# 🚀 Learning Outcomes

This project demonstrates practical experience with:

- Data Cleaning
- Data Transformation
- Data Modeling
- Star Schema Design
- DAX Calculations
- Interactive Dashboard Design
- Power BI Navigation
- Tooltips
- Bookmarks
- Row-Level Security
- Power BI Service Deployment

---
