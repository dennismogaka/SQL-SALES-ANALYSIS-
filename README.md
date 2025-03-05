## SQL-SALES-ANALYSIS

**write a query to retrieve all records from a table name sampl_sales_data**:

'''sql
SELECT COUNT(*) FROM `sample_sales_data`;
'''

/*Write a query to find average revenue*/
"SELECT CAST(AVG(`COL 12`) AS DECIMAL(10,0)) AS AVg_Revenue"
"FROM sample_sales_data;"

/*write a query to find the mode for column7*/
SELECT `COL 7` AS Mode_Quantity,
COUNT(*) FROM sample_sales_data
GROUP BY `COL 7`
ORDER BY COUNT(*) DESC
LIMIT 1;

/*write a query to find the total number of unique categories*/
SELECT COUNT(DISTINCT `COL 6`) AS Number_categories FROM sample_sales_data;

/*write a query to identify the unique categories*/
SELECT DISTINCT `COL 6` as u_categories FROM sample_sales_data;

/*write a query to identify unique stores*/
SELECT DISTINCT `COL 3` AS u_stores FROM sample_sales_data;

/*write a query to find out the number of unique stores*/
SELECT COUNT(DISTINCT `COL 3`) AS Number_stores FROM sample_sales_data;

/*write a query to identify number of product_IDS*/
SELECT COUNT(DISTINCT `COL 5`) AS Number_productid FROM sample_sales_data;

/*write a query to calculate the total revenue*/
SELECT CAST(SUM(`COL 12`) AS DECIMAL(10,0)) AS Total_Revenue FROM sample_sales_data;

/*write a query to calculate total revenue per product category*/
SELECT `COL 6`,
      ROUND(SUM(`COL 12`),0) AS Total_revenuep
      FROM sample_sales_data
      GROUP by `COL 6`
      ORDER BY `COL 12`;
      
/*write a query to extract blanks from the database*/
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

/*write a query to fill the blanks in column 6 with 'unknown'*/
UPDATE sample_sales_data
SET `COL 6` = 'unknown'
WHERE `COL 6` = ' ';

/*select columns in `COL 6` with unknown*/
SELECT * FROM sample_sales_data
WHERE `COL 6`= 'unknown';

/*write a query to set col 8 to whole numbers*/
SELECT 
     ROUND(`COL 8`,0)
     FROM sample_sales_data
    
