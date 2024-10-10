# Cece-Cycling-Services-Analysis


### Table of Contents
1. [Project Overview](#project-overview)
2. [Data](#data)
3. [Tools](#tools)
4. [SQL Server](#sql-server)
5. [Power BI](#power-bi)
6. [Insights](#insights)
7. [Recommendations](#recommendations)


### Project Overview
---
In this project, I developed key performance metrics for Cece's Cycling Services, focusing on hourly revenue analysis, profit trends, seasonal revenue, and rider demographics. The analysis highlights opportunities for revenue management within the shared economy of urban mobility.

### Data
---
The data i worked with was already cleaned and prepared. What i did to make the analysis process easily was go through the data and understand each column. Any further data modelling needed was done in Power BI through Data transformation

## Tools 
---
- SQL Server: Used for data manipulation and querying.
- Power BI: Used for data visualization and creating dashboards.


### SQL Server
---
 I imported the dataset and utilized Common Table Expressions (CTE) and LEFT JOIN queries to analyze the data effectively.
 ```
with cte as
(
select * from bike_share_0
union
select * from bike_share_1 
)
select dteday,season, b.yr,mnth,weekday,hr,rider_type,riders,price, COGS,
riders* price as revenue,
riders*price - COGS*riders as profit
from cte b
left join cost_table c
on b.yr = c.yr;
```
   
###Power BI
---
 After quering the data in SQL Server, I imported it into Power BI where i did the transformation needed in order to visualize Key Performance Metrics. These KPMetrics included;
   - Hourly Revenue Trends: A matrix chart showing revenue changes throughout the day.
   - Profit Analysis: A bar chart comparing profits across different hours and days.
   - Demographic Insights: A pie chart visualizing rider demographics.

### Insights
---
- Positive Demand Elasticity: The analysis revealed that increasing prices could lead to higher demand, indicating effective pricing strategies.
- Seasonal Patterns: Revenue trends suggest fluctuations based on time of year, allowing for strategic planning and marketing.

## Recommendations
---
- Price Adjustment: Consider raising prices based on identified demand elasticity to maximize revenue. A 10-15% 
increase in price could be set to test the market's 
response without risking a significant loss of customers.
- Partnership Development: Explore potential B2B partnerships with local businesses to enhance visibility and attract more customers.
- Market Analysis: Conduct future market research to understand market structures like customer satisfaction, potential competitive changes and the overall economic environment. This can guide us in increasing or decrease pricesegmented
- Pricing Strategy: Consider different pricing for causual and registered riders,as they may have different price sensitivities.

