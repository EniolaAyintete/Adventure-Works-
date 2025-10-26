# Adventure-Works-

Adventure Works Sales Analytics Dashboard (Power BI)
📊 Project Overview

This Power BI project analyzes global sales performance for the Adventure Works manufacturing company.
The dashboard connects directly to a Microsoft SQL Server database, cleans and models the data in Power BI, and visualizes insights on Sales Performance, Customer Behavior, and Product Profitability across regions.

🎯 Objectives

Connect Power BI to a SQL Server database running in Docker / Azure Data Studio.
Extract and clean relational data from multiple schemas (Sales, Production, Person).
Build a star-schema data model for efficient DAX calculations.
Create interactive dashboards with KPIs, charts, and drill-throughs for business insight.

🧰 Tech Stack
Tool	      Purpose
Power BI Desktop	    Data modeling & visualization
Azure Data Studio / Docker (SQL Server 2019)	    Database host
DAX	      Measures & aggregations
Power Query (M)    	Data cleaning & transformation
AdventureWorks 2019	Sample       OLTP database

Data Preparation & Cleaning
Performed in Power Query:
Removed unused tables & columns to reduce model size.
Renamed columns for readability (e.g., SalesOrderHeader.SalesOrderID → Order ID).

Merged related tables:
SalesOrderHeader + SalesOrderDetail → unified sales table.
Joined Product, ProductSubcategory, ProductCategory to get full hierarchy.
Replaced nulls with zeros / “Unknown”.
Created calculated columns

Data Modeling
Designed a clean star schema
Relationships:

Sales[CustomerID] → Customer[CustomerID]

Sales[ProductID] → Product[ProductID]

Sales[TerritoryID] → SalesTerritory[TerritoryID]

Sales[OrderDate] → Date[Date]

Marked the Date table as the official date dimension for time intelligence.

Dashboard Pages & Insights
1️⃣ Sales Overview
KPIs: Total Sales ($109.8 M), Sales Count (31 K), Profit ($12.5 M), YoY Growth (0%).
Visuals: Sales by Country, Category, Channel, and Business Type.
Insight: Most sales originate from the United States and the Bike category via Reseller Channel (73%).

2️⃣ Customer Overview
KPIs: 18 K Total Customers | $5.94 K Avg Revenue per Customer | 0.87 Repeat Rate.
Visuals: Customer Count by Country, Profit by State, CLV by Region, Customer Type (New vs Returning).
Insight: ≈ 87% of customers are returning; US and Australia yield highest profitability.

3️⃣ Product Overview
KPIs: 275 K Units Sold | $109.8 M Revenue | $751 Avg Price | Top Product: Mountain-200 Black (38).
Visuals: Sales by Category & Subcategory, Profit by Model, YoY Sales by Category, Quantity by Subcategory.
Insight: Bikes dominate revenue (≈ 65%), especially Mountain and Road Bikes. Components drive steady repeat sales volume.
