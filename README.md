# STUDENT: sebera isimbi ange thressy
# ID:28389
## DEPARTMENT: SOFTWARE Engineering
# PL-SQL-Window-Functions
## Course:  Database Development with PL/SQL
## Lecturer: Eric Maniraguha
                              Assignment on PL/SQL Window Functions 2026
                              
   STEP 1
   
Business Context:

ishingiro Supermarket has branches across all rwanda and it wants to understand its customer's behaviour and how their product are performing among their branches the sales and marketing team needs reliable information for sales and stock planning

Data challenge:

the company has recorded many transactions and therefore there are unable to see which products are selling most in all districts and they are unable to see if number of customers is increasing or not and without these information sales can not increase on higher level to meet the demand

Expected Outcome:

to get information of best selling products in districts ,getting total sales that happened in the whole month and all this data then will be used to target customers

STEP 2 
Find the Top 5 Products in Each Region:
I will use the RANK() window function to see which products are selling the most in each region.

Calculate Running Total of Monthly Sales:
I will use SUM() OVER() to add up monthly sales and show how the total grows month by month.

Check Month-to-Month Sales Change:
I will use LAG() to compare each month’s sales with the previous month and see the difference.

Group Customers into 4 Spending Levels:
I will use NTILE(4) to divide customers into four groups based on how much they spent.

Find 3-Month Moving Average of Sales:
I will use AVG() OVER() to calculate the average sales for every 3-month period.

STEP 3  
Customer Table sql code
![Customers Table sql](/images/Customer%20sql%20croped.png)

customer table sql code


The customers table stores information about all our customers.  
It includes a unique ID for each customer, their name, and the region they belong to.  
This table helps us track who is buying our products and where they are located.
![Customers Table](/images/CUSTOMER%20TABLE.jpg)

Product table 

product table sql 

![Product table sql ](/images/product%20sql%20croped.png)


The Products table stores all items available in the catalog.  
It includes the product ID, name, and category.

![Product table](/images/Product%20table.png) 

Transaction table sql code

![Transaction table sql ](/images/transaction%20sql%20cropped.png) 

Transactions table 
The Transactions table records all sales made by customers.  
It includes the transaction ID, the customer and product involved (via foreign keys), the sale date, and the amount.  
This table connects Customers and Products to analyze sales, trends, and customer behavior.
![Transaction table](/images/Transaction%20table.png)  

ER diagram 

![ER diagram](/images/ER%20diagram.png) 


STEP 4 
RANK sql code 

![RANK sql code](/images/rank%20sql%20.png) 

Interpretation:
These functions rank customers based on total revenue. ROW_NUMBER() gives a unique sequence, RANK() allows ties, DENSE_RANK() avoids gaps in ranks, and PERCENT_RANK() shows relative position as a percentage.

rank results

![RANK results](/images/rank%20results%20.png)

Aggregate sql code 

![Aggregate sql code](/images/aggregate%20sql%20code.png) 

Interpretation:
The query calculates cumulative sales (running_total) and 3-day moving averages (moving_avg). This helps identify sales trends and monitor business performance over time.

Aggregate result

![Aggregate result](/images/distribution%20result.png) 


Navigation sql code

![Navigation sql code](/images/navigation%20sql.png) 

Interpretation:
LAG() compares current month sales with the previous month, showing growth. LEAD() shows the following month’s sales. This helps track changes over time and plan actions.

Navigation result 

![Navigation result](/images/navigation%20result.png) 


Distribution sql code

![Navigation sql code](/images/distribution%20sql.png) 

Interpretation:
NTILE(4) divides customers into 4 quartiles based on spending. CUME_DIST() shows each customer’s relative position. This helps segment customers for marketing or loyalty programs.

Distribution results 

![Distribution result](/images/distribution%20result.png) 

 STEP 6

1. Descriptive – What happened?

The Ranking functions showed the top customers by revenue. We can clearly see which customers spend the most and which are in the lower ranks.

The Aggregate functions revealed running totals and moving averages, highlighting sales trends over time.

The Navigation functions (LAG/LEAD) showed month-over-month growth and fluctuations, indicating periods of increased or decreased sales.

The Distribution functions segmented customers into quartiles, helping identify high-value versus low-value clients.

2. Diagnostic – Why did it happen?

Top customers appear in multiple transactions or high-value purchases, which explains their high ranks.

Fluctuations in monthly sales (seen in LAG/LEAD) are caused by seasonal buying patterns or promotions.

Running totals and moving averages trend upward when consistent sales occur; dips indicate fewer transactions.

Customer quartiles show natural spending distribution: a small percentage contributes to most revenue, while many customers spend less.

3. Prescriptive – What next?

Focus marketing campaigns on top-quartile customers to increase loyalty and repeat sales.

Monitor months with lower sales and consider promotions or discounts to boost revenue.

Use moving averages to forecast future sales and adjust inventory accordingly.

Analyze lower-quartile customers to understand barriers and improve their engagement.

- ## References
Oracle Docs – Window Functions

Oracle LiveSQL Tutorials

Mode Analytics SQL Guide

Vertabelo SQL Analytics Blog

SQLShack – Window Functions Examples

DataCamp – Advanced SQL Tutorial

Towards Data Science – SQL Analytics Articles

GeeksforGeeks – SQL Window Functions

LearnSQL.com – Partition By, Frame Clause

Analytics Vidhya – SQL Business Use Cases


"All sources were properly cited.implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation"







