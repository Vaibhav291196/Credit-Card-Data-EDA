# Credit Card Data Exploratory Data Analysis (EDA)

## 📌 Project Overview

This project performs an in-depth Exploratory Data Analysis (EDA) on a Credit Card dataset containing customer demographics, spending transactions, repayments, credit limits, product categories, and city-level information.

The objective is to uncover customer spending behavior, repayment trends, profitability patterns, product preferences, and geographical insights that can help financial institutions make data-driven business decisions.

---

## 🎯 Business Objectives

The analysis aims to answer the following business questions:

* Understand customer spending patterns.
* Analyze repayment behavior over time.
* Identify profitable periods and customer segments.
* Determine top spending categories.
* Identify cities generating maximum revenue.
* Find high-value customers.
* Compare yearly and monthly spending trends.
* Analyze product-wise performance.
* Estimate monthly earnings/profitability.

---

## 📂 Dataset Description

The project uses three datasets:

### Customer Data

Contains customer demographic and account information.

| Feature  | Description                        |
| -------- | ---------------------------------- |
| Customer | Customer ID                        |
| Age      | Customer Age                       |
| City     | Customer City                      |
| Product  | Card Type (Gold, Platinum, Silver) |
| Limit    | Credit Limit                       |
| Company  | Company Code                       |
| Segment  | Customer Segment                   |

---

### Spend Data

Contains transaction-level spending information.

| Feature  | Description          |
| -------- | -------------------- |
| Customer | Customer ID          |
| Date     | Transaction Date     |
| Type     | Transaction Category |
| Amount   | Spending Amount      |

Examples of transaction categories:

* Petro
* Food
* Camera
* Air Ticket
* Train Ticket
* Jewellery
* Clothes
* Sandals
* Bus Ticket

---

### Repayment Data

Contains customer repayment records.

| Feature  | Description      |
| -------- | ---------------- |
| Customer | Customer ID      |
| Date     | Repayment Date   |
| Amount   | Repayment Amount |

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 📊 Data Preprocessing

### 1. Date Feature Engineering

Extracted:

```python
Month
Year
```

from transaction and repayment dates.

---

### 2. Spending Amount Validation

Business Rule:

If spending exceeds the customer's credit limit:

```python
spent_amount = 0.5 * credit_limit
```

This prevents unrealistic spending values.

---

### 3. Data Integration

Merged:

* Customer Data
* Spend Data
* Repayment Data

to perform combined analyses.

---

## 📈 Exploratory Data Analysis

### Monthly Average Spending Trend

Analyzed:

```python
customer_spend.groupby(['Year','Month'])['spent_amount'].mean()
```

Key Findings:

* Spending generally increased from 2004 to 2006.
* High spending observed during early months of the year.
* Significant fluctuations across years.

---

### Monthly Average Repayment Trend

Analyzed repayment patterns by:

```python
customer_repayment.groupby(['Year','Month'])['repayment_amount'].mean()
```

Findings:

* Repayments generally follow spending trends.
* Certain months show significantly higher repayment activity.

---

### Monthly Profitability Analysis

Calculated:

```python
Monthly Profit = Repayment Amount - Spend Amount
```

Estimated earnings using:

```python
Monthly Earnings
```

Findings:

* Positive profits observed in most periods.
* Highest earnings recorded during selected months in 2005 and 2006.

---

## 🔍 Key Insights

### Top 5 Spending Categories

| Rank | Category     |
| ---- | ------------ |
| 1    | PETRO        |
| 2    | CAMERA       |
| 3    | FOOD         |
| 4    | AIR TICKET   |
| 5    | TRAIN TICKET |

These categories contributed the largest share of spending.

---

### City with Maximum Spending

| City      | Total Spending |
| --------- | -------------- |
| COCHIN    | Highest        |
| BANGALORE | Second         |
| CALCUTTA  | Third          |

Cochin generated the highest overall spending volume.

---

### Top 10 Customers by Repayment

Top customers include:

* A61
* A60
* A42
* A13
* A38
* A43
* A40
* A14
* A44
* A26

These customers contribute significantly to repayment revenue.

---

### Product-wise Spending Analysis

Compared spending across:

* Gold
* Platinum
* Silver

Findings:

* Gold card holders generated the highest spending.
* Platinum card users showed moderate spending.
* Silver card users contributed the least spending volume.

---

### Year-wise Product Spending

Analyzed:

```python
Year × City × Product
```

Insights:

* Gold products consistently dominate spending across all cities.
* Cochin and Bangalore contribute heavily to Gold card transactions.
* Platinum card spending grew significantly in some cities over time.

---

### Monthly City-wise Spending

Compared monthly expenditures for each city.

Key observations:

* Bangalore
* Cochin
* Calcutta

showed consistently strong spending patterns across months.

---

### Air Ticket Spending Trend

Year-wise spending on Air Tickets:

| Year | Spending |
| ---- | -------- |
| 2004 | 5.56M    |
| 2005 | 9.55M    |
| 2006 | 8.66M    |

Air travel spending peaked in 2005.

---

## 📉 Visualizations Included

The project includes:

* Bar Charts
* Product-wise Spending Charts
* Monthly Spending Analysis
* Repayment Trend Analysis
* Profit Trend Analysis
* City-wise Spending Analysis
* Year-wise Product Comparisons
* Air Ticket Spending Analysis

Built using:

```python
Matplotlib
Seaborn
```

---

## 📁 Project Structure

```text
Credit-Card-EDA/
│
├── Credit_Card_Data_EDA.ipynb
├── Credit_Card_Data_EDA.pdf
├── datasets/
   ├── Customer.csv
   ├── Spend.csv
   └── Repayment.csv

```

---


---

## 📌 Business Recommendations

1. Focus marketing campaigns on high-spending cities such as Cochin, Bangalore, and Calcutta.
2. Promote Gold cards since they generate the highest spending.
3. Offer loyalty programs to top repayment customers.
4. Increase partnerships in Petro, Camera, and Travel categories.
5. Monitor months with lower profitability and improve customer engagement.

---

## 📚 Conclusion

This EDA provides valuable insights into customer spending behavior, repayment trends, product performance, and city-level revenue generation. The findings can help financial institutions optimize credit card offerings, improve customer retention strategies, and maximize profitability through data-driven decision making.

