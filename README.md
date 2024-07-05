# Quantium-Data-Analytics-Virtual-Experience-Program
This repository contains results of the completed tasks for the Quantium Data Analytics Virtual Experience Program by Forage, designed to replicate life in the Retail Analytics and Strategy team at Quantium, using Python.
This program consisted of three task and the following submissions were made

- Data preparation and customer analytics

- Experimentation and uplift testing

- Analytics and commercial application

# Dependencies
Python Version: 3.7

Packages: pandas, numpy, seaborn, sklearn, matplotlib, datetime, scipy

# Task 1 - Data preparation and Customer Analytics
Conduct analysis on your client's transaction dataset and identify customer purchasing behaviours to generate insights and provide commercial recommendations.

## Background information for the task
We need to present a strategic recommendation to Julia that is supported by data which she can then use for the upcoming category review however to do so we need to analyse the data to understand the current purchasing trends and behaviours. The client is particularly interested in customer segments and their chip purchasing behaviour. Consider what metrics would help describe the customers’ purchasing behaviour.

## Main goals of this task are :
- Examine transaction data - check for missing data, anomalies, outliers and clean them
- Examine customer data - similar to above transaction data
- Data analysis and customer segments - create charts and graphs, note trends and insights
- Deep dive into customer segments - determine which segments should be targetted
  
## Data Cleaning:
- Date column was in integer format. So the date column was changed to date time format.
- There are 365 days in a year but in the DATE column there are only 364 unique values so one was missing. As it was a Christmas day and store was closed there was no anomaly. Value was kept as zero transaction for "TOT_SALES".
![December_Sales](https://github.com/cwiredu1/Quantium-Data-Analytics-Virtual-Experience-Program/assets/121901813/6127404b-a599-478d-a7fa-f356d519faa1)

- Data is checked if all the products in given data are chips.
- There were some product names that were written in more than one way. Example : Dorito and Doritos, Grains and GrnWves, Infusions and Ifzns, Natural and NCC, Red and RRD, Smith and Smiths and Snbts and Sunbites. It was cleaned thereafter.
- Split and frequency of each word in "PROD_NAME" column. Removed all rows containing "salsa" in "PROD_QTY" column.
- Checked for outliers and removed outliers rows in "PROD_QTY" column.
- Each word value was counted in "PROD_NAME" column to extract the brand name. Combined brands written in multiple ways. Created a new column "Cleaned_Brand_Names".
![Brand_Names](https://github.com/cwiredu1/Quantium-Data-Analytics-Virtual-Experience-Program/assets/121901813/8cba7c55-b3bd-4712-ab40-f192ecc5ecf8)

## Data Analysis on Customer Segments
- The 4 main questions answered in data analysis were:
1. Who spends the most on chips (total sales), describing customers by lifestage and how premium their general purchasing behaviour is
2. How many customers are in each segment
3. How many chips are bought per customer by segment
4. What's the average chip price by customer segment

Groupby sum TOT_SALES column and identified top 3 highest total sales contributing segments.
Plot the groupby into stacked bar chart with percentage text on each segment stack.
![Stage_Plot1](https://github.com/cwiredu1/Quantium-Data-Analytics-Virtual-Experience-Program/assets/121901813/2808c5a6-57a3-48e3-85bc-dac0e0cfb6ac)

## Insights:

- The three highest contributing segments to total sales are: 
1. Budget older families,
2. Mainstream young singles/couples,
3. Mainstream retirees
- Older families have largest avg no of packets purchased per customer, while the mainstream young singles/couples have the largest population
- Across most segments, Kettles chips and 175g packets are the most purchased
- Minstream young singles/couple are 28% more likely to purchase Tyrells chips than other segments, and 32% more likely to purchase 270g chip packets which are Twisties chips

# Task 2 - Experimentation and Uplift Testing
Extend your analysis from Task 1 to help you identify benchmark stores that allow you to test the impact of the trial store layouts on customer sales.

## Background Information for the task
Julia has asked us to evaluate the performance of a store trial which was performed in stores 77, 86 and 88.

This can be broken down by:

- total sales revenue
- total number of customers
- average number of transactions per customer
  
Create a measure to compare different control stores to each of the trial stores to do this write a function to reduce having to re-do the analysis for each trial store. Consider using Pearson correlations or a metric such as a magnitude distance e.g. 1- (Observed distance – minimum distance)/(Maximum distance – minimum distance) as a measure. Once you have selected your control stores, compare each trial and control pair during the trial period. You want to test if total sales are significantly different in the trial period and if so, check if the driver of change is more purchasing customers or more purchases per customers etc.

## Insights:
- We can see that Trial store 77 sales for Feb, March, and April exceeds 95% threshold of control store. Same goes to store 86 sales for all 3 trial months.
1. Trial store 77: Control store 233
2. Trial store 86: Control store 155
3. Trial store 88: Control store 40
   
- Both trial store 77 and 86 showed significant increase in Total Sales and Number of Customers during trial period. But not for trial store 88. Perhaps the client knows if there's anything about trial 88 that differs it from the other two trial.
- Overall the trial showed positive significant result.
