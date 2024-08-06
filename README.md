# **Comprehensive Sales Insights Analysis with Power BI**

<!-- ## Project Overview

Welcome to the **Comprehensive Sales Insights Analysis** project! This project is designed to give you a comprehensive feel of how data analysis projects are executed in large companies using Power BI. It’s ideal for anyone looking to advance their career as a data analyst or data scientist. --> 

### Project Overview

Welcome to the **Comprehensive Sales Insights Analysis** project! In this case study, we focus on AtliQ Hardware, a company specializing in computer hardware and peripherals. The company is struggling to keep up with a dynamically changing market and faces significant challenges in tracking and analyzing sales data effectively. To address these challenges, the Sales Director, Dhaval Patel, has decided to invest in a data analysis project. The goal is to build a Power BI dashboard that provides real-time sales insights and facilitates data-driven decision-making.

---

## Project Breakdown

1. **Problem Statement**  
   Understand the sales challenges AtliQ Hardware is facing and define the project goals.

2. **Data Discovery & Cleaning**  
   Import and clean data using MySQL to ensure accuracy and readiness for analysis.

3. **ETL Process**  
   Transform and prepare the data using Power BI for effective analysis and visualization.

4. **Dashboard Creation**  
   Develop an interactive Power BI dashboard that visualizes key metrics such as revenue trends, regional performance, and product sales.

5. **Stakeholder Feedback**  
   Act as a stakeholder to provide feedback on the dashboard for iterative improvements.

6. **Project Wrap-Up**  
   Summarize findings and discuss next steps, including enhancements based on stakeholder feedback.

---

## Setup Instructions

### MySQL Setup

1. Follow the steps in this video to install MySQL on your local computer: [MySQL Installation Video](https://www.youtube.com/watch?v=WuBcTJnIuzo).
2. Download the `db_dump.sql` file and import it into your MySQL database as per the video tutorial.

### Data Analysis Using SQL

Run the following SQL queries to analyze the data:

1. **Show all customer records**  
   ```sql
   SELECT * FROM customers;
   ```

2. **Show total number of customers**  
   ```sql
   SELECT count(*) FROM customers;
   ```

3. **Show transactions for Chennai market**  
   ```sql
   SELECT * FROM transactions WHERE market_code='Mark001';
   ```

4. **Show distinct product codes sold in Chennai**  
   ```sql
   SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';
   ```

5. **Show transactions where currency is US dollars**  
   ```sql
   SELECT * FROM transactions WHERE currency="USD";
   ```

6. **Show transactions in 2020 joined by date table**  
   ```sql
   SELECT transactions.*, date.* FROM transactions
   INNER JOIN date ON transactions.order_date = date.date
   WHERE date.year = 2020;
   ```

7. **Show total revenue in 2020**  
   ```sql
   SELECT SUM(transactions.sales_amount) FROM transactions
   INNER JOIN date ON transactions.order_date = date.date
   WHERE date.year = 2020 AND (transactions.currency = "INR" OR transactions.currency = "USD");
   ```

8. **Show total revenue in January 2020**  
   ```sql
   SELECT SUM(transactions.sales_amount) FROM transactions
   INNER JOIN date ON transactions.order_date = date.date
   WHERE date.year = 2020 AND date.month_name = "January"
   AND (transactions.currency = "INR" OR transactions.currency = "USD");
   ```

9. **Show total revenue in Chennai for 2020**  
   ```sql
   SELECT SUM(transactions.sales_amount) FROM transactions
   INNER JOIN date ON transactions.order_date = date.date
   WHERE date.year = 2020 AND transactions.market_code = "Mark001";
   ```

### Data Analysis Using Power BI

1. **Formula to create `norm_amount` column**  
   ```powerbi
   = Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)
   ```

2. **Interactive Dashboard**  
   Explore the interactive dashboard here: [Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiMGNhNjAwZWMtZjhmOS00N2FiLTgwYjMtZGMxMDAxODRmMzZkIiwidCI6IjhkMWE2OWVjLTAzYjUtNDM0NS1hZTIxLWRhZDExMmY1ZmI0ZiIsImMiOjN9&embedImagePlaceholder=true) (Click on view interactive content for better experience.)

---

### Insights Gained:

- **Profitability vs. Revenue:** Markets with high revenue are not always the most profitable. For instance, while Delhi had high revenue, Mumbai offered significantly higher profit margins. This highlights the importance of focusing on both revenue and margin to optimize sales strategies.

- **Customer Analysis:** Detailed analysis at the customer level revealed that even customers with low profit margins could contribute significantly to overall profit due to high order volumes. Conversely, some customers could be unprofitable despite high revenue, prompting a review of customer management strategies.

- **Dynamic Performance Metrics:** By setting dynamic performance targets, such as profit margin thresholds, businesses can quickly identify underperforming regions or products, allowing for targeted interventions to address these issues effectively.

## Conclusion

This project demonstrated the power of using advanced analytics and DAX formulas in Power BI to gain actionable insights from sales data. Key insights included identifying high-margin markets versus high-revenue markets, understanding customer profitability, and dynamically assessing performance against targets. By leveraging these techniques, businesses can make data-driven decisions to optimize sales strategies and improve overall profitability.

---

## Credits

- **Dhaval Patel**: Special thanks to Dhaval Patel for his amazing youtube playlist on [*Power Bi*](https://www.youtube.com/playlist?list=PLeo1K3hjS3uva8pk1FI3iK9kCOKQdz1I9).

---

## Contact

For any questions or feedback regarding this project, feel free to contact me at dhruvmojila098@gmail.com.

---

Dive into the project and experience how data analysis projects are executed in a corporate environment. Enjoy your analytical journey! 🚀
