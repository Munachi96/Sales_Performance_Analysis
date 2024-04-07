# Sales_Performance_Analysis_for_a_Telecom_Company_USA
A Data Analysis Project that Analysed the sales performance of a Telecommunication company Based in the United State. The company’s sales transaction data generated over the past years was used for this analysis.

# Project Overview:
This Data Analysis Project aims to provide insights into the sales performance of a Telecommunication company Based in the United State.

__About the Company:__ The Telecommunication Company operates a B2B business model and
sells a wide variety of cell phones and devices, including __smartphones, tablets,
smartwatches__. They offer devices from all of the major manufacturers, such as Apple,
Samsung, Google, and Motorola.
Various aspects of the company’s sales transaction data generated over the past years was
analysed to gain insights into their Customer Behaviour, Product Popularity, Top Performing
Channel of Marketing, Regional Performance and Revenue Trends of the company since it
began.
We seek to identify Top performing customers, products, channels of sales , region , trends, and
the overall performance of the company , to enable the company to make data-driven
decisions/recommendations and to gain a deeper understanding of the company’s overall
performance.

# Data Sources:
Sales Transaction Data : The primary dataset used for this data analysis project was sales
transaction data, containing detailed information about each sales made by the company , and
was extracted from the company’s database using SQL codes.
Several SQL complex queries were written to the company’s database in order to extract the
required data for this data analysis project.
Each SQL complex query was used to extract a particular aspect of the company’s sales data.
The results were downloaded and saved as the following csv files below: <br> <br>

“customers_behaviour.csv” <br> <br>
“revenue_generated_by_channels_all_time.csv” <br> <br>
“revenue_generated_by_region_all_time.csv” <br> <br>
“revenue_trend_over_the_years.csv” <br> <br>

# Data Analysis Tools Used:

- __SQL (PostgreSQL)__
     - for Data Collection
     - for Data Cleaning
     - for Data Analysis
- __Power BI__
    - for Data Modelling
    - for Data Analysis
    - for Data Visualization and Creating an Interactive Report.
 
 # Data Collection:
 - __Database Inspection__ :In the initial data collection phaseI inspected the company’sdatabase using __SQL__ code to check for missing data __(NULL)__ in each of the 
    tables in the company’s database.
 - I extracted the required data for the purpose of the data analysis project using __SQL__
 __complex query__  and __SQL data aggregation__

 # Data Cleaning and Formatting:
- I used __SQL__ codes to clean and format the data to conform to the required data format.
- I downloaded the result of my  __SQL__ Queries from the company’s database as a csv file to my PC.

 # Loading Data into Power BI:
- I loaded the downloaded csv files into __Power BI__ for the purpose of Data Visualization and Building interactive dashboard/report.

 # Exploratory Data Analysis (EDA): EDA involves exploring the sales data in order to answersome key questions such as :
- Who are the top 10 customers of the company ?
- What particular products are the Top customers buying ?
- Comparative analysis to find out the top selling product ?
- What Is the Total quantity of items a particular customer has ever bought from thecompany ?
- What is the Total revenue generated by the company from a particular customer ?
- What are the top performing channels of sales ?
- What is the Total quantity of items sold through a particular channel ?
- What is the Total Revenue generated through a particular channel ?
- Which region is the best performing region ?
- What is the Total quantity of items sold in a particular region ?
- What is the Total Revenue generated in a particular region?
- What is the peak sales period ?
- What is the sales performance at a particular given time (year, month, day) ?
- What is the sales trend between a particular period of time ?
- What is the overall sales Trend of the company over the years ?
- What is the overall sales performance of the company ?

# Data Analysis :

```SQL
/* QUERY 1: SQL CODE SOLUTION FOR EXTRACTING THE Total Items and Total
revenue generated by each customer (CUSTOMERS BEHAVIOUR) */
SELECT a.name AS customers_name,
SUM(o.smartphones_qty) ,
SUM(o.smartwatches_qty),
SUM(o.tablets_qty),
COUNT(a.name) AS No_of_Transaction,
SUM(o.total) AS total_quantity,
SUM(o.total_amt_usd)AS total_revenue_usd
FROM accounts a
JOIN orders o
ON a.id = o.account_id
GROUP BY customers_name
ORDER BY total_revenue_usd DESC


```
