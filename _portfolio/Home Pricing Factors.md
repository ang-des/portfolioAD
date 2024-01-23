---
title: Home Pricing Factors
image: assets/img/portfolio/02-full.jpg
alt: Keep Exploring

caption:
  title: Explore
  subtitle: Graphic Design
  thumbnail: assets/img/portfolio/02-thumbnail.jpg
---

This presentation analyzes the factors that drive home prices by providing data-driven insights for an investment bank. Variables that provide impact on prices will be identified in order to provide informed decisions on how to allocate dollars earmarked for investment into mortgage-backed securities.  

## About the Data

This data set was a sample of 1,460 houses that were sold between 2006 and 2010 in Ames, Iowa.

There are 81 columns with a good distribution between numerical and categorical data.

This data was retrieved from [Kaggle](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data).

## Research Questions

1. What factors influence the selling price of a home? (characteristics such as quality, number of bedrooms, etc.)
2. Which type of homes are most frequently sold in the market; is there a relationship between the age or condition and their selling prices?
3. Are there any observable patterns or trends indicating which combinations of home types and neighborhoods attract the highest number of buyers/selling price?
4. Do certain neighborhoods have higher home prices compared to others?

## Methods

Find correlations between numerical data and the housing sale price

Used descriptive statistics, A/B testing with t-tests, PivotTables, and PivotCharts to provide insights into central tendencies and relationships between variables.

Assess the quality of the data, handling missing values, and detecting outliers.

Incorporate visualizations to identify patterns and relationships with data.

## Methods Explained

This project was done using Excel, splitting data into treatment and control groups, while utilizing pivot tables and the Data Analysis ToolPak to manipulate data.

Based on insights from using Exploratory Data Analysis, new columns of data were created in order to get the proper data needed for t-tests.

Confidence intervals were also calculated for the hypotheses in order to accept or reject the null.

## Results

### Neighborhoods

The top neighborhood to bring in the highest average sales for homes is: North Ames, which accounted for 14.42% of total sales and generated a revenue of $32,815,593.

College Creek and Northridge Heights are other neighborhoods that could be of interest.

### Bedrooms

3 bedroom homes were sold the most, comprising of 55.07% of total home sales with a revenue of $145,569,724.

With 95% confidence, the difference in means is between $32,101 and $13,617.

Rejected the null that there is no significant difference in means between houses that have 2 bedrooms and those that have 3.

### Car Garages

2 car garages sold the most consisting of 56.44% of homes sold with the revenue at $151,493,771.

With 95% confidence, the difference in means is between $73,817 and $90,507.

Rejected the null that there is no significant difference in means between houses with and without garages.

### Fireplaces

The average sale price was higher for homes with 2-3 fireplaces inside, but the most sales came from homes with 0-1 fireplace, with 47.25% (0) and 44.52% (1) of total home sales along with $97,518,723 (0) and  $137,698,541 (1) in revenue.

With 95% confidence, the difference in means is between $68,087 and $82,044.

Rejected the null that there is no significant difference in means between houses that have fireplaces and those that don’t.

### Overall Quality

Higher quality homes (6-10 rating) sold more than lower quality homes, accounting for 63.15% of total home sales and brought in $196,554,295 in revenue.

With 95% confidence, the difference in means is between $93,420 and $81,678.

Rejected the null that there is no significant difference in means between houses with a quality rating of 1-5 (low) and those with a quality rating of 6-10 (high)

### Central Air

Homes with Central Air sold more than homes without it, accounting for 93.49% of total home sales and brought in $254,144,859 in revenue.

With 95% confidence, the difference in means is between $71,662 and $90,182.

Rejected the null that there is no significant difference in means between houses that have central air and those that do that.

<p align="center">
  <br>
  <img src="https://github.com/ang-des/home-prices-business-research/blob/main/images/all-graphs.png?raw=true" alt="all graphs" width=700>
</p>

## Top variables that drive home prices

1. Overall Quality
2. Garage Cars
3. Fireplaces
4. Year remodel added
5. Year built
6. Neighborhoods

## Call to Action

Based on these findings, specific factors exert a significant influence on the prices of homes in the market. When making informed decisions about investing in mortgage-backed securities, it is crucial to take into account these factors and their impact on home prices.

## Recommendations

Give priority to three-bedroom homes, as they have the highest sales volume and generate substantial revenue.

Pay close attention to neighborhoods like North Ames, College Creek, and Northridge Heights, which have shown promising sales performance.

Give preference to homes with Central Air Conditioning, as they are in high demand  among buyers.

Consider properties with two-car garages, as they have demonstrated strong sales performance. 

Evaluate homes with an overall quality rating of 6 to 10, as they attract a significant number of buyers. 
