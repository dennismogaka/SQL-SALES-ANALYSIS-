# SQL-SALES-ANALYSIS
# Table of Contents  
- [ Project Overview](#project-overview)  
- [ Project Objective](#project-objective)  
- [ Data Used](#data-used)  
- [ Project Structure](#project-structure)  
- [ Findings](#findings)  
- [ Conclusion](#conclusion)
## PROJECT OVERVIEW
## Project Title: SQL Sales Analysis
## Database:
This project is designed to demonstrate SQL skills and techniques typically used by data analysts to explore, clean and analyze sales data. The project involves performing exploratory data analysis (EDA) and answering specific business questions through SQL Queries.
## OBJECTIVES
1.	Data Cleaning: Identify and fill any records with missing and NULL values.
2.	Exploratory Data Analysis [EDA]: Perform basic Exploratory data analysis to understand the data set.
3.	Business Analysis: Use SQL to answer specific questions and derive insights from the sales data.
## PROJECT STRUCTURE
#### 1.	DATA EXPLORATION AND CLEANING
#### •	Record Count: Determine the total number of records in the total number of records in the dataset.
#### •	Customer Count: Find out how many unique customers are in the dataset.
#### •	Category Count: Identify all the unique product categories in the dataset.
#### •	Blanks: Check for any missing values in the dataset and derive records with missing values.
### 2.	DATA ANALYSIS AND FINDINGS
The following SQL Queries were developed to answer specific business questions.

1.**write a query to retrieve all records from a table name sample_sales_data**:

```sql
SELECT COUNT(*) FROM `sample_sales_data`;
```

2.**Write a query to find average revenue**.
```sql
SELECT CAST(AVG(`COL 12`) AS DECIMAL(10,0)) AS AVg_Revenue"
"FROM sample_sales_data;"
```
3.**write a query to find the mode for column7**.
```sql
SELECT `COL 7` AS Mode_Quantity,
COUNT(*) FROM sample_sales_data
GROUP BY `COL 7`
ORDER BY COUNT(*) DESC
LIMIT 1;
```
4.**write a query to find the total number of unique categories**.
```sql
SELECT COUNT(DISTINCT `COL 6`) AS Number_categories FROM sample_sales_data;
```
5.**write a query to identify the unique categories**.
```sql
SELECT DISTINCT `COL 6` as u_categories FROM sample_sales_data;
```
6.**write a query to identify unique stores**.
```sql
SELECT DISTINCT `COL 3` AS u_stores FROM sample_sales_data;
```
7.**write a query to find out the number of unique stores**.
```sql
SELECT COUNT(DISTINCT `COL 3`) AS Number_stores FROM sample_sales_data;
```
8.**write a query to identify number of product_IDS**.
```sql
SELECT COUNT(DISTINCT `COL 5`) AS Number_productid FROM sample_sales_data;
```
9.**write a query to calculate the total revenue**.
```sql
SELECT CAST(SUM(`COL 12`) AS DECIMAL(10,0)) AS Total_Revenue FROM sample_sales_data;
```
11.**write a query to calculate total revenue per product category**.
```sql
SELECT `COL 6`,
      ROUND(SUM(`COL 12`),0) AS Total_revenuep
      FROM sample_sales_data
      GROUP by `COL 6`
      ORDER BY `COL 12`;
```      
13.**write a query to extract blanks from the database**.
```sql
select * from sample_sales_data
where `COL 1` = ' '
OR 
`COL 2` = ' '
OR
`COL 3` = ' '
OR
`COL 4` = ' '
OR
`COL 5` = ' '
OR
`COL 6` = ' '
OR
`COL 7` = ' '
OR
`COL 8` = ' '
OR
`COL 9` = ' '
OR
`COL 10` = ' '
OR
`COL 11` = ' '
OR
`COL 12` = ' ';
```
15.**write a query to fill the blanks in column 6 with 'unknown'**.
```sql
UPDATE sample_sales_data
SET `COL 6` = 'unknown'
WHERE `COL 6` = ' ';
```
16.**select columns in `COL 6` with unknown**.
```sql
SELECT * FROM sample_sales_data
WHERE `COL 6`= 'unknown';
```
17.**write a query to set col 8 to whole numbers**.
```sql
SELECT 
     ROUND(`COL 8`,0)
     FROM sample_sales_data;
```
# FINDINGS
•	Yearly sales show variation in sales helping identify peak years.
•	The analysis identifies the top spending customers .
•	The analysis identifies the most sold product category.
•	It also identifies the region with highest revenue.
•	The channel with highest revenue in the four years is also identified.
# CONCLUSION
The project covers data cleaning, Exploratory Data Analysis [EDA] and business driven SQL Queries. The findings from the project will be of great help in driving business decisions by understanding sales patterns, customer behavior , discount impact on sales and product performance.

 END OF PROJECT   
