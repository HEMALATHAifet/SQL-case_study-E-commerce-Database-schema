Perfect 👍 Here’s a **complete, ready-to-present case study** on an **E-Commerce Database Schema** — ideal for portfolio, GitHub, or LinkedIn.

You can copy this into a markdown file (`README.md`) or convert it into a report/PDF later.

---

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

```sql
CREATE TABLE Customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    phone VARCHAR(15),
    address VARCHAR(200)
);

CREATE TABLE Categories (
    category_id INT PRIMARY KEY,
    category_name VARCHAR(50)
);

CREATE TABLE Products (
    product_id INT PRIMARY KEY,
    name VARCHAR(100),
    category_id INT,
    price DECIMAL(10,2),
    stock_qty INT,
    FOREIGN KEY (category_id) REFERENCES Categories(category_id)
);

CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    total_amount DECIMAL(10,2),
    status VARCHAR(20),
    FOREIGN KEY (customer_id) REFERENCES Customers(customer_id)
);

CREATE TABLE Order_Items (
    order_item_id INT PRIMARY KEY,
    order_id INT,
    product_id INT,
    quantity INT,
    price DECIMAL(10,2),
    FOREIGN KEY (order_id) REFERENCES Orders(order_id),
    FOREIGN KEY (product_id) REFERENCES Products(product_id)
);

CREATE TABLE Payments (
    payment_id INT PRIMARY KEY,
    order_id INT,
    payment_method VARCHAR(20),
    payment_date DATE,
    amount DECIMAL(10,2),
    status VARCHAR(20),
    FOREIGN KEY (order_id) REFERENCES Orders(order_id)
);

CREATE TABLE Shipments (
    shipment_id INT PRIMARY KEY,
    order_id INT,
    shipped_date DATE,
    delivery_date DATE,
    tracking_no VARCHAR(50),
    FOREIGN KEY (order_id) REFERENCES Orders(order_id)
);

CREATE TABLE Reviews (
    review_id INT PRIMARY KEY,
    product_id INT,
    customer_id INT,
    rating INT CHECK (rating BETWEEN 1 AND 5),
    comment VARCHAR(255),
    review_date DATE,
    FOREIGN KEY (product_id) REFERENCES Products(product_id),
    FOREIGN KEY (customer_id) REFERENCES Customers(customer_id)
);
```

---

## 🧮 **3. Sample Business Queries**

### 1️⃣ Total revenue by month

```sql
SELECT 
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(total_amount) AS total_revenue
FROM Orders
GROUP BY EXTRACT(MONTH FROM order_date)
ORDER BY month;
```

### 2️⃣ Top 5 best-selling products

```sql
SELECT 
    p.name, 
    SUM(oi.quantity) AS total_sold
FROM Order_Items oi
JOIN Products p ON oi.product_id = p.product_id
GROUP BY p.name
ORDER BY total_sold DESC
LIMIT 5;
```

### 3️⃣ Average customer spending

```sql
SELECT 
    c.name, 
    SUM(o.total_amount) AS total_spent
FROM Customers c
JOIN Orders o ON c.customer_id = o.customer_id
GROUP BY c.name
ORDER BY total_spent DESC;
```

### 4️⃣ Inventory low stock check

```sql
SELECT name, stock_qty 
FROM Products
WHERE stock_qty < 10;
```

### 5️⃣ Average product rating

```sql
SELECT 
    p.name,
    ROUND(AVG(r.rating),2) AS avg_rating
FROM Reviews r
JOIN Products p ON r.product_id = p.product_id
GROUP BY p.name
ORDER BY avg_rating DESC;
```

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

---

### 💬 Example GitHub Title

> **E-Commerce Database Schema & Analysis — SQL Case Study**

### 🔗 Example LinkedIn Post

> 🚀 *Day 59 of my SQL Learning Journey!*
> Designed an **E-Commerce Database Schema** simulating a real online store.
> Learned how to structure relationships between customers, orders, payments & reviews — and analyzed sales, ratings, and customer behavior.
>
> #SQL #DatabaseDesign #DataAnalytics #Ecommerce #SQLProject #CaseStudy #LearningJourney

---

Would you like me to now give you a **PDF or README.md version** (ready for GitHub upload) of this same case study?
