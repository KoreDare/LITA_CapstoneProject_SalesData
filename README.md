# LITA_CapstoneProject_SalesData

### Project Objective
This project aims to analyze the sales performance of a retail store by exploring available data to ascertain top-selling products, regional performance, and monthly sales trends. This will, in turn, inform our decision about which products to improve upon and the ones to cut down on. 

### Data Sources
The primary data source used here is SalesData from the LITA Capstone Project. [Sales Data.xlsx](https://github.com/user-attachments/files/17636823/Sales.Data.xlsx)
The dataset contains sales information for clothes and accessories sold by a retail store spread out over different regions. We will use Excel, SQL, and Power BI to determine trends and patterns.

### Data Tools
- Microsoft Excel for Data Cleaning, Analysis, and Visualization
- Structured Query Language (SQL) for Querying of Data
- GitHub for Portfolio Building
- Microsoft Power BI for Data Summarization and Visualization

### Data Analysis using Excel PivotTables and Dashboard
Using the PivotTables in Excel, I retrieved the parameters itemized below:
- Total Sales by Product
- Total Sales by Region
- Total Sales by Month
- Total Sales by Region according to Product Category
- Percentage Sales by Region
- Percentage Sales by Product

I gathered that the highest-selling product by sales value was Shoes, while the Southern Region brought in a greater part of the sales for the store. I also noticed the month with the highest sales made was February. 

<img width="907" alt="Sales Data PivotTables" src="https://github.com/user-attachments/assets/e560c498-c34e-4c81-adb0-a39646e51c53">

<img width="529" alt="Sales Data Dashboard" src="https://github.com/user-attachments/assets/1dc7f76e-91cc-4698-8784-5a45688e7dc5">

### Data Analysis using SQL
I imported the dataset which I had saved as a .csv file from Excel after creating the database in the SQL interface. After cleaning the data, I used the following queries to extract the various information as detailed below:

- Total Sales for each Product Category

> ```SQL
> select Product, sum(Total_Sales) as TotalSales
> from [dbo].[Sales_Data_Capstone_Project]
> Group by Product
> ```

- Number of Sales Transactions in each Region

> ```SQL
> select Region, count(Total_Sales) as SalesTransaction
> from [dbo].[Sales_Data_Capstone_Project]
> Group by Region
> ```

- Highest-Selling Product by Total Sales Value

> ```SQL
> select top 1 Product, sum(Total_Sales) as TotalSales
> from [dbo].[Sales_Data_Capstone_Project]
> Group by Product
> Order by 2 desc
> ```

- Total Revenue per Product

> ```SQL
> select Product, sum(Quantity * UnitPrice) as TotalRevenue
> from [dbo].[Sales_Data_Capstone_Project]
> Group by Product
> ```

- Monthly Sales Totals for the Current Year

> ```SQL
> select datename(month, OrderDate) as Month, sum(Total_Sales) AS SalesTotal
> from [dbo].[Sales_Data_Capstone_Project]
> where year(OrderDate) = year(GETDATE())
> Group by datename(month, OrderDate), datepart(month, OrderDate)
> order by datepart(month, OrderDate)
> ```

- Top 5 Customers by Total Purchase Amount

> ```SQL
> select Top 5 Customer_Id, sum(Quantity * UnitPrice) AS TotalPurchaseAmount
> from [dbo].[Sales_Data_Capstone_Project]
> Group by Customer_Id
> Order by 2 desc
> ```

- Percentage of Total Sales by Region

> ```SQL
> select Region, sum(Total_Sales) as RegionSales,
> sum(Total_Sales) * 100.0 / (select sum(total_sales) from [dbo].[Sales_Data_Capstone_Project]) as PercentageSales
> from [dbo].[Sales_Data_Capstone_Project]
> group by Region
> order by PercentageSales desc
> ```

- Products with No Sales in the Last Quarter

> ```SQL
> select Product from [dbo].[Sales_Data_Capstone_Project]
> group by Product
> having max(OrderDate) < DATEADD(Quarter, -1, GetDate())
> ```

### Data Analysis using Power BI


