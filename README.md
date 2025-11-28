
### 🛒 Customer Churn Database – SQL Project
### 📌 Project Overview

This project creates and configures a SQL database named ecomm to store customer data for churn analysis. The dataset includes demographic, behavioral, and transactional attributes that can be used for predictive analytics, segmentation, and business intelligence.

🗂 Database & Table Creation

The SQL script includes:

Dropping existing database (if exists)

Creating a new database

Creating the customer_churn table with structured fields

DROP DATABASE IF EXISTS ecomm;
CREATE DATABASE ecomm;
USE ecomm;

CREATE TABLE customer_churn(
    CustomerID                  INT  PRIMARY KEY,
    Churn                       BIT,
    Tenure                      INT,
    PreferredLoginDevice        VARCHAR(20),
    CityTier                    INT,
    WarehouseToHome             INT,
    PreferredPaymentMode        VARCHAR(20),
    Gender                      ENUM('Male','Female'),
    HourSpendOnApp              INT,
    NumberOfDeviceRegistered    INT,
    PreferedOrderCat            VARCHAR(20),
    SatisfactionScore           INT,
    MaritalStatus               VARCHAR(10),
    NumberOfAddress             INT,
    Complain                    BIT,
    OrderAmountHikeFromlastYear INT,
    CouponUsed                  INT,
    OrderCount                  INT,
    DaySinceLastOrder           INT,
    CashbackAmount              INT
);

🧠 Key Fields & Purpose
Column Name	Description
CustomerID	Unique identifier for each customer
Churn	Whether customer stopped using service (1=yes, 0=no)
Tenure	How long the user has been a customer
PreferredLoginDevice	Desktop / Mobile / App type
CityTier	City type (Tier 1, 2, 3)
WarehouseToHome	Distance between warehouse & home
PreferredPaymentMode	Card, UPI, COD, etc
Gender	Male / Female
HourSpendOnApp	Time spent using the app
NumberOfDeviceRegistered	Devices linked to account
PreferedOrderCat	Most ordered category
SatisfactionScore	Review 1–10
MaritalStatus	Single / Married, etc
NumberOfAddress	Number of stored delivery addresses
Complain	Whether the customer has submitted complaints
OrderAmountHikeFromlastYear	% increase in spending
CouponUsed	Number of coupons used
OrderCount	Total number of orders
DaySinceLastOrder	Time since last order
CashbackAmount	Cashback received
🎯 Goal of This Project

This dataset enables analysis such as:

✔ Predicting customer churn
✔ Identifying user engagement patterns
✔ Understanding purchase behavior
✔ Customer segmentation
✔ Business decision insights

🔍 Example Analytical Queries
Get churn rate:
SELECT AVG(Churn) * 100 AS ChurnRatePercentage FROM customer_churn;

Average tenure of customers:
SELECT AVG(Tenure) FROM customer_churn;

Most preferred payment method:
SELECT PreferredPaymentMode, COUNT(*) 
FROM customer_churn 
GROUP BY PreferredPaymentMode 
ORDER BY COUNT(*) DESC;

Do high complain customers churn more?
SELECT Complain, AVG(Churn) AS ChurnPercentage
FROM customer_churn
GROUP BY Complain;

🚀 Future Enhancements

Insert sample data

Create views for KPI reporting

Build Python ML churn prediction model

Export results as CSV for visualization

👤 Author

Rizwana — Data Analytics / SQL Developer
Feel free to contribute, suggest improvements, or fork this project!

If you want — I can also:
✔ create fake sample data
✔ write MySQL data insertion scripts
✔ build Python analysis notebook
✔ generate ER-diagram
✔ write Jupyter notebook for churn prediction model
