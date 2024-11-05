# LITA-CAPSTONE-DATA-PROJECT
## This is my first independent project from the LITA Data Analysis training
## Project Overview 1
This is the data for Nationwide Sales that shows products, quantities, prices and revenue across four regions
## Data Sources
The primary source of data is the excel spreadsheet sent to our Canvass Learning Management System for this Project
## Tools Used
- Microsoft Excel
  1. Data Cleaning
  2. Data Analysis
  3. Data Visualization
     
- SQL- Structured Query Language
  1. Data Cleaning
  2. Data Analysis
  3. Data Visualization
     
- Microsoft PowerBI
  1. Data Cleaning
  2. Data Analysis
  3. Data Visualization

- GitHub for Portfolio Building

## Data Analysis
This is where I included some basic lines of codes, queries and DAX used during my analysis

```SQL
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
