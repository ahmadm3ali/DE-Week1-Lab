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

1. Issue and recommendation:Some orders have missing customer city values. These records
    should be checked or excluded from city-based reports because they cannot be 
    assigned to the correct city.
2. Issue and recommendation:Some orders have a quantity of zero. These records should
    be checked and excluded from valid sales calculations because they do not represent a 
    positive quantity sold.

## What the pipeline does
The pipeline loads daily order data from orders.csv into BigQuery,
checks for missing cities and invalid quantities, removes duplicate orders,
and produces a clean report for the shop manager.

## BigQuery Results
Raw table: DE_Intro.orders
- Rows loaded: 8
- Rows with a missing city: 1
- Rows with a non-positive quantity: 1
- Rows returned by the filtered query: 5