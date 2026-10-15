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
Complete after the lab: In one sentence, describe how the data moves from the source to a useful output.
