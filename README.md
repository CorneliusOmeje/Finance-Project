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

![Screenshot 2024-11-30 021304](https://github.com/user-attachments/assets/5cc48924-6284-40c6-bcac-90c5b4296e3a)

## Data Sources
Finance Data: The primary dataset used for this analysis comes in an Excel file, containing 4 different tables of information made by the company. [Download here](https://mavenanalytics.io/data-Playground?order=date_added%2Cdesc&search=coff)

## Analysis Tools Used
- Microsoft Excel
- Power Query
- Power Pivot
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

![Screenshot 2024-11-30 021828](https://github.com/user-attachments/assets/540bcd33-3fdc-48a5-ba33-ed9123b8668a)
![Screenshot 2024-11-30 021649](https://github.com/user-attachments/assets/2a9148a2-fbc7-4b9f-96e6-c45ab3ce9640)
![Screenshot 2024-11-30 021624](https://github.com/user-attachments/assets/28766736-4707-4d85-a77f-c66b38b29ee2)
![Screenshot 2024-11-30 021602](https://github.com/user-attachments/assets/50196260-2cf2-4649-a542-6a8227095862)
![Screenshot 2024-11-30 021440](https://github.com/user-attachments/assets/21b02add-8190-405f-bc34-906ca29833c2)
![Screenshot 2024-11-30 021927](https://github.com/user-attachments/assets/ed14e657-2407-4793-9bac-a507f5f415eb)


## Data Analysis
Power Pivot was used for creating some measures using DAX Funcions. Some of the measures used for these analysis include:
``` Sql
Total orders = COUNT('Data Cleaning & transformation'[transaction_id])
```
``` Sql
Total Sales = SUM('Data Cleaning & transformation'[Total Bills])
```
``` Sql
Avg Order per person = DIVIDE([Total Qty],[Total orders],0)
```
``` Sql
Avg Sale per Person = DIVIDE([Total Sales],[Total orders],0)
```

## Findings
 The analysis results are summarized as follows:
1. Target were only met for 2 months out of the 14 months of the given period.
2. The Yummies Team met most of the targets.
3. 11 salesperson met their targets.

## Recommendations
Based on the analysis conducted, i recommend the following:
- There should be a Shift scheduling strategy of sales rep being targeted on fridays to ensure smooth and timely order processing and better customer experiences.
- To ensure a balanced customer to sales representative ratio, more sales reps should be placed between 8am and 9am daily on the selling floor.
- Promotions and Marketing campaigns should be targeted on Coffee Product category.
- Regular and Large Sizes should be priotized durin
