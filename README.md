# Sales_Profit_Loss_Dashboard
# 📊 Sales Dataset Analysis in Power BI

This project provides a comprehensive analysis of a sales dataset using **Power BI**. The dataset includes sales, cost, and discount data across different product categories, customers, and regions. Additional calculated columns like **Profit** and **Loss** help to identify performance trends and business insights.

---

## 📁 Dataset Overview

The dataset includes the following key columns:

- `Order ID`
- `Order Date`
- `Ship Date`
- `Customer ID`
- `Customer Name`
- `Segment` (Consumer, Corporate, Home Office)
- `Region`, `State`, `City`
- `Category`, `Sub-Category`, `Product Name`
- `Sales` (Total selling price)
- `Cost` (Calculated cost price)
- `Quantity`, `Discount`
- `Profit` (Calculated)
- `Loss` (Calculated if cost > sales)

---

## 🧮 Power BI Calculations

### ✅ Calculated Columns (DAX):

```DAX
Profit = ROUND([Sales] - [Cost], 2)

Loss = IF([Cost] > [Sales], ROUND([Cost] - [Sales], 2), 0)

ProfitStatus = 
SWITCH(TRUE(),
    [Profit] > 0, "Profit",
    [Profit] < 0, "Loss",
    "Break-even"
)

Profit % = DIVIDE([Profit], [Cost], 0) * 100

