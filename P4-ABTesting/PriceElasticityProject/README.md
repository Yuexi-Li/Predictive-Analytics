# Pricing Elasticity Result 
## Outline 
- Treatment Units 
- Control Units 
- Prepare test 
- Run test 
- Analyze reults 


## Business Background 
- Pricing Elasticity
"Price elasticity of demand is a measure of the relationship between a change in the quantity demanded of a particular good and a change in its price. Price elasticity of demand is a term in economics often used when discussing price sensitivity

## Select Control variable 
- Discrete control varibale 
  - Region (need to segment each region)
- Continuous control variable 
  - Can be used to run the distance 
  - e.g. 
    - Avgerage sales per store per month 
    - average number of invoices per month per store 
    - SKU category (average number of facial/ average facial sales)
- Matching trend 
  - two common trend
    - growth in store traffic
      -> `invoices per week `
    - seasonal patterns in sales volume 
      -> `total sales per store`


## Data Preparation 
1. Prepare Data from two raw data files (found at the bottom of the page)

- Point of Sales Transaction file
- Treatment Stores file containing price levels and store identifiers

2. Create three data files:

Use these two raw data files to create 3 files. These files are:

- Weekly store traffic data for A/B Trend Tool -> Produces our seasonality and trend indices to help us match our treatment and control stores
- Store list data for A/B Controls tool -> Produces which control stores to match with our treatment stores along with results from the A/B Trend Tool
- Sales data for A/B Analysis tool -> Produces the final results

3. Use the three data files to match our treatment and control stores to calculate the sales lift.

### Data Cleaning 
**Traffic Data** 
- get store, week, week_sart, week_end, total_invoice number 
  - Transaction date:
    - Select out the invoice date between '2013-02-07' to '2014-05-28' And region is not null 
    - Create the Week_start, week_end , and week_number from 2013-02-07 
    -  Week_number 
        `FLOOR(DateTimeDiff([Invoice_Date], "2013-02-07", 'days') / 7+1)`
  - Select out stores with all sales information in each week 
    - Count distinct week = 68 
  - Aggregate the gross_margin and sales per records with  Facial flag (Count distinct not null facial flag)

**Sales Data** 
