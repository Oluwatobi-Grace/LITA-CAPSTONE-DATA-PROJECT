# LITA-CAPSTONE-DATA-PROJECT BY OLUWATOBI GRACE BELLOS
## This is my first independent project from the LITA Data Analysis training


## [Project Overview](project-overview)
#### [Data Sources](data-sources)
#### [Tools Used](tools-used)
#### [Data Cleaning](data-cleaning)
#### [Data Analysis](data-analysis)
#### [Data Visualization](data-visualization)


## Project Overview
---
This project includes two sets of data which are:
- Sales Data: This is the data for Nationwide Sales that shows products, quantities, prices and revenue across four regions.
- Customer Data: This shows the subscription trend of customers, cancellation status, duration of subscription and other relevant information.


## Data Sources
---
The primary source of data is the excel spreadsheets sent to our Canvass Learning Management System for this Project

## Tools Used
---
- Microsoft Excel
  1. Data Cleaning
  2. Data Analysis
  3. Data Visualization
     
- SQL- Structured Query Language
  1. Data Cleaning
  2. Data Analysis
     
- Microsoft PowerBI
  1. Data Cleaning
  2. Data Analysis
  3. Data Visualization

- GitHub for Portfolio Building


## Data Cleaning
---
This is where I removed blank columns, added some more relevant columns based on some conditions peculiar to each data set for a more effetive data analysis 

## Data Analysis
---
This is where I included some basic lines of codes, conditional formatting, queries and DAX used during my analysis
#### My SQL codes are as follows:
```
create database MY_LITA_PROJECT
select *from sales_data_for_project
select *from customer_data_for_project

select Revenue from [dbo].[Customer_data_for_project]
select customerid, Revenue from [dbo].[Customer_data_for_project]
select *from [dbo].[Customer_data_for_project]

select subscriptiontype from [dbo].[Customer_data_for_project]
where subscriptiontype = 'basic'

select customerid, subscriptiontype from [dbo].[Customer_data_for_project]
group by subscriptiontype
 
select *from [dbo].[Customer_data_for_project]

-------total sales for each product category------
select sum(revenue) as TotalSalesperPproduct, [Product] from [dbo].[Sales_Data_for_Project]
group by [Product]

select sum([Quantity]) as TotalQuantitySoldperProduct, [Product] from [dbo].[Sales_Data_for_Project]
group by [Product]

-------total sales transaction in each region------
select sum([Quantity]) as TotalSalesPerRegion, [Region] from [dbo].[Sales_Data_for_Project]
group by [Region]

select sum([Revenue]) as TotalRevPerRegion, [Region] from [dbo].[Sales_Data_for_Project]
group by [Region]

----------highest selling product by total sales value-------
select sum([Quantity]) as QtysoldPerProduct, [Product] from [dbo].[Sales_Data_for_Project]
group by [Product]
order by sum([Quantity]) desc
-------highest selling product is Hat--------------

--------Total revenue per product-------
select sum([Revenue]) as SalesPerProduct, [Product] from [dbo].[Sales_Data_for_Project]
group by [Product]
order by sum([Revenue]) desc
-------highest revenue comes from shoes-------

select sum([Revenue]) as SalesPerProduct, [Product] from [dbo].[Sales_Data_for_Project]
group by [Product]
order by sum([Revenue]) desc

-------to know the top 5 customers by purchase amount-------
select sum([Revenue]) as SalesPerProduct, [Customer_Id] from [dbo].[Sales_Data_for_Project]
group by Customer_Id
order by sum([Revenue]) desc

select [Revenue], [Customer_Id] from [dbo].[Sales_Data_for_Project]
where [Revenue] >= '600'
select max(revenue) from [dbo].[Sales_Data_for_Project]

-------products with no sales---------
select [Revenue], [Product] from [dbo].[Sales_Data_for_Project]
where [Revenue] = '0'


---------Customer table----------
-------total number of customers from each region----------
select count(customerid) as CustomersPerRegion, Region from [dbo].[Customer_data_for_project]
group by Region


--------most popular subscription type by the number of customers--------
select subscriptiontype, count(customerid) as NumberOfSubcribers from [dbo].[Customer_data_for_project]
group by subscriptiontype
------most poular subscription type is Basic----------

-----customers who canceled their subscription within 6 months------
select customerid, Subscription_Duration_m from [dbo].[Customer_data_for_project]
where Subscription_Duration_m<'6'

-------average subscription duration for all customers-------
select avg([Subscription_Duration_m]) as averagesub_in_months from [dbo].[Customer_data_for_project]

-----customers with subscriptions longer than 12 months---------
select customerid, Subscription_Duration_m from [dbo].[Customer_data_for_project]
where Subscription_Duration_m >'12'

-------total revenue by subscription type--------
select [SubscriptionType], sum([Revenue]) as Total_Revenue from [dbo].[Customer_data_for_project]
group by SubscriptionType

----top 3 regions by subscription cancellations------
select region, count(Canceled) as No_Of_Cancellations from [dbo].[Customer_data_for_project] where Canceled = 'true'
group by Region

------total number of active subscriptions------
select count(canceled) as Active_Subscribers from [dbo].[Customer_data_for_project] where Canceled = 'false'

------total number of cancelled subscriptions------
select count(canceled) as Canceled_Subscribers from [dbo].[Customer_data_for_project] where Canceled = 'true'
```
## Data Visualization
With the use of Microsoft Excel and PowerBI, I was able summarize the two data sets into the visualizations below
### Microsoft Excel
#### Sales Data
![SALES DATA EXCEL](https://github.com/user-attachments/assets/49e274a8-8f1d-40c1-9d1d-47210dc129da)
#### Customer Data
![CUSTOMER DATA EXCEL](https://github.com/user-attachments/assets/6aca2dbb-d96c-44b8-b617-f0922dac5ee8)

### Microsoft PowerBI
#### Sales Data
![SALES DATA POWERBI](https://github.com/user-attachments/assets/a5be47e2-2f18-4d20-91d9-2c315f8eb691)
#### Customer Data
![CUSTOMER DATA POWERBI](https://github.com/user-attachments/assets/0f70d478-74be-4da7-a4af-4ff20259cd95)


## Thank you
