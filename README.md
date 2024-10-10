# Cece-Cycling-Services-Analysis


### Table of Contents
1. [Project Overview](#project-overview)
2. [Tools](#tools)
3. [Data](#data)
4. [Data Analysis](#data-analysis)
5. [Power BI Visualizations](#power-bi-visualizations)
6. [Insights](#insights)
7. [Recommendations](#recommendations)
8. [Conclusion](#conclusion)

### Project Overview
---
In this project, I developed key performance metrics for Cece's Cycling Services, focusing on hourly revenue analysis, profit trends, seasonal revenue, and rider demographics. The analysis highlights opportunities for revenue management within the shared economy of urban mobility.

### Data
The data i worked with was already cleaned and prepared. What i did to make the analysis process easily was go through the data and understand each column. Any further data modelling needed was done in Power BI through Data transformation

## Tools 
- SQL Server: Used for data manipulation and querying.
- Power BI: Used for data visualization and creating dashboards.

### How I Used the Tools
1. SQL Server: I imported the dataset and utilized Common Table Expressions (CTE) and LEFT JOIN queries to analyze the data effectively.

     WITH HourlyRevenue AS (
       SELECT 
           DATEPART(HOUR, RentalTime) AS RentalHour,
           SUM(Revenue) AS TotalRevenue
       FROM 
           Rentals
       GROUP BY 
           DATEPART(HOUR, RentalTime)
   )
   SELECT 
       hr.RentalHour,
       hr.TotalRevenue,
       pd.Profit
   FROM 
       HourlyRevenue hr
   LEFT JOIN 
       ProfitData pd ON hr.RentalHour = pd.RentalHour
   ORDER BY 
       hr.RentalHour;
   
2. Power BI: After processing the data in SQL Server, I imported it into Power BI to create visualizations, including:
   - Hourly Revenue Trends: A line chart showing revenue changes throughout the day.
   - Profit Analysis: A bar chart comparing profits across different hours and days.
   - Demographic Insights: A pie chart visualizing rider demographics.

## Insights
- Positive Demand Elasticity: The analysis revealed that increasing prices could lead to higher demand, indicating effective pricing strategies.
- Seasonal Patterns: Revenue trends suggest fluctuations based on time of year, allowing for strategic planning and marketing.

## Recommendations
- Price Adjustment: Consider raising prices based on identified demand elasticity to maximize revenue.
- Partnership Development: Explore potential B2B partnerships with local businesses to enhance visibility and attract more customers.
- Targeted Marketing: Develop campaigns aimed at specific demographics to improve usage during off-peak seasons.

## Conclusion
This project showcases my skills in data analysis, SQL proficiency, and data visualization within the urban mobility sector. The findings provide actionable insights for improving revenue management strategies in the shared economy.
`

### Additional Notes:
- Power BI Visualizations: You can add more specific details about the visualizations you created in Power BI if you want to elaborate further.
- Insights and Recommendations: These sections are concise; feel free to expand on them if you have more detailed observations or suggestions based on your analysis.
