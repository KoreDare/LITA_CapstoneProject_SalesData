# LITA_CapstoneProject_SalesData

### Project Objective
This project aims to analyze the sales performance of a retail store by exploring available data to ascertain top-selling products, regional performance, and monthly sales trends. This will, in turn, inform our decision about which products to improve upon and the ones to cut down on. 

### Data Sources
The primary data source used here is SalesData.csv from the LITA Capstone Project. [Sales Data.xlsx](https://github.com/user-attachments/files/17636823/Sales.Data.xlsx)
The dataset contains sales information for clothes and accessories sold by a retail store spread out over different regions. We will use Excel, SQL, and Power BI to determine trends and patterns.

### Data Tools
- Microsoft Excel for Data Cleaning, Analysis, and Visualization
- Structured Query Language (SQL) for Querying of Data
- GitHub for Portfolio Building
- Microsoft Power BI for Data Summarization and Visualization

### Data Analysis
I imported the dataset as a .csv file from Excel after creating the database in the SQL interface. After cleaning the data, I used the following queries to extract the various information as detailed below:

> Total Sales for each Product Category
> 
>
>  ```select Product, sum(Total_Sales) as TotalSales
> from [dbo].[Sales_Data_Capstone_Project]
> Group by Product

<img width="907" alt="Sales Data PivotTables" src="https://github.com/user-attachments/assets/e560c498-c34e-4c81-adb0-a39646e51c53">

<img width="529" alt="Sales Data Dashboard" src="https://github.com/user-attachments/assets/1dc7f76e-91cc-4698-8784-5a45688e7dc5">
