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
- Data Cleaning:
- Date column was in integer format. So the date column was changed to date time format.
There are 365 days in a year but in the DATE column there are only 364 unique values so one was missing. As it was a Christmas day and store was closed there was no anomaly. Value was kept as zero transaction for "TOT_SALES".
