# LITA-Capstone-Project-Customer
This shows one of the two final projects I worked on while undergoing the Ladies in Tech Africa training organised by The Incubator Hub.

[Project Title](project-title)

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

### Project Title: Customer Data Analysis

### Project Overview
The aim of this project is to analyze the customer data of a subscription service. The goal was to understand customer behaviour, track subscription types and identify key trends in cancellations and renewals.

### Data Sources
The data used is LITA Capstone Dataset.xslx and was provided on the LMS portal by the tutors.

### Tools Used
- Microsoft Excel- Data Cleaning and Analysis
- SQL(Structured Query Language)- Data Querying
- Microsoft PowerBI- Data Visualization
- GitHub- Documentation and Portfolio Building

### Data Cleaning and Preparations
The following actions were performed before the data was worked on for analysis and visualization:
1. Data loading and inspection
2. Removal of duplicates

### Exploratory Data Analysis
The data was explored to answer questions like:
- the total number of customers from each region.
- the most popular subscription type by the number of customers.
- customers who canceled their subscription within 6 months.
- the average subscription duration for all customers.
- customers with subscriptions longer than 12 months.
- total revenue by subscription type.
- the top 3 regions by subscription cancellations.
- the total number of active and canceled subscriptions.

### Data Analysis
Listed below are the queries I used in answering the questions:

```SQL
select region, COUNT(customerid) as Amount_of_Customers from customerdata
group by region
order by 2 desc

select top(1) subscriptiontype, count(customerid) as Popular_Subscription from customerdata
group by subscriptiontype
order by 2 desc

select * from customerdata
where canceled = 1
and subscriptionduration < 183
select count(customerid) from customerdata
where canceled = 1

select AVG(subscriptionduration)as Average_Subscription_Duration from customerdata

select * from customerdata
where subscriptionduration > 366

select subscriptiontype, sum(revenue) as TotalRevenue from customerdata 
group by subscriptiontype
order by 2 desc

select top(3) region, count(customerid) as SubscriptionCancellation from customerdata
where canceled = 1
group by region
order by 2 desc

select count(customerid) as Active_Subscriptions from customerdata
where canceled = 0

select count(customerid) as Canceled_Subscriptions from customerdata
where canceled = 1
```

### Data Visualization
Here are some tables and dashboards from Microsoft Excel and Microsoft PowerBI;

|Region|Total Revenue|
|------|-------------|
|North|16,817,972|
|West|16,864,376|
|South|16,899,064|
|East|16,958,763|
|Grand Total|67,540,175|

|Subscription Type|Total Revenue|
|-----------------|-------------|
|Standard|16,864,376|
|Premium|16,899,064|
|Basic|33,776,735|
|Grand Total|67,540,175|

|Region|Amount of Customers|
|------|-------------------|
|West|8,420|
|North|8,433|
|South|8,446|
|East|8,488|
|Grand Total|33,787|

|Subscription Type|Amount of Customers|
|-----------------|-------------------|
|Standard|8,420|
|Premium|8,446|
|Basic|16,921|
|Grand Total|33,787|

![Customer Excel](https://github.com/user-attachments/assets/0b284ab9-e080-42c4-ae28-1b98a987af5b)

<img width="575" alt="New Customer BI" src="https://github.com/user-attachments/assets/76d774da-b980-44d1-a057-5147771e7d04" />
