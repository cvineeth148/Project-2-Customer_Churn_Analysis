# Project-2-Customer_Churn_Analysis

### Dashboard Link : https://app.powerbi.com/groups/me/reports/c50ddd45-da42-4e57-a760-4fe77985481d/ReportSection?experience=power-bi

## Problem Statement

This dashboard helps the bank understand its customers better and identify key factors contributing to customer churn. It provides insights into customer behavior based on dimensions like balance, credit score, age, products held, and country. By using this dashboard, the bank can focus on high-risk customers who are more likely to leave due to factors such as low balances or unfavorable credit scores.

With the analysis showing that certain customer segments, based on age or country, are at higher risk of churn, the bank can work on targeted retention strategies. The dashboard also reveals that customers holding fewer products are more likely to churn, indicating an opportunity for cross-selling initiatives.

Since the analysis shows a considerable portion of customers at risk of leaving, the bank should prioritize improving its offerings and customer experience to reduce churn and boost customer satisfaction.



### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : Renaming the columns for better understanding and for future visualization.
- Step 6 : For credit card, Active member, Churn columns we have values as 1 and 0 so we are changing the value (change datatype to text before replacing) using replace value for readablility.(CC :Owned or Not Owned, AM:Active or Not Active etc..)
- Step 7 : By observing the product coloumn we can see it as just number values. So created a "column from example" option in add column tab.
- Step 8 : When we look the columns Credit score, Age and salary we can see there are lots of distinct columns so it won't be good in visuals and will be difficult to analyse. Creating a range for each of the column values using "conditional columns". 
- Step 9 : we have columns for balance and estimated salary we are removing estimated salary, as of now we are going with balance.
- Step 10 : creating three reference tables from the main table. Generated unique column IDs for each table to ensure data integrity and maintain relationships across tables.
- Step 11 : Open Model View and check all the realations are established. If no we need to connect all dimension table to fact table.
- Step 12 : Creating measure for base values (total customers, total customers lost and churn rate).
           
           Customers = count('Bank Customer Churn Details'[Customer ID])
  
           Customer Lost = calculate(count('Bank Customer Churn Details'[Churn]), 'Bank Customer Churn Details'[Churn]="Churned")

           Chun rate = 'Bank Customer Churn Details'[Customer Lost]/'Bank Customer Churn Details'[Customers]

              
- Step 13 : In the report view, under the view tab, theme was selected.
- Step 14 : Now starting to use the chart based on the requirement, Added Card to display total customers using measure.
- Step 15 : Added 5 donut charts based on Gender, Churn, Product, Creditcard, Activity.
- Step 16 : Added 3 Line and clustered column chart for representing Age, Customer and churn rate, then bank balance, then credit score range.
- Step 17 : A guage chat was also added to get the analysis compared to the target churn rate. 
- Step 17 : Visual filters (Slicers) were added for two fields named Churned and Not Churned

- Step 18 : New measure was created to find total count of customers.

        
A card visual was used to represent count of customers.

![Screenshot 2024-10-24 125851](https://github.com/user-attachments/assets/9215fcda-bc0f-4e5d-b8dd-69bf2c7c0f19)

 
 - Step 19 : The report was then published to Power BI Service.
 
 
![Screenshot 2024-10-23 124749](https://github.com/user-attachments/assets/c505d29a-5a2e-4cef-a200-8b165a4d679e)


# Snapshot of Dashboard (Power BI Service)

![Screenshot 2024-10-24 130202](https://github.com/user-attachments/assets/e31ebe7d-d357-4843-b596-598cfa161a9b)

 
 # Report Snapshot (Power BI DESKTOP)

 
![Screenshot 2024-10-24 130244](https://github.com/user-attachments/assets/3720aa08-8a86-4584-97b3-02e858e5044b)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Customers = 10K

   Number of Churned Customers (Male) = 898 (44.08 %)

   Number of Churned Customers (Female) = 1139 (55.92 %)

   Number of Not Churned Customers (Male) = 4559 (57.25.58 %)

   Number of Not Churned Customers (Female) = 3404 (42.75 %)


           thus, higher number of customers Churned are Females difference is almost 10% of men.
           

 ### [2] Insights
 
 
 1.1) 51.21 % of customers with age ranges from 51 - 60 years have churned
 
 1.2) 100% of customers with a credit score below 400 have churned.
 
 1.3) 100 % of customers having balance ranges from 1k - 10k have churned
 
 
 ### Product Group
 
 2.1)  100 % customers have churned who use prod 4.
 
 2.2)  82.7 % customers have churned in prod 3.
 
 2.3)  27.7 % Churn rate for prod 1.
 
 2.4)  7.6 % Churn rate for prod 2.
 
         thus, Products 4 and 3 need to be analyzed as they have the highest churn rate.
         Product 2 is doing great.


### Country and churn rates

3.1) 16.2 % France.

3.2) 16.7 % Spain.

3.3) 32.4 % Germany.


        thus, more customers churn is happening in Germany. Others are close to the target.
        
