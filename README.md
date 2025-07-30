# Banking Dashboard

This project focuses on developing a basic understanding of risk analytics in banking and financial services, demonstrating how data can be used to minimize the risk of financial loss when lending to customers.

## Problem Statement

The core problem addressed is to understand risk analytics in banking and financial services and to leverage data to mitigate the risk of losing money when providing loans to customers.

## Solution

Our solution involves creating interactive dashboards using Power BI. These dashboards enable informed decision-making based on an applicant's profile, helping to determine if they are likely to repay a loan, and thus assisting in loan approval decisions.

## About the Dataset

The dataset used in this project contains comprehensive information about bank details and various client details. It consists of multiple tables interlinked through primary and foreign keys. The key tables include:
1. Banking Relationship
2. Client-Banking
3. Gender
4. Investment Advisor
5. Period
6. Data Cleaning and Transformation

### Several data cleaning and transformation steps were performed to prepare the data for analysis:
Engagement Timeframe: A new column, Engagement Timeframe, was created in the Client-Banking table to represent the tenure of clients with the bank.
Engagement Days: A new column, Engagement Days, was created in the Client-Banking table to calculate the number of days a client has been with the bank from their joining date.

### Income Band: The Estimated Income column was binned into Income Band categories:
< 100000 as "Low"
< 300000 as "Mid"

### Processing Fees: A new column, Processing Fees, was created based on the Fee Structure. If the fee structure is "high," the processing fee is set to 0.05.

## Calculated Functions (DAX)
The following DAX functions were utilized to create various measures:
1. SUM: Aggregates all numbers in a specified column.
2. Bank Deposit = SUM('Clients - Banking'[Bank Deposits])
3. DISTINCTCOUNT: Counts the number of distinct values in a column.
4. Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])
5. SUMX: Returns the sum of an expression evaluated for each row in a table.
6. Total Fees = SUMX('Clients - Banking' , [Total Loan] * 'Clients - Banking'[Processing Fees] )
7. SWITCH: Evaluates an expression against a list of values and returns one of multiple possible result expressions.
8. SWITCH(<expression>, <value>, <result>[, <value>, <result>]...[, <else>])
9. DATEDIFF: Returns the number of interval boundaries between two dates.
10. Engagment Days = DATEDIFF('Clients - Banking'[Joined Bank],TODAY(), DAY )

## Key Performance Indicators (KPIs)

The following KPIs are present in the dashboards to provide key insights:
1. Total Clients: Represents the total number of clients in banking.
2. Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])
3. Total Loan: Provides information about the combined bank loan, business lending, and credit card balance for a particular investor/gender.
4. Total Loan = [Bank Loan] + [Business Lending] + [Credit Cards Balance]
5. Bank Loan: The total loan amount to be repaid by the client to the bank.
6. Bank Loan = SUM('Clients - Banking'[Bank Loans])
7. Business Lending: The loan amount given to small businesses.
8. Business Lending = SUM('Clients - Banking'[Business Lending])
9. Total Deposit: Information about the total amount deposited by particular investors in the bank.
10. Total Deposit = [Bank Deposit] + [Savings Account] + [Foreign Currency Account] + [Checking Accounts]
11. Total Fees: The amount charged by the bank for account setup, maintenance, etc.
12. Total Fees = SUMX('Clients - Banking' , [Total Loan] * 'Clients - Banking'[Processing Fees])
13. Bank Deposit: Money deposited in the bank.
14. Bank Deposit = SUM('Clients - Banking'[Bank Deposits])
15. Checking Account Amount: Offers easy access to money for daily transactional needs.
16. Checking Accounts = SUM('Clients - Banking'[Checking Accounts])
17. Total CC Amount: Short-term financing for a company by a bank.
18. Total CC Amount = SUM('Clients - Banking'[Amount of Credit Cards])
19. Saving Account Amount: An interest-bearing deposit account held at a bank.
20. Savings Account = SUM('Clients - Banking'[Saving Accounts])
21. Foreign Currency Amount: An account held in a currency other than the currency of India, Bhutan, or Nepal.
22. Foreign Currency Account = SUM('Clients - Banking'[Foreign Currency Account])
23. Engagement Account: Focuses on delivering digital experiences to customers.
24. Engagment Length = SUM('Clients - Banking'[Engagment Days])
25. Credit Cards Balance: The total amount of money currently owed by a cardholder to their credit card bank.
26. Credit Cards Balance = SUM('Clients - Banking'[Credit Card Balance])

## Visualizations and Results

The project includes several dashboards for comprehensive analysis:
1. Home Dashboard
2. Loan Analysis Dashboard
3. Deposit Analysis Dashboard
4. Summary Dashboard

## Key Observations
1. Bank Loan by Income Band: Bank loans are highest for the Mid Income band and lowest for the High Income band.
2. Bank Loan by Nationality: Bank loans are highest for European countries and lowest for Australian countries.

## Conclusion

Empowered by the latest data visualization techniques, Power BI dashboards are highly effective resources for the banking sector. As demonstrated in this project, a banking operations dashboard in Power BI can be developed with key banking-related metrics and KPIs to provide valuable insights.

## Future Work
These dashboards can be further leveraged to:
1. Easily determine the total loan amount and other financial details of a particular investor.
2. Identify which types of banks have more clients (e.g., private banks showing a higher client count), enabling other banks to strategize for client growth.
3. Provide insights into which nationality has the highest bank loans.
4. Offer information about various amounts involved in different types of accounts by investors.
