Customer Shopping Behavior Analysis
A full-stack data analytics project exploring transactional retail data using Python, PostgreSQL, and Power BI — uncovering spending patterns, customer segments, and product preferences across 3,900 purchases.
PROJECT OVERVIEW
This project performs end-to-end analysis of customer shopping behavior, from raw data cleaning in Python to SQL-driven business insights and an interactive Power BI dashboard. The goal is to surface actionable recommendations around customer retention, discount strategy, and product positioning.

DATASET SUMMARY

Rows: 3,900
Columns: 18
Missing Data: 37 values in Review Rating column
Age Range: 18 to 70
Average Purchase Amount: $59.76
Average Review Rating: 3.75 / 5.0

Key feature groups:

Demographics: Age, Gender, Location, Subscription Status
Purchase Details: Item, Category, Amount (USD), Season, Size, Color
Behavior Signals: Discount Applied, Previous Purchases, Frequency, Shipping Type, Review Rating

PYTHON: EDA AND DATA PREPARATION
Performed using pandas in a Jupyter notebook.
Steps taken:

Data Loading — Imported CSV using pandas
Initial Exploration — Used df.info() and .describe() for structure and statistics
Missing Data Handling — Imputed missing review_rating values with the median per product category
Column Standardization — Renamed all columns to snake_case
Feature Engineering

age_group: binned customer ages into lifecycle segments
purchase_frequency_days: derived from purchase frequency labels


Redundancy Check — Confirmed discount_applied and promo_code_used were redundant; dropped promo_code_used
Database Integration — Connected to PostgreSQL and loaded the cleaned DataFrame via SQLAlchemy

SQL: BUSINESS ANALYSIS (PostgreSQL)
Ten business questions answered using structured SQL queries:

Revenue by Gender
Male: $157,890 | Female: $75,191
High-Spending Discount Users
839 customers used discounts yet spent above the average purchase amount
Top 5 Products by Rating
Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78)
Shipping Type Comparison
Express avg: $60.48 | Standard avg: $58.46
Subscribers vs. Non-Subscribers
Average spend nearly identical — Subscribers: $59.49 | Non-subscribers: $59.87
Discount-Dependent Products
Hat (50%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%)
Customer Segmentation
Loyal: 3,116 | Returning: 701 | New: 83
Top 3 Products per Category
Clothing: Blouse, Pants, Shirt
Accessories: Jewelry, Sunglasses, Belt
Footwear: Sandals, Shoes, Sneakers
Outerwear: Jacket, Coat
Repeat Buyers and Subscriptions
Non-subscribers make up the majority of repeat buyers (2,518 vs. 958)
Revenue by Age Group
Young Adult: $62,143 | Middle-aged: $59,197 | Adult: $55,978 | Senior: $55,763

POWER BI DASHBOARD
An interactive dashboard was built to visualize all key findings, featuring:

KPI cards for Total Customers, Average Purchase Amount, and Average Review Rating
Donut chart showing Subscription Status breakdown (27% Yes / 73% No)
Bar charts for Revenue and Sales by Category and Age Group
Slicers to filter by Subscription Status, Gender, Category, and Shipping Type

BUSINESS RECOMMENDATIONS

Boost Subscriptions
Only 27% of customers subscribe. Promote exclusive perks to grow this segment.
Customer Loyalty Programs
3,116 loyal customers exist — reward them to reduce churn risk.
Review Discount Policy
Discount rates of ~50% on items like Hats and Sneakers may be eroding margins.
Product Positioning
Highlight top-rated items (Gloves, Sandals, Boots) in marketing campaigns.
Targeted Marketing
Focus on Young Adults and Express-shipping users, who are the highest revenue contributors.

TECH STACK

Excel
Python (pandas, SQLAlchemy)
PostgreSQL
Power BI
