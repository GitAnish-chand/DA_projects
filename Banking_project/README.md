# Banking Customer Analytics Project

## Overview

This project performs comprehensive exploratory data analysis (EDA) on a banking customer dataset. It demonstrates data pipeline development, database integration, and advanced data visualization techniques to uncover customer segmentation patterns and financial insights.

## 🎯 Project Objectives

- Load and validate banking customer data from CSV format
- Integrate data with PostgreSQL database for scalable storage
- Perform exploratory data analysis to identify customer segments
- Create income-based customer classifications
- Analyze categorical distributions across customer demographics
- Generate insights on customer risk profiles and financial behaviors

## 📊 Dataset

**Source:** `Banking.csv`  
**Records:** 3,000+ customers  
**Fields:** 25 attributes including:
- **Customer Demographics:** Age, Nationality, Occupation, Gender
- **Financial Metrics:** Estimated Income, Bank Deposits, Loans, Credit Card Balance
- **Banking Products:** Credit Cards, Checking Accounts, Saving Accounts, Business Lending
- **Classification:** Risk Weighting, Loyalty Classification, Fee Structure

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| **Python 3.x** | Data processing and analysis |
| **Pandas** | Data manipulation and CSV handling |
| **SQLAlchemy** | ORM for database operations |
| **PostgreSQL** | Data storage and querying |
| **Matplotlib & Seaborn** | Data visualization |
| **NumPy** | Numerical computations |
| **Jupyter Notebook** | Interactive analysis environment |

## 📋 Project Structure

```
├── bank.ipynb                      # Main analysis notebook
├── Banking.csv                     # Source customer data
├── database_banking.sql            # Database schema
├── README.md                       # This file
└── abc.txt                         # Configuration/notes
```

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas sqlalchemy psycopg2-binary matplotlib seaborn numpy
```

### Database Setup

1. **Create PostgreSQL database:**
   ```sql
   CREATE DATABASE banking_case;
   ```

2. **Update connection string** in the notebook:
   ```python
   engine = create_engine("postgresql://postgres:password@localhost:5432/banking_case")
   ```

3. **Load schema** (if using `database_banking.sql`):
   ```bash
   psql -U postgres -d banking_case -f database_banking.sql
   ```

### Running the Analysis

1. Open `bank.ipynb` in Jupyter Notebook or VS Code
2. Install required packages (first cell)
3. Execute cells sequentially to:
   - Load CSV data
   - Connect to PostgreSQL
   - Insert data into database
   - Perform EDA
   - Generate visualizations

## 📈 Key Analysis Sections

### 1. Data Loading & Database Integration
- Read banking data from CSV
- Establish PostgreSQL connection
- Upload data to `banking_customers` table
- Query verification

### 2. Data Profiling
- Dataset shape: rows and columns
- Data types and missing values
- Statistical summary (min, max, mean, std)
- Duplicate detection

### 3. Income Segmentation
- Categorize customers into income bands:
  - **Low:** $0 - $100,000
  - **Medium:** $100,000 - $300,000
  - **High:** $300,000+
- Distribution analysis and visualization

### 4. Categorical Analysis
Detailed analysis of key customer attributes:
- Branch ID (BRId)
- Gender Distribution (GenderId)
- Nationality composition
- Occupation types
- Fee Structure preferences
- Loyalty Classification
- Risk Weighting
- Properties Owned

### 5. Cross-Dimensional Analysis
- Distribution of categorical variables by Nationality
- Count plots with Hue analysis
- Demographic insights and patterns

## 🔍 Key Findings & Insights

- **Customer Base:** Diverse nationality and occupation distribution
- **Income Distribution:** Customers distributed across three income bands
- **Credit Products:** Varying adoption of credit cards and banking products
- **Risk Profile:** Different risk weightings enable targeted customer strategies

## 📊 Visualizations Generated

- Income band distribution bar charts
- Categorical value count distributions
- Cross-tabulated analysis by demographics
- Multi-dimensional countplots

## 💡 Skills Demonstrated

✅ **Data Engineering:** ETL pipeline, CSV-to-Database loading  
✅ **Database Management:** PostgreSQL, SQLAlchemy ORM  
✅ **Data Analysis:** Exploratory Data Analysis (EDA), Statistical profiling  
✅ **Data Visualization:** Matplotlib, Seaborn advanced plotting  
✅ **Python:** Pandas, NumPy, functional programming  
✅ **Business Intelligence:** Customer segmentation, risk analysis

## 📌 Usage Notes

- Update PostgreSQL credentials before running
- Ensure database exists before data insertion
- Use `if_exists="append"` to add data incrementally
- Modify income band thresholds based on business requirements
- Filter categorical columns as needed for specific analyses

## 🔐 Security Considerations

⚠️ **Note:** Database credentials are hardcoded for demonstration. In production:
- Use environment variables for sensitive data
- Implement `.env` file with python-dotenv
- Never commit credentials to version control
- Use database connection pooling for scalability

## 📧 Data Source & Attribution

This project uses banking customer data with realistic field values for educational and analytical purposes.

## 📄 License

This project is available for educational and portfolio purposes.

---

**Last Updated:** December 2025  
**Status:** Active Development
