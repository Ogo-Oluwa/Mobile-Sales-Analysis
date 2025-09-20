# Mobile Sales Analysis

## Overview:
 *This is a sales report for Mobile Sales Products*
 
---
## Contents
Project Overview | Data Source | Tools Used | Table Outlay | Query Languages (SQL) | Visualization

---

## Project Overview:
>> This project analyzes the sales of Mobile Sales Products to uncover insights on sales distribution by various attributes such as Brands, Customer Gender and Payment Method, Using pivot tables, I explored metrics like total sales by Payment method and Gender, average income of buyers, gender distribution and overall revenue. This analysis helps to understand the key factors driving sales in the dataset provided.

## Data Sources:
www.kaggle.com/dataset

## Tools Used:
+ Pivot Table / Charts
+ PowerBI
+ SQL

## Table Outlay:
First Three Records

| TransactionID | Date | MobileModel | Brand | Price | UnitsSold | TotalRevenue | CustomerAge | CustomerGender | Location | PaymentMethod |
|-----|-----|-----|------|-----|-----|-----|------|-----|-----|------|
| 79397f68-61ed-4ea8-bcb2-f918d4e6c05b |	06/01/2024 |	direction |	Green Inc |	1196.95	| 85	| 28002.8	| 32	| Female	| Port Erik|	Online |
| 4f87d114-f522-4ead-93e3-f336402df6aa | 05/04/2024 |	right |	Thomas-Thompson |	1010.34 |	64 |	2378.82 |	55 |	Female |	East Linda|	Credit Card |
| 6750b7d6-dcc5-48c5-a76a-b6fc9d540fe1 |	02/13/2024 |	summer |	Sanchez-Williams |	400.8 |	95 |	31322.56 |	57 |	Male |	East Angelicastad |	Online |

## Query Language: (SQL)
Some of the query language to retrieve records are displayed here
```SQL
--- Categorize data into gold, silver, diamond customers
 SELECT *, 
CASE
	WHEN price < 500 THEN 'Silver'
	WHEN price BETWEEN 500 AND 800 THEN 'gold'
	else 'Diamond'
	END AS 'Level'
FROM mobile_sales;
```


```SQL
--- Retrieve all female customers that bought goods above 900---
SELECT * FROM mobile_sales
WHERE CustomerGender = 'Female'
AND price > 900;
```

```SQL
--- Retrieve the most expensive brand ---
SELECT Brand, MAX(price) AS 'price' FROM mobile_sales
GROUP BY Brand
ORDER BY price DESC;
```
```SQL
--- Retrieve number of available brands ---
SELECT COUNT(DISTINCT Brand) AS 'No. of Brands Available' FROM mobile_sales;
```
