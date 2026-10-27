# Online Retail — End-to-End Data Analysis

An exploratory data analysis project using Python to uncover retail sales trends, product performance, geographical revenue distribution, customer purchasing behaviour, and data quality issues.

## Project Overview

This project analyses the **Online Retail II** transactional dataset to understand how an online retail business performs. It covers data cleaning, feature engineering, exploratory data analysis (EDA), data visualization, and customer RFM analysis.

The goal is to transform raw transaction records into meaningful insights that can support data-driven business decisions.

## Objectives

- Inspect and understand the structure of the dataset.
- Identify missing values, duplicate records, and unusual transactions.
- Clean the data and engineer useful features.
- Calculate transaction-level revenue.
- Analyse quantity and unit-price distributions.
- Compare revenue contributions across countries.
- Examine monthly revenue trends.
- Explore relationships between numerical variables.
- Analyse customer purchasing behaviour using RFM metrics.
- Present findings through clear visualizations and summaries.

## Dataset

The project uses the `online_retail_II.csv` dataset.

The dataset contains transaction-level information about products, invoices, dates, prices, customers, and countries.

| Column | Description |
|---|---|
| `Invoice` | Invoice identifier |
| `StockCode` | Product or item code |
| `Description` | Product description |
| `Quantity` | Number of units in the transaction line |
| `InvoiceDate` | Transaction date and time |
| `Price` | Price per unit |
| `Customer ID` | Customer identifier |
| `Country` | Country associated with the transaction |

### Dataset Size

- **Original records:** 1,067,371 rows
- **Original columns:** 8
- **Exact duplicate rows removed:** 34,335
- **Rows after deduplication:** 1,033,036

## Technologies Used

- **Python** — core programming language
- **Pandas** — data manipulation and analysis
- **NumPy** — numerical operations and conditional processing
- **Matplotlib** — plotting and chart customization
- **Seaborn** — statistical data visualization
- **Jupyter Notebook** — interactive analysis and documentation

## Project Workflow

### 1. Data Loading and Inspection

- Load the CSV dataset into a Pandas DataFrame.
- Inspect the first few rows, dimensions, column names, and data types.
- Understand the structure of the transaction records.

### 2. Data Quality Assessment

- Identify missing values.
- Count exact duplicate rows.
- Convert `InvoiceDate` into a datetime format.
- Examine missing customer identifiers and product descriptions.

Missing values are handled according to the purpose of each analysis rather than automatically deleting every incomplete row.

### 3. Data Cleaning and Feature Engineering

- Remove exact duplicate rows from a working copy.
- Identify cancellation-style invoices.
- Flag negative quantities and non-positive prices.
- Calculate revenue for each transaction line.

**Revenue calculation:**

`Revenue = Quantity × Price`

### 4. Sales Data Preparation

The main sales-analysis dataset excludes:

- Cancellation-style invoices identified by the `C` prefix.
- Transactions with non-positive quantities.
- Transactions with non-positive prices.

These are explicit analysis filters. The resulting sales total is an analytical estimate based on these rules, not audited accounting revenue.

### 5. Univariate Analysis

Explore individual numerical variables using histograms and boxplots.

The analysis examines:

- Quantity distributions.
- Unit-price distributions.
- Skewness and extreme values.
- Descriptive statistics and percentiles.

Upper-percentile capping is used in selected charts to make the main distribution easier to view. It does not modify the underlying sales data.

### 6. Geographical Revenue Analysis

- Aggregate revenue by country.
- Rank countries by calculated revenue.
- Visualize the leading countries and the combined contribution of the remaining countries.
- Examine the concentration of revenue across geographical markets.

### 7. Customer Analysis — RFM

RFM stands for **Recency, Frequency, and Monetary Value**.

| Metric | Meaning |
|---|---|
| Recency | Days since the customer's last observed purchase |
| Frequency | Number of distinct invoices associated with the customer |
| Monetary | Total calculated revenue associated with the customer |

RFM provides a customer-level view of historical purchasing behaviour. Customer records without an identifiable `Customer ID` cannot be included in this customer-level analysis.

### 8. Bivariate Analysis

Explore relationships between variables using charts such as:

- Monthly revenue trend line charts.
- Country-level revenue comparisons.
- Scatter plots.
- Correlation heatmaps.

These visualizations help reveal patterns and associations. Correlation does not establish causation.

## Key Findings

The analysis produced the following results under the project's stated filtering rules:

- **1,007,913 sales-analysis rows** remained after applying the filters.
- **20,476,260.45** in calculated revenue was obtained in the dataset's price currency.
- **40,077 distinct invoices** were present in the filtered sales data.
- **5,878 identifiable customers** were available for customer-level analysis.
- **43 countries** were represented in the filtered sales data.
- The United Kingdom contributed approximately **85% of calculated revenue**.
- November 2011 was the highest-revenue month, at approximately **1,503,866.78**.
- February 2011 was the lowest-revenue month, at approximately **522,545.56**.

These figures describe the filtered dataset and should be interpreted in the context of its data quality and analysis rules.

## Business Insights

The findings can help a retail business:

- Monitor monthly sales performance and identify periods requiring further investigation.
- Understand geographical revenue concentration.
- Identify customers with recent purchases, frequent transactions, or high historical spend.
- Review unusual transactions and product descriptions.
- Develop customer retention and re-engagement strategies.
- Improve data quality checks for future reporting.

## Limitations

- Missing customer IDs limit customer-level analysis.
- Filtering choices affect the calculated sales total.
- Revenue is not the same as profit because product costs and other expenses are not included.
- Some descriptions may represent adjustments or non-merchandise entries.
- Extreme values require investigation rather than automatic deletion.
- Historical purchasing behaviour does not guarantee future customer behaviour.

## Future Improvements

- Build an interactive sales dashboard using Power BI or Plotly.
- Investigate extreme values and unusual transaction records in greater detail.
- Improve product-description standardization.
- Perform more detailed customer segmentation.
- Add profitability analysis if cost data becomes available.
- Develop repeatable reporting and monitoring workflows.

## How to Run the Project

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd YOUR_REPOSITORY_NAME
```

Replace the placeholders with your repository URL and folder name.

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Add the dataset

Place `online_retail_II.csv` in the expected location or update the CSV path in the notebook to match your computer.

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `Online_Retail_II_Complete_Analysis.ipynb` and run the cells in order.

## Repository Structure

```text
Online-Retail-II-Analysis/
│
├── Online_Retail_II_Complete_Analysis.ipynb
├── online_retail_II.csv
├── README.md
└── requirements.txt
```

The CSV is shown as part of the suggested structure; include it only if you have permission to redistribute the dataset.

## Conclusion

This project demonstrates an end-to-end retail data analysis workflow, from inspecting and cleaning transaction records to visualizing sales patterns and examining customer behaviour with RFM metrics.

It highlights how Python-based exploratory data analysis can turn raw retail data into interpretable business insights while keeping data-quality issues and analytical limitations visible.

---

**Project:** Online Retail II — End-to-End Data Analysis  
**Domain:** Data Analytics / Exploratory Data Analysis  
**Language:** Python  
**Environment:** Jupyter Notebook
