# Week 1 Data Engineering Lab

## Scenario
A small online shop sends daily order data as a CSV file. A manager wants a reliable summary of valid orders by city.

## Pipeline plan
- Source: `orders.csv` (daily batch file)
- Raw destination: BigQuery table `de_intro.raw_orders`
- Curated output: query results after checking and filtering the data
- User of the output: shop manager

## Local data check
Before reporting, record at least two issues you found in the CSV and what you recommend doing with each.

1. Issue and recommendation: The problem that would make the report inaccurate:
O-1006 is listed 2 times, which is wrong because it could be counted twice
O-1004 has a missing customer_city field, which can make reports by city inaccurate
O-1005 says that the stautus is delivered but the quantity is 0, this could affect the sales and quantity reports

2. Issue and recommendation: The CSV file has 8 order records. I found one duplicate order, one missing city
and one order with a 0 quantity.
These problems can affect the accuracy of sales totals, order counts and city-based reports. 
The data should be checked before creating the final report

## What the pipeline does
Complete after the lab: In one sentence, describe how the data moves from the source to a useful output.
