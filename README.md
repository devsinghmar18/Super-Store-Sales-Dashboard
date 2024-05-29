
# Super Store Sales-Dashboard


## Problem Statement

This dashboard helps the company to understand their customers better in USA. It helps to know the total sales and profit of different types of products in different regions of the country.

Forecasting done after January 2021 for 15 days.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.

- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.

- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".

- Step 4 : It was observed that in none of the columns errors & empty values were present through column quality under Data preview section.

- Step 5 : In column "Returns" #N/A is replaced to 0 value.)

- Step 6 :Two empty columns "ind1" and "ind2" are removed.

- Step 7 : 2 Clustered Bar chart is used to show "Sales by Category" vs "Sum of sales and "Sales by Ship Mode" vs "Sum of Sales and filtered it for top 3 values".

- Step 8 : "Sales by Sub - Category" vs "Sum of Sales" is also shown through clustered Bar chart.

- Step 9 : Two Stacked area chart are used to show the 2019 and 2020 year for "Sum of Profit" vs "Months" and  "Sum of Sales" vs "Months".

- Step 10 : Map visual is used  for "Sum of Sales" and "Sum of Profit" with bubble size for different states in USA.

Snap of map,
![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/35359c1d-73ad-4b3d-9601-c605a0e11280)
           
- Step 11 : Four card visuals were added to the canvas, showing Total profit, Sales, Avg. delivery Time and Quantity.

- Step 12 : Average Delivery Time is calculated through order date to ship date difference.
For creating new column AvgDelivery following DAX expression was written;

    AvgDelivery = DATEDIFF('SuperStore_Sales_Dataset'[Order Date] ,'SuperStore_Sales_Dataset'[Ship Date], DAY)

Snap of new calculated column,
![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/1fd91c12-269c-4d28-9b84-b28c9d7a52d1)


- Step 13 : Two Donut chart visual are also added for "Sum of Sales by Payment Mode" vs "Total Sales" and "Sum of Sales by Segment" vs "Total Sales".

- Step 14 : A horizontal slicer is added to show different regions of USA. 

- Step 15 : A long clustered Bar Chart visual is added to show State wise Total Sales on second page.

 - Step 16 : Total Sales for a single date is done by creating a new table for Date column and Total sales (By combining sales of that particular date).

For creating new table following DAX query is used;
    
    SalesForecast = SUMMARIZE('SuperStore_Sales_Dataset','SuperStore_Sales_Dataset'[Order Date],"TOTAL SALES",SUM(SuperStore_Sales_Dataset[Sales]))

Snap for new calculated table,
![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/be37905b-a64b-46f7-aa61-3a28852c8f8e)


- Step 17 : Now Sales Forecast for 15 days is done through Line chart visual using "Total Sales" vs "Date"(this is for each day) starting from Jan 2019 to Jan 2021 and forecasting it after Jan with a confidence interval of 95%.
        
 - Step 18 : A second line chart visual is made by zooming it through zoom slider and forecasting is done similar to above case.
 

 
 - Step 19 : The report was then published to Power BI Service.
 
 
![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/2075434e-9771-4001-be25-61d9af3ca861)

# Snapshot of Dashboard (Power BI Service)

![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/89bd02c1-0aeb-4bce-ad4f-2a4db08b3a94)

 
 # Report Snapshot (Power BI DESKTOP) of First page

 
![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/82ff1033-95a1-4523-ae3d-078ecdc24563)

 # Report Snapshot (Power BI DESKTOP) of Second page

 ![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/ba3d0e53-2042-4e5b-9055-e4a697afde21)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Sales = 1.6M

    Total sales in Central region = 341K

    Total sales in East region = 450.2K

    Total sales in South region = 252.1K

    Total sales in West region = 522.4K

Maximum sales can be clearly seen in West region


### [2] Total Profit = 175.3K

    Total sales in Central region = 27.5K

    Total sales in East region = 53.4K
 
    Total sales in South region = 26.6K

    Total sales in West region = 67.9K 

Maximum profit can be seen in West region as sales of products are also more in that region.

One more insight is that average time to deliver products is 4 days which is same for all regions.


  ### [3] Sales By Category
  
    Total office supplies products sales = 0.64M

    Total technology products sales = 0.47M

    Total furniture products sales = 0.45M

Common insight is that for all regions of USA sequence of products sales didn't changed.


 ### [4] Type of payment mode
 
    Through cards = 22%

    Through cash on delivery = 43%

    Through online mode = 35%

It means people believe in cash on delivery more as they don't  trust online or card payment much.


### [5] Segment wise sales

    Consumer sales = 48%

    Home office sales = 19%

    Corporate sales = 33%

People are buying more products for their personal use.

### [6] State wise sales

    California = 0.34M

    New York = 0.19M

    Texas = 0.12M

As California has the maximum sales but New York has a very high profit despite low sales than California.


### [7] Sales Forecast for 15 days

#### After 31 December-> 

![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/de418b0d-51e0-4954-805c-ddfadee6e49b)

![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/a65b028d-9e97-4501-9692-acca4591c7cd)

![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/519a75e8-407a-4086-a86c-1383ad2469e5)

![image](https://github.com/devsinghmar18/Super-Store-Sales-Dashboard/assets/105980995/1dd3881e-e0ee-4f62-925c-e6af661ee229)


These are for a confidence interval of 95%.

