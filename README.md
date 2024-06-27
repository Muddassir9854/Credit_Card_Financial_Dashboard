
## Introduction:- 
In this project, I developed a comprehensive Credit Card Transaction Dashboard using SQL and Power BI to analyze and visualize credit card transactions and customer data. The project involved several key stages, including data importation, database connection setup, data understanding and analysis using DAX queries, and dashboard creation with various Key Performance Indicators (KPIs) and visualizations.


## Project Objective :- 
To develop a comprehensive credit card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.

- **Data Integration and Management**: Seamlessly integrate transaction and customer data into a unified platform for efficient analysis.

- **Dynamic Data Analysis**: Utilize DAX queries to perform dynamic calculations and gain deeper insights into customer behavior and transaction trends.

- **Visualization and Reporting**: Develop an interactive dashboard that provides stakeholders with clear and actionable insights through various KPIs and visualizations.

- **Performance Monitoring**: Track key financial metrics and customer-related statistics to monitor business performance and identify growth opportunities.

- **Customer Segmentation**: Segment customers based on demographics and behavior to tailor marketing strategies and improve customer engagement.


## What I did in This Project :-

- **Data Importation**: Imported transaction and customer datasets into a SQL database.
Ensured data integrity and accuracy during the import process.

- **Database Connection Setup**: Established a live connection between Power BI and the SQL database.
Configured automatic data refresh to keep the dashboard up-to-date with the latest data.

- **Data Analysis with DAX**: Wrote DAX queries to segment customers into age and income groups.
Calculated key metrics such as current week revenue, previous week revenue, and week-over-week (WoW) growth.
Derived additional insights like transaction counts and average customer income.

 Some DAX expression was written like;
 
>>1. **Age Group** 
 
       
    AgeGroup = SWITCH(
    TRUE(),
    'ccdb cust_detail'[Customer_Age]<30, "20-30",
    'ccdb cust_detail'[Customer_Age]>= 30 && 'ccdb cust_detail'[Customer_Age] < 40, "30-40",
    'ccdb cust_detail'[Customer_Age]>= 40 && 'ccdb cust_detail'[Customer_Age] < 50, "40-50",
    'ccdb cust_detail'[Customer_Age]>= 50 && 'ccdb cust_detail'[Customer_Age] < 60, "50-60",
    'ccdb cust_detail'[Customer_Age]>= 60 ,"60+",
    "UNKNOWN"
    )

>>2. **Income Group** 
 
       
    IncomeGroup = SWITCH(
    TRUE(),
    'ccdb cust_detail'[Income] < 35000, "Low",
    'ccdb cust_detail'[Income] >= 35000 && 'ccdb cust_detail'[Income] < 70000, "Mid",
    'ccdb cust_detail'[Income] >= 70000, "High",
    "Unknown"
    )

>>3. **Current Week Revenue** 
 
       
    Cur_week_Rev = CALCULATE(
    SUM('ccdb credit_card_details'[Revenue]),
    FILTER(
        ALL('ccdb credit_card_details'),
        'ccdb credit_card_details'[Week_Num2] = MAX('ccdb credit_card_details'[Week_Num2])))
    
>>4. **Previous Week Revenue** 
 
    Previous_week_Rev = CALCULATE(
    SUM('ccdb credit_card_details'[Revenue]),
    FILTER(
        ALL('ccdb credit_card_details'),
        'ccdb credit_card_details'[Week_Num2] = MAX('ccdb credit_card_details'[Week_Num2])-1))

>>5. **WoW Growth** 
 
     WoW_Revenue_Change = DIVIDE(([Cur_week_Rev] - [Previous_week_Rev]),[Previous_week_Rev])

- **Dashboard Creation**: Created a user-friendly and interactive dashboard in Power BI.
Incorporated KPIs such as total revenue, transaction amount, interest earned, count of transactions, average customer income, customer satisfaction score, and customer acquisition cost.

**Designed various charts to visualize data insights, including**:
| KPIs                                 | Description                                                    |
|--------------------------------------|----------------------------------------------------------------|
| **Total transactions**               | Track the total transactions occured through credit cards.     |
| **Total Revenue**                    | Total Revenue generated by transactions.                       |
| **Total Interest Earned**            | How much interest earned by credit cards.                      |
| **WoW Growth**                       | Understand WoW growth through **Line Chart** and identify the trends, usage of credit cards on each week. |
| **Revenue by Education level**       | Identify the usage of Credit Cards by customers on which Education level and generating Revenue.       |
| **Revenue by Age Group**             | Understand which age groups of customers using mostly credit cards.       |
| **Revenue by Expenses Type**         | Identify where Customers uses the Credit Cards.                |
| **Revenue by Customer Job**          | Which Occupied customers using credit cards mostly .           |


## Dashboard🔲 :- 

- **Credit Card Transaction Dashboard**
  
![Credit Card Transaction (1)](https://github.com/mohd-muddassir99/Credit_Card_Financial_Dashboard/assets/153819384/9e7e4f45-c201-4476-afdb-64321bad0b4d)

- **Credit Card Customer Analysis Dashboard**


![CreditCardCustomer](https://github.com/mohd-muddassir99/Credit_Card_Financial_Dashboard/assets/153819384/992121c2-9ee8-423a-96e5-b9abb51c6722)



## Project Insights🥇 :-

- **Revenue Trends**: Identified revenue patterns across different customer demographics and transaction types, helping to pinpoint high-value customer segments.
- **Customer Behavior**: Analyzed customer spending habits, preferences for certain transaction methods (e.g., chip usage), and the impact of educational and occupational backgrounds on spending.
- **Growth Analysis**: Evaluated week-over-week revenue growth to measure business performance and identify periods of significant revenue changes.
- **Customer Satisfaction and Acquisition**: Monitored customer satisfaction scores and acquisition costs to ensure efficient resource allocation and enhance customer experience.
  **Some more insights**:
  
| S.no                                 | Insights                                                       |
|--------------------------------------|----------------------------------------------------------------|
| **1.**                               | **Revenue increased by 28.8%.**                                |
| **2.**                               | **Customer count increased by 11.5%.**                         |
| **3.**                               | **Overall Revenue is 55M.**                                    |
| **4.**                               | **Our Average Customer aquisition cost is 97.**                |
| **5.**                               | **Total Interest earned is 8M.**                               |
| **6.**                               | **Male customers are contributing more in revenue 30M, female 25M.**                               |
| **7.**                               | **Blue & Silver credit card are contributing to 93% of overall transactions.**                     |
| **8.**                               | **Three States TX, NY & CA is contributing to 68%.**                                               |
| **9.**                               | **Overall Activation rate (How much customers activate our card in just a month)is 57.5%.**        |
| **10.**                              | **Overall Delinquent rate (Who is not paying their dept.) is 6.06%.**                 |


View the **Credit Card Transaction Dashboard** here:

<p align="center">
    <a href="https://github.com/mohd-muddassir99/Credit_Card_Financial_Dashboard/blob/main/Credit%20card%20transaction.pdf">
        <img src="https://static.vecteezy.com/system/resources/previews/010/750/673/non_2x/pdf-icon-on-white-background-file-pdf-icon-sign-pdf-format-symbol-flat-style-free-vector.jpg" width="65px" alt="Access Dataset"><br>
        Credit Card Transaction
    </a>
</p> <br>

View the **Credit Card Customer Analysis Dashboard** here:

<p align="center">
    <a href="https://github.com/mohd-muddassir99/Credit_Card_Financial_Dashboard/blob/main/Credit%20card%20customer.pdf">
        <img src="https://static.vecteezy.com/system/resources/previews/010/750/673/non_2x/pdf-icon-on-white-background-file-pdf-icon-sign-pdf-format-symbol-flat-style-free-vector.jpg" width="65px" alt="Access Dataset"><br>
        Credit Card Customer Analysis
    </a>
</p> <br>

## Software and Tools used:-

<table>
    <tr>
        <!-- Specify width for each cell to ensure equal column width -->
        <td align="center" width="33%"><img alt="Power BI" width="35px" src="https://upload.wikimedia.org/wikipedia/commons/c/cf/New_Power_BI_Logo.svg"/><br>Microsoft Power BI</td>
        <td align="center" width="33%"><img alt="Excel" width="35px" src="https://cdn.worldvectorlogo.com/logos/excel-4.svg"/><br>Microsoft Excel</td>
        <td align="center" width="33%"><img alt="DAX" width="50px" src="https://learn.microsoft.com/en-us/training/achievements/use-dax-power-bi-desktop.svg"/><br>DAX</td>
        <td align="center" width="33%"><img alt="My SQl" width="78px" src="https://1000logos.net/wp-content/uploads/2020/08/MySQL-Logo.png"/><br>My SQL</td>
    </tr>
</table>


---

<div align="center">
Thanks for checking out my Credit Card Transaction Dashboard project! Your interest means a lot. Feel free to reach out if you have any questions or feedback. Happy analyzing! 😊<br>
 🔗 Connect with me on LinkedIn 
 
  <p align="center">
    <a href="https://www.linkedin.com/in/mohd-muddassir99/">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/640px-LinkedIn_logo_initials.png" width="65px" alt="Access Dataset"><br>
        LinkedIn
    </a>

   | **Mohd Muddassir** | </a> <br>
Don't forget to follow and star ⭐ the repository if you find it valuable.
</div>






