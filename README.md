# Finance-Project

## Project Overview

This Data Analsis project aims to analyse the financial dataset to generate actionable insights in order to enhance the financial performance of the company.
By analyzing various aspect of the sales data, i seek to identify:
- what are the total sales for Actual & Target,
- What are the variance percentage,
- What are the YTD values,
- what are the salesperson performance like within the given period,
- How many months were targets met and
- What are the Teams performance like over the given period.

![Screenshot 2025-02-14 131719](https://github.com/user-attachments/assets/4efb4969-cc35-4a00-bd69-1a221677769d)


## Data Sources
Finance Data: The primary dataset used for this analysis comes in an Excel file, containing 4 different tables of information made by the company.
[Finance Analysis.xlsx](https://github.com/user-attachments/files/18799151/Finance.Analysis.xlsx)


## Analysis Tools Used
- Microsoft Excel
- Power Query
- Power BI for Visualization

## Data Cleaning and Preparation
In the initial Data Cleaning and Preparation Phase, i performed the following tasks:
1. Imported the data using power query
2. Unpivoted colums in power query
3. Used Power query to transform and add additional column
4. Removed Duplicates
5. Handled Blanks and Trimmed Spaces
6. Performed Data modelling where all dimensions tables where connected to fact tables.

## Exploratory Data Analysis
EDA involves exploring the Financial Dataset to answer key questions, such as:
- How many months were targets met in the given period?
- Which Team meant the most target?
- What are the YTD values for the given period?
- Which Salesperson meant most targets?
- What are the variance trend within the given period?

![Screenshot 2025-02-14 132013](https://github.com/user-attachments/assets/48aba2fe-309f-440e-80bf-55df9dd30acd)

![Screenshot 2025-02-14 132256](https://github.com/user-attachments/assets/a9f2a99b-25e6-4fb3-abdc-cd64c348e462)

## Data Analysis
Power BI was used for creating some measures using DAX Funcions. Some of the measures used for these analysis include:
``` Sql
Month Targets Reached = 
    VAR month_with_target_reached = FILTER(ALL('Calendar'), [Variance]>0)
RETURN
    COUNTROWS(month_with_target_reached)
```
``` Sql
Target status = IF([Variance]>0, 1, -1)
```
``` Sql
Trend chart title = 
    VAR month_count = COUNTROWS('Calendar')
RETURN
" We met targets for " & [Month Targets Reached] & " out of " & month_count 
```
``` Sql
YTD sales actual = CALCULATE([Total sales actual],DATESYTD('Calendar'[Date]))
```
``` Sql
Variance percentage Label = 
    VAR up = "🟢"
    VAR down = "🔴"
    VAR formatted_var_percentage = FORMAT(ABS([Variance %]), "0.0%")
RETURN
formatted_var_percentage & " " & IF([Variance %]>0, up, down)
```

## Findings
 The analysis results are summarized as follows:
1. Target were only met for 2 months out of the 14 months of the given period.
2. The largest positive variance was 5.5% in March, while other months were below targets.
3. The variance percentages indicate that top performers exceeded targets by up to 9%, while others had smaller margins.
4. Several months had a negative variance, with sales lagging behind projections.
5. The Yummies Team met most of the targets.
6. Only 11 salesperson met their targets.

## Recommendations
Based on the analysis conducted, i recommend the following:
### **Actionable Recommendations to Improve Performance:**
1. **Improve Sales Team Efficiency:**
   - Identify underperforming salespeople and provide targeted coaching or incentives.
   - Replicate the strategies of top performers to boost overall sales efficiency.

2. **Adjust Sales Targets Based on Trends:**
   - Since only 2 out of 14 months met targets, consider revising targets to be more realistic.
   - Introduce quarterly adjustments to reflect market conditions better.

3. **Increase Sales in Low-Performing Months:**
   - Identify why sales dipped in certain months (e.g., seasonality, external factors).
   - Implement promotions, discounts, or marketing pushes during historically weak months.

4. **Customer Engagement and Retention:**
   - Strengthen relationships with high-value customers through loyalty programs.
   - Offer personalized discounts or deals to repeat buyers.

5. **Optimize Product/Service Offerings:**
   - Analyze which products or services contributed most to missed targets.
   - Focus marketing efforts on high-margin or high-demand products.
