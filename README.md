# Bank Loan Analysis Project (SQL + Tableau)

## 📘 Overview
This project analyzes and visualizes **bank loan data** using **SQL** for backend data processing and **Tableau** for interactive dashboarding.  
The goal is to evaluate the overall performance of the bank’s lending portfolio, monitor key metrics, and identify trends to support **data-driven decision-making**.

---

## 🎯 Objective
To design a comprehensive **Bank Loan Summary Dashboard** that provides actionable insights into:
- Loan application trends  
- Disbursement performance  
- Repayment consistency  
- Borrower characteristics  
- Risk segmentation (Good vs. Bad Loans)

---

## 🧩 Tools & Technologies
- **Database:** MySQL  
- **Visualization:** Tableau  
- **Dataset:** Bank loan data (containing fields like loan amount, term, issue date, loan status, purpose, employment length, etc.)

---

## 📊 Key Metrics (KPIs)
The following KPIs were calculated using SQL and visualized in Tableau:

| **KPI** | **Description** |
|----------|----------------|
| **Total Loan Applications** | Number of loan applications received |
| **Total Funded Amount** | Total approved and disbursed loan amount |
| **Total Amount Received** | Total repayments collected from borrowers |
| **Average Interest Rate** | Mean interest rate across all active loans |
| **Average Debt-to-Income (DTI)** | Borrowers’ average DTI ratio for financial health analysis |
| **Good vs. Bad Loans** | Classification based on loan status: *Fully Paid / Current = Good*, *Charged Off = Bad* |

---

## 🧮 SQL Analysis
All insights were derived from SQL queries built on the **bank_loan_data** table.

### **Key SQL Operations**
- **Aggregation Queries:** `SUM()`, `AVG()`, `COUNT()`  
- **Filtering by Month/Term:** Using `MONTH(issue_date)` and conditions  
- **Categorization:** `CASE` statements to define Good and Bad loans  
- **Trend Analysis:** Monthly grouping using `GROUP BY DATENAME(MONTH, issue_date)`

---

### **Example Query**
```sql
SELECT 
    MONTH(issue_date) AS Month_Number, 
    DATENAME(MONTH, issue_date) AS Month_Name, 
    COUNT(id) AS Total_Loan_Applications,
    SUM(loan_amount) AS Total_Funded_Amount,
    SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY MONTH(issue_date), DATENAME(MONTH, issue_date)
ORDER BY MONTH(issue_date);

📈 Tableau Dashboard Overview

1. Bank Loan Summary
   - Displays Total Applications, Funded Amount, Amount Received, Average Interest Rate, and Average DTI.
   - Includes Month-to-Date (MTD) and Month-over-Month (MoM) performance indicators.

2. Good Loan vs. Bad Loan Analysis
   - Donut charts showing loan quality segmentation.
   - KPIs for both Good and Bad categories:
       • Applications count
       • Funded amount
       • Amount received

3. Loan Applications by Month
   - Line chart displaying monthly trends in loan applications.

4. Loan Term Distribution
   - Donut chart comparing short-term (36 months) and long-term (60 months) loans.

5. Applications by Employment Length
   - Bar chart analyzing borrower stability based on years of employment.

6. Applications by Loan Purpose
   - Categorized bar chart showing why loans were taken (e.g., debt consolidation, credit card, home improvement, etc.).

7. Home Ownership Analysis
   - Treemap visualizing loan distribution across ownership statuses: Own, Rent, Mortgage, etc.

⚙️ Filters Used
Interactive filters applied in Tableau:
• Purpose  
• Grade  
• Verification Status  
Users can modify these filters to view segmented insights (e.g., Grade A loans only).


📚 Conclusion
This project demonstrates how SQL and Tableau can be combined to build a complete data analysis and visualization pipeline for financial institutions.
The dashboard empowers banks to:
• Monitor portfolio performance  
• Detect risk patterns early  
• Improve lending strategies  
• Enhance financial decision-making



🧑‍💻 Author
Gouri Mathur
Data Analyst | SQL & Tableau Enthusiast
