# PROJECT-2
Customer Data Project 2
# Project Title: Customer Segmentation for a Subscription Service 

## Outline
[Project Overview](#project-overview)

[Data Description](#data-description)

[ Methodology](#methodology)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Insights Generation](#insights-generation)

[Conclusions](#conclusions)

[Recommendations](#recommendations)

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
``` CREATE DATABASE CAPSTONE```. The CSV file was then imported by right-clicking on the database created, going to tasks, importing flat files, browsing the file, clicking on next, and then finishing. The file was scanned through before importing. It was then viewed in SQL by using the following command: ``` Select * from Customer Data```
**Importing Data Into Power BI:** For Power BI, the file was imported by selecting the Get Data option and choosing the Excel workbook. It was searched for in my files and taken to the transform workshop before loading.
      
3. **Data Transformation**
- Ensured all data fields were assigned the correct data types, with numerical fields formatted as currencies where appropriate, and date fields set to date format.


## Exploratory Data Analysis 

### Excel
The pivot table in Excel was used to summarize and analyze the dataset to generate some interesting reports.

![PIVOT TABLES (EXCEL)](https://github.com/user-attachments/assets/dc27df95-8823-47cc-8610-b2638a6ac973)


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

  ```SQL
  select Region,count(CustomerName) as [Total Number of Customers] from [dbo].[CustomerData] group by Region order by 2 desc

![SQL Query 8](https://github.com/user-attachments/assets/7f887d92-2a16-48bf-a022-b85a91dafc7d)

```
select top 1 SubscriptionType, count(CustomerName)as [Most Popular Subscription Type] from [dbo].[CustomerData] 
group by SubscriptionType
```
![SQL Query 9](https://github.com/user-attachments/assets/44b1f295-94af-4108-b6f2-d3c2987d45b2)

```SQL
select * from [dbo].[CustomerData] where Canceled ='TRUE' and year(SubscriptionEnd) ='2024' and Month(SubscriptionEnd) in (3,4,5,6,7,8)
```
![SQL Query 10](https://github.com/user-attachments/assets/6401a95e-7ae9-42f9-a8be-4abaadd2ea78)

```SQL
select avg(datediff(month,subscriptionstart,subscriptionend)) as [Average Subscription Duration] from [dbo].[CustomerData]
```
![SQL Query 11](https://github.com/user-attachments/assets/610a052e-1e9f-42e2-a2d8-b0381e542fa7)

```SQL
select customerid from [dbo].[CustomerData] where datediff(month,subscriptionstart,subscriptionend)>12
```
![SQL Query 12](https://github.com/user-attachments/assets/ae506e23-86df-43b0-af5c-19a90a52ce82)

```SQL
select SubscriptionType, sum(Revenue) as [Total Revenue] from [dbo].[CustomerData] group by SubscriptionType
```
![SQL Query 13](https://github.com/user-attachments/assets/9793c162-487f-4164-abaa-0773429a9c34)

```SQL
select top 3 Region, count(Canceled) as [Subscription Cancelation] from [dbo].[CustomerData] where Canceled ='TRUE' group by Region
```
![SQL Query 14](https://github.com/user-attachments/assets/2ffbb730-a08f-4b87-94f4-6e7f4497785d)

```SQL
select Canceled, count(Canceled) as [Subscriptions] from [dbo].[CustomerData] group by Canceled
```
![SQL Query 15](https://github.com/user-attachments/assets/e68fe789-dfa3-473a-86b0-de4a792c03c7)

### Power BI
The Power BI was used to create an interactive dashboard that visualizes key customer segments, cancellations, and subscription trends. Slicers for region and subscription type were also included for interactive analysis. The dashboard provides an overview of  customer behavior across different regions, highlighting total revenue, number of active and canceled subscriptions, average subscription date, etc. Some visuals used were a Bar Chart, Line Chart, Pie Chart, and Visual Card.

![PBI 2(1)(1)](https://github.com/user-attachments/assets/477dcc24-3d27-42cd-b8b0-2989ead66c1d)



## Insights Generation
- Basic subscription type contributed the highest revenue, followed by Premium and Standard.
- The East and North regions primarily used the basic subscription type. The south region uses the Premium subscription type while the West region uses the standard subscription type.
- The highest number of customers subscribe to the Basic plan, followed by Premium and then Standard, aligning with the revenue distribution across these types.
- East generated the highest revenue, followed by South, West, and North.
- The East region has the highest customer count, followed by South, West, and North, which mirrors the revenue pattern
- East has no canceled subscriptions, suggesting strong customer retention.
- North, South, and West have more canceled subscriptions than active ones, indicating potential issues in these regions.
- 2022 had more active subscriptions while 2023 saw an increase in canceled subscriptions surpassing the active ones.
- July and February 2022 had more customers compared to July and February 2023.
- August showed the opposite, with fewer customers in August 2023 compared to August 2023.

## Conclusions
- The Basic subscription type is the most popular type generating the highest revenue and customer base, suggesting it meets a broad range of customer needs.
- The East region is the most significant market, both in terms of revenue and customer count, with strong customer loyalty as evidenced by no cancellations.
- Other regions face higher cancellation rates than active subscriptions, indicating a need to address customer satisfaction or retention issues.
- The increase in cancellations in 2023 suggests a possible shift in customer satisfaction or market condition that impacted retention, especially given the cancellation trend in the North, South, and West regions.
- The decline in customer counts in July and February 2023 indicates a seasonal lull or market shift while August indicates possible seasonal or promotional factors that contributed to higher subscriptions.

## Recommendations
- Conduct surveys or gather feedback to understand why cancelations are higher in the North, West, and South regions, identifying any issues with service quality, pricing or value, or maybe the subscription type.
- Implement loyalty programs or rewards for long-term subscribers to incentivize retention.
- Offer retention-focused discounts for subscribers in regions with high cancellation rates, particularly during periods with historically low customer activity.
- Consider introducing add-on benefits to the Basic subscriptions to further increase its value and appeal, especially in the East and North where it is already widely used.
- Encourage basic subscribers to explore premium features by offering limited-time upgrades or trials to the Premium plan.
- Investigate the factors driving higher cancelations in 2023. Use insights to adjust service or pricing to meet evolving customer needs.
- To sustain customer growth in challenging months like February and July, introduce specific campaigns or discounts to attract new customers and retain existing ones.
- Continue to monitor and maintain the East region’s high customer retention with ongoing customer satisfaction initiatives.
- Consider expanding customer acquisition efforts in South and North, potentially by refining the Standard and Premium subscription options to meet regional preferences more closely.
