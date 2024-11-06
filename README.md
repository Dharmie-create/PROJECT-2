# PROJECT-2
Customer Data Project 2
# Project Title: Customer Segmentation for a Subscription Service 

## Project Overview
This data analysis project aims to understand customer behavior, track subscription types, and identify key trends in cancelations and renewals by analyzing customer data for a subscription service to identify segments and trends. By analyzing the various parameters in the data received, we seek to  gather enough insights to make reasonable decisions which then enable us to tell compelling stories around our data from the insight gotten and to know the best performance from our data. More so, we can figure out what is working, what is not working, and what should be focused on.

## Data Description
The dataset includes the following fields:
- **CustomerID:** A unique identifier for each customer making the purchase.
- **Customer Name:** Name of customers having subscriptions
 -**Region:** The geographical area or region where the order was placed or delivered.
- **Subscription Type:** The type of subscription chosen for each customer.
- **Subscription Start:** The start date of each customer’s subscription.
- **Subscription End:** The end date of each customer’s subscription
- **Canceled:** Column showing whether a customer’s subscription has been canceled or not, with True indicating a canceled subscription and False indicating an active subscription
- **Revenue:** The amount of revenue generated from each subscription.

### Basic Statistics About The Dataset
- **Total Sales Revenue:** $67,540,175 
- **Number of Unique Customers:** 20
- **Number of Subscription Type:** 3 (Basic, Standard, Premium)
- **Number of Active Subscriptions:** 18,612
- **Number of Canceled Subscriptions:** 15,175


## Methodology
### Tools Used
#### Microsoft Excel
- For Data Cleaning
- For Analysis 

#### SQL-Structured Query Language
- For Querying of Data
- For Analysis

#### PBI-Power Business Intelligence
- For Visualization
 
### Data Collection
The dataset for this analysis was provided by LITA Incubator Hub, an initiative that has the vision of empowering ladies across Africa through technology, equipping them with the skills to thrive in the digital age. The data was provided in Excel format, making it accessible for analysis.

### Data Manipulation
1. **Data Cleaning**
- Checked for spelling errors, duplicate values, and blank cells.
- Ensured data quality by removing duplicate entries.

2. **Data Importing**
- **Importing Data Into SQL:** The data which was in Excel format was converted to a CSV file. To import the data into SQL, I used SQL Server Management Studio(SSMS). A database was created named CAPSTONE using the following command: 
``` CREATE DATABASE CAPSTONE```. The CSV file was then imported by right-clicking on the database created, going to tasks, going to import flat files, browsing the file, clicking on next, and then finish. The file was scanned through before importing. It was then viewed in SQL by using the following command: ``` Select * from Customer Data```
- **Importing Data Into Power BI:** For Power  BI, the file was imported by selecting the Get Data option and choosing Excel workbook. The file was searched for in my files and taken to the transform workshop before loading.
      
3. **Data Transformation**
- Ensured all data fields were assigned the correct data types, with numerical fields formatted as currencies where appropriate, and date fields set to date format.
- **Created New column:** A new column was added to get the revenue generated for each quantity of product sold per transaction by multiplying the quantity sold by the unit price.


## Exploratory Data Analysis 

### Excel
The pivot table in Excel was used to summarize and analyze the dataset to generate some interesting reports.

### SQL
Some SQL queries were written to extract key insights from the data. The goal was to analyze customer data for the subscription service and identify segments and trends. They are:
- retrieve the total number of customers from each region.
- find the most popular subscription type by the number of customers.
- find customers who canceled their subscription within 6 months.
- Calculate the average subscription duration for all customers.
- find customers with subscriptions longer than 12 months.
- calculate total revenue by subscription type.
- find the top 3 regions by subscription cancellations.
- find the total number of active and canceled subscriptions. 

### Power BI
The Power BI was used to create an interactive dashboard that visualizes key customer segments, cancellations, and subscription trends. Slicers for region and subscription type were also included for interactive analysis. The dashboard provides an overview of  customer behavior across different regions, highlighting total revenue, number of active and canceled subscriptions, average subscription date, etc. Some visuals used were a Bar Chart, Line Chart, Pie Chart, and Visual Card.


