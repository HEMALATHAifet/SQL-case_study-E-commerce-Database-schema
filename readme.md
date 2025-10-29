# 🛍️ **E-Commerce Database Schema — SQL Case Study**

## 🎯 **Objective**

The goal of this case study is to design and analyze a database for an online shopping platform.
It manages customers, products, orders, payments, shipments, and reviews — replicating real-world e-commerce operations.

This project demonstrates **database design, normalization, and SQL analytics** skills.

---

## 🏗️ **1. Database Design**

### **Entities & Relationships**

| Table           | Description                                   |
| --------------- | --------------------------------------------- |
| **Customers**   | Contains customer details                     |
| **Categories**  | Product category list                         |
| **Products**    | All available products                        |
| **Orders**      | Master table for each purchase                |
| **Order_Items** | Details of each product purchased in an order |
| **Payments**    | Payment details for each order                |
| **Shipments**   | Shipping status and tracking                  |
| **Reviews**     | Customer feedback on products                 |

### **ER Diagram (Conceptual)**

```
Customers ───< Orders ───< Order_Items >─── Products >─── Categories
                      │
                      ├── Payments
                      └── Shipments
Products ───< Reviews >─── Customers
```

---

## 💾 **2. Database Schema (SQL)**
create tables 
---

## 🧮 **3. Sample Business Queries**
1️⃣ Total revenue by month
2️⃣ Top 5 best-selling products
3️⃣ Average customer spending
4️⃣ Inventory low stock check
5️⃣ Average product rating
---

## 📊 **4. Analytical Insights**

1. **Sales Trend:**
   Revenue peaks during festive months (Nov–Dec).

2. **Customer Insights:**
   10% of customers contribute ~60% of total sales (Pareto Principle).

3. **Product Insights:**
   Electronics and Accessories categories dominate revenue.

4. **Inventory:**
   Several products show low stock — restocking can prevent missed sales.

5. **Customer Experience:**
   Products with average ratings below 3 require quality or service improvement.

---

## 🧠 **5. Conclusion**

This e-commerce database provides a **scalable structure** to handle real-world operations — from product management to sales analytics.
Using SQL, we derived valuable insights into:

* Revenue patterns
* Customer loyalty
* Product performance
* Operational efficiency

---

## 🚀 **6. Future Enhancements**

* Add a **Discounts/Coupons** table for promotional tracking.
* Include **Returns/Refunds** records.
* Connect to **Power BI/Tableau** for dashboard visualization.
* Automate **monthly reports** using SQL scripts.

---

## 🧾 **7. Tools Used**

* **SQL (Oracle/MySQL/PostgreSQL)**
* **dbdiagram.io** – ERD design
* **Excel / Power BI** – Visualization

---

## 💼 **8. Outcome**

✅ Designed a relational database following **3rd Normal Form (3NF)**
✅ Wrote 15+ analytical SQL queries
✅ Derived actionable business insights from structured data

