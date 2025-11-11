# 🛍️ Customer Shopping Behavior - Data Cleaning & Preprocessing

## 📋 Project Overview

This project focuses on **data cleaning and preprocessing** of customer shopping behavior data. The goal is to transform raw, unstructured data into a clean, well-structured dataset ready for further analysis, exploratory data analysis (EDA), visualization, and machine learning modeling.

The dataset contains comprehensive customer purchase information including demographics, product preferences, and transaction details. Through systematic cleaning and preprocessing, we ensure data quality and consistency for downstream analytical tasks.

---

## 📊 Dataset Information

### Dataset Source
- **File**: `customer_shopping_behavior.csv`
- **Format**: CSV (Comma-Separated Values)
- **Total Records**: 3,902 rows
- **Total Features**: 18 columns

### Dataset Features
| Column | Description |
|--------|-------------|
| **Customer ID** | Unique customer identifier |
| **Age** | Customer age |
| **Gender** | Customer gender (Male/Female) |
| **Item Purchased** | Product name |
| **Category** | Product category (Clothing, Footwear, etc.) |
| **Purchase Amount (USD)** | Transaction value in USD |
| **Location** | Geographic location |
| **Size** | Product size (S, M, L, XL) |
| **Color** | Product color |
| **Season** | Season of purchase |
| **Review Rating** | Customer review rating |
| **Subscription Status** | Active subscription status |
| **Shipping Type** | Shipping method used |
| **Discount Applied** | Discount availability |
| **Promo Code Used** | Promotional code usage |
| **Previous Purchases** | Number of prior transactions |
| **Payment Method** | Payment type (Credit Card, PayPal, etc.) |
| **Frequency of Purchases** | Purchase frequency category |

### Data Quality Issues Found & Resolved
- ✅ **Missing Values**: Review Rating column had missing values → Filled with median value
- ✅ **Redundant Columns**: `promo_code_used` was identical to `discount_applied` → Removed
- ✅ **Inconsistent Column Naming**: Column names had mixed case and special characters → Standardized to lowercase with underscores
- ✅ **Categorical Data**: Frequency categories needed numeric conversion → Mapped to days

---

## 🎯 Objectives

The cleaning and preprocessing workflow accomplished the following objectives:

### 1. **Data Exploration & Validation**
   - Load and inspect dataset structure
   - Generate summary statistics
   - Identify missing values and data types

### 2. **Handling Missing Values**
   - Identified missing values in Review Rating column
   - Applied median imputation strategy to preserve data distribution

### 3. **Column Standardization**
   - Removed leading/trailing whitespace from column names
   - Converted all column names to lowercase
   - Replaced spaces with underscores for programming compatibility
   - Removed special characters (parentheses)

### 4. **Feature Engineering**
   - Created `age_group` feature by binning age into 5 categories:
     - Teen (0-19), Young Adult (20-35), Adult (36-55), Middle Aged (56-75), Senior (75+)
   - Created `purchase_frequency_days` by mapping categorical frequencies to numeric values

### 5. **Redundancy Removal**
   - Identified duplicate information between `promo_code_used` and `discount_applied`
   - Removed redundant `promo_code_used` column

### 6. **Data Export**
   - Loaded cleaned data into PostgreSQL database
   - Ensured data persistence for downstream analytics

---

## 🛠️ Tools & Libraries Used

| Tool/Library | Purpose |
|--------------|---------|
| **Python 3.x** | Programming language |
| **Jupyter Notebook** | Interactive development environment |
| **Pandas** | Data manipulation and analysis |
| **NumPy** | Numerical computations |
| **SQLAlchemy** | Database ORM |
| **psycopg2** | PostgreSQL database adapter |
| **PostgreSQL** | Data storage and persistence |

---

## 📝 Steps Performed

### Step 1: Data Loading
- Imported required libraries (Pandas)
- Loaded CSV file into a Pandas DataFrame

### Step 2: Exploratory Analysis
- Displayed first few rows using `df.head()`
- Generated summary statistics with `df.describe(include='all')`
- Checked data types and dataset shape

### Step 3: Missing Value Treatment
- Identified missing values in each column using `isnull().sum()`
- Filled missing Review Rating values with median (preserves distribution)

### Step 4: Column Name Standardization
- Applied string transformations to all column names
- Converted to lowercase, replaced spaces with underscores, removed special characters

### Step 5: Age Group Feature Engineering
- Created categorical age groups using `pd.cut()` with 5 bins
- Labels: Teen, Young Adult, Adult, Middle Aged, Senior

### Step 6: Purchase Frequency Conversion
- Mapped categorical frequencies to numeric days
- Created new `purchase_frequency_days` column for quantitative analysis

### Step 7: Redundancy Detection & Removal
- Verified that `promo_code_used` matched `discount_applied` exactly
- Dropped redundant `promo_code_used` column

### Step 8: Database Integration
- Installed SQLAlchemy and psycopg2 drivers
- Established PostgreSQL connection
- Loaded cleaned DataFrame to database table

---

## 📁 Project Structure

```
project1/
│
├── 📓 notebook.ipynb                    # Main Jupyter Notebook with all preprocessing code
├── 📊 customer_shopping_behavior.csv    # Raw customer data (input)
├── 📄 customer_shopping_behavior.sql    # SQL queries for database operations
└── 📖 README.md                         # This file
```

### Directory Description
- **notebook.ipynb**: Contains all data cleaning and preprocessing logic with documentation
- **customer_shopping_behavior.csv**: Source dataset with raw customer shopping records
- **customer_shopping_behavior.sql**: SQL scripts for database queries and analysis
- **README.md**: Project documentation and setup instructions

---

## 🚀 How to Run the Project

### Prerequisites
Ensure you have the following installed:
- Python 3.7 or higher
- Jupyter Notebook or JupyterLab
- PostgreSQL (optional, for database storage)

### Installation Steps

1. **Clone or download the project**
   ```bash
   git clone https://github.com/yourusername/customer-shopping-behavior.git
   cd customer-shopping-behavior
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   # On Windows
   venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install required packages**
   ```bash
   pip install pandas numpy jupyter sqlalchemy psycopg2-binary
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

5. **Open the notebook**
   - Navigate to `notebook.ipynb` in the Jupyter interface
   - Click to open the notebook

6. **Run the cells**
   - Execute cells sequentially using `Shift + Enter` or click "Run" button
   - Ensure all cells execute without errors

### PostgreSQL Setup (Optional)
If you want to store data in PostgreSQL:

1. Update database credentials in the notebook:
   ```python
   username = 'your_username'
   password = 'your_password'
   database = 'customer_behavior'
   host = 'localhost'
   port = '5432'
   ```

2. Create the database:
   ```sql
   CREATE DATABASE customer_behavior;
   ```

3. Run the database insertion cell in the notebook

---

## 🔮 Future Scope

This cleaned dataset is now ready for advanced analytics:

### 📈 Exploratory Data Analysis (EDA)
- Statistical summaries by demographics (age, gender, location)
- Distribution analysis of purchase amounts and frequencies
- Seasonal purchase patterns

### 📊 Data Visualization
- Customer segmentation analysis using scatter plots and heatmaps
- Revenue trends over time
- Category-wise purchase behavior
- Geographic distribution visualizations using Plotly or Seaborn

### 🤖 Machine Learning Models
- **Predictive Modeling**: Predict purchase amounts or likelihood of subscription
- **Customer Segmentation**: K-means clustering or RFM analysis
- **Churn Prediction**: Identify at-risk customers
- **Recommendation System**: Product recommendations based on purchase history

### 💡 Advanced Analytics
- Cohort analysis based on purchase frequency
- Customer lifetime value (CLV) calculation
- A/B testing frameworks for promotional strategies
- Time series forecasting for demand prediction

---

## 👤 Author

**Created by Anish chand, Aspiring Data Analyst**

This project demonstrates proficiency in data cleaning, preprocessing, feature engineering, and database integration using Python and industry-standard tools.

---

## 📄 License

This project is open source and available under the MIT License.


**Last Updated**: November 11, 2025

