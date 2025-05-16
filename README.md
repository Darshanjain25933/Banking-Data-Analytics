# 💼 Banking Dashboard - Risk Analytics in Financial Services

## 📌 Problem Statement
Develop a basic understanding of **risk analytics** in the banking and financial services sector. The goal is to analyze customer data to **minimize the risk of loan defaults**, enabling better lending decisions.

---

## ✅ Solution Overview
Using **Power BI** and its latest features, we created interactive dashboards to help banks assess an applicant’s financial profile. Based on the applicant's data, the system can assist in determining whether to **approve or reject loan applications**, improving risk mitigation and decision-making.

---

## 📂 About the Dataset
The dataset includes multiple interlinked tables with **bank and client-related information**:
- `Banking Relationship`
- `Client-Banking`
- `Gender`
- `Investment Advisor`
- `Period`

These tables are related using **primary and foreign keys**.

---

## 🧹 Data Cleaning & Transformation
Performed multiple data transformations to enhance analysis:
- Created a new column `Engagement Timeframe` to analyze client tenure.
- Added `Engagement Days` to calculate how many days a client stayed in the bank using `DATEDIFF`.
- Binned `Estimated Income` into `Income Band`:
  - Low: `< 100,000`
  - Mid: `< 300,000`
- Created a new column `Processing Fees`:
  - If `Fee Structure = High`, then `Processing Fee = 0.05`.

---

## 📊 Calculated Functions Used

### 🧮 Aggregates:
- `SUM`: Adds all numbers in a column  
  `Bank Deposit = SUM('Clients - Banking'[Bank Deposits])`
- `DISTINCTCOUNT`: Counts unique values  
  `Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])`
- `SUMX`: Evaluates and sums expressions  
  `Total Fees = SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])`

### 🔁 Logical Functions:
- `SWITCH`: Returns values based on conditions
- `DATEDIFF`: Calculates date difference in days  
  `Engagement Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)`

---

## 📈 KPIs & Metrics

| Metric                  | Description |
|------------------------|-------------|
| **Total Clients**       | Total unique clients |
| **Total Loan**          | Bank + Business Lending + Credit Card Balances |
| **Bank Loan**           | Total loans taken from bank |
| **Business Lending**    | Loans given to small businesses |
| **Total Deposit**       | Sum of all deposit types |
| **Total Fees**          | Fees charged based on processing fees |
| **Checking Accounts**   | Transactional bank accounts |
| **Saving Accounts**     | Interest-based accounts |
| **Foreign Currency**    | Foreign accounts holdings |
| **Engagement Length**   | Number of days since joining |
| **Credit Cards Balance**| Outstanding credit amount |

---

## 📊 Visualizations

- **Home Page Dashboard**
- **Loan Analysis Dashboard**
- **Deposit Analysis Dashboard**
- **Summary Dashboard**

All dashboards include interactive visuals and slicers for detailed insights.

---

## 📌 Conclusion

Using Power BI, we've built a powerful risk-analysis solution tailored for banks. With clear visuals and KPIs, decision-makers can quickly assess:
- Total loan exposure
- Client engagement
- Income brackets
- Deposit trends

This reduces risks and enables better financial decisions.

---

## 🔮 Future Work

- Identify which **banks** have more clients (e.g., private vs public)
- Track which **nationalities** have the highest loan exposure
- Help in forming strategies to attract more clients
- Compare different **account types** and their usage
- Extend analysis to include **fraud detection** and **credit scoring**

---

## 🛠️ Tools Used
- **Power BI Desktop**
- DAX (Data Analysis Expressions)
- Data Modeling
- Relationship Mapping
- Custom KPIs and Measures

---

## 📁 Project Structure

```plaintext
📦Banking-Dashboard/
 ┣ 📁 PowerBI_Files/
 ┃ ┗ 📄 BankingDashboard.pbix
 ┣ 📁 Assets/
 ┃ ┗ 📄 Screenshots.png
 ┣ 📄 README.md
 ┗ 📄 Dataset.csv (or Excel File)
