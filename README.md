# 🍕 Pizza Sales Analysis Dashboard - Power BI Project

This project presents a comprehensive **Power BI Dashboard** for analyzing pizza sales performance. It involves data cleaning, transformation, and visualization to extract meaningful business insights.

---

## 📂 Dataset Overview

The dataset includes four CSV files:

- `orders.csv`: Order metadata (date, time)
- `order_details.csv`: Items per order (pizza_id, quantity)
- `pizza.csv`: Pizza menu (type, size, price)
- `pizza_types.csv`: Name, category, and ingredients

---

## 🎯 Project Objectives

1. Identify peak and low pizza order hours.
2. Analyze which days of the week receive the most orders.
3. Calculate total sales and average order value.
4. Identify the most ordered and most profitable pizzas.
5. Segment orders by time of day (morning/afternoon/evening/night).
6. Estimate profit and profit margin.
7. Enable interactive filtering using slicers (date, category, size, time slot, etc.).

---

## 🔧 Tools Used

- **Power BI Desktop**
- **Power Query Editor** (for data transformation)
- **DAX** (for calculated measures and KPIs)

---

## 🧹 Data Cleaning & Transformation

Performed in Power Query:

- Removed nulls, trimmed & standardized text
- Converted date/time columns to proper types
- Created custom columns:
  - `DateTime` (from date + time)
  - `Hour`, `Day Name`, `Time Slot` (Morning/Afternoon/Evening/Night)

---

## 📊 Key Measures (DAX)

```dax
Sales = SUMX(order_details, order_details[quantity] * RELATED(pizza[price]))
Profit = [Sales] * 0.6
Profit Margin % = DIVIDE([Profit], [Sales]) * 100
Total Orders = COUNTROWS(order_details)
Total Quantity = SUM(order_details[quantity])
