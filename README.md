# Project Overview

This project analyzes food delivery operations using Power BI. The dataset contains customer, restaurant, delivery partner, and order information.

The project demonstrates the complete Business Intelligence workflow including:

Data Cleaning
Data Transformation
Data Modeling
DAX Calculations
Dashboard Design
Business Insights

# Tools Used

Power BI Desktop
Power Query
DAX
Excel / CSV


# The project contains five datasets:

# Table	                      Description
Order_details               Customer orders
User_details                Customer information
Restaurant_details          Restaurant information
Delivery_details            Delivery metrics
Delivery_person_details  	  Delivery partner details

# Data Cleaning
Performed using Power Query.

**Delivery Details**
Removed unnecessary columns
Changed data types
Removed blank rows
Removed errors
Removed NaN values

**Order Details**
Removed duplicates
Converted date/time
Removed null values
Added Order Value Category

**User Details**
Converted Latitude & Longitude
Removed duplicate customers
Added Age Group

**Restaurant Details**
Removed duplicate Restaurant IDs

**Delivery Person Details**
Removed blank rows
Removed NaN values


# Data Modeling
**Relationships**
**From**	                                       **To**
Order_details → User_details	               Customer ID
Order_details → Restaurant_details           Restaurant ID
Order_details → Delivery_details             Order ID
Delivery_details → Delivery_person_details   Delivery Person ID

# DAX Measures

**Total Sales**
Total Sales =
SUM(Order_details[Order Value])

**Average Order Value**
Average Order Value =
AVERAGE(Order_details[Order Value])

**Total Deliveries**
Total Deliveries =
DISTINCTCOUNT(Order_details[Order Id])

**On-Time Delivery %**
On-time Delivery % =
DIVIDE(
COUNTROWS(
FILTER(
Delivery_details,
Delivery_details[Time Taken (Min)]<=30
)),
COUNTROWS(Delivery_details)
)*100

# Dashboard Pages
**1) KPI Dashboard**
Features:

Total Sales
Average Order Value
Total Deliveries
On-Time Delivery %
Total Sales for Drinks
Total Sales for Snacks
Sales Distribution

**2) Charts Dashboard**
Visuals:
Order Value Distribution
Customer Demographics
Sales by Order Type

**3) Performance Dashboard**
Visuals:
Delivery Performance
Delivery Person Efficiency
Restaurant Performance

# Business Insights

Some insights from the dashboard:

Total Sales exceeded ₹22M.
Average Order Value is around ₹914.
On-Time Delivery Rate is nearly 70%.
Buffet orders contribute the highest revenue.
Non-vegetarian cuisine generates the largest share of sales.
Customers in their twenties and thirties form the largest customer segments.
