# 📊 Power BI Dashboard – Order Analytics



An interactive **Order Analytics Dashboard** built using Microsoft Power BI.  
This project visualizes customer orders, shipping performance, regional insights, and product categories, offering actionable business intelligence for decision-making.

---

## 📁 Data Sources

1. **List of Orders**  
   High-level order details including:  
   `Order ID`, `Order Date`, `Customer`, `City`, `Country`, `Segment`, `Ship Date`, and more.

2. **Order Breakdown**  
   Product-specific details including:  
   `Product Name`, `Category`, `Sub-Category`, `Sales`, `Profit`, `Discount`, `Return Status`, and others.

---

## 🧹 Data Transformation Steps (Power Query)

### 🔹 List of Orders
- Converted `Order Date` and `Ship Date` to proper `Date` types.
- Renamed ambiguous columns (`lon` → `Longitude`, `lat` → `Latitude`).
- Added calculated columns:
  - `Order Year` = `Date.Year([Order Date])`
  - `Shipping Delay (Days)` = `Duration.Days([Ship Date] - [Order Date])`

### 🔹 Order Breakdown
- Converted numeric fields (`Sales`, `Profit`, `Discount`, `Quantity`) to number types.
- Converted categorical columns (`Category`, `Sub-Category`, `Return Status`) to text types.

---

## 🔗 Data Modeling

- Established a **One-to-Many** relationship:
  ```markdown
  List of Orders[Order ID] → Order Breakdown[Order ID]
