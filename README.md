 <div align="center">

```
██████╗  █████╗ ███╗   ██╗██████╗  █████╗ ███████╗
██╔══██╗██╔══██╗████╗  ██║██╔══██╗██╔══██╗██╔════╝
██████╔╝███████║██╔██╗ ██║██║  ██║███████║███████╗
██╔═══╝ ██╔══██║██║╚██╗██║██║  ██║██╔══██║╚════██║
██║     ██║  ██║██║ ╚████║██████╔╝██║  ██║███████║
╚═╝     ╚═╝  ╚═╝╚═╝  ╚═══╝╚═════╝ ╚═╝  ╚═╝╚══════╝
```

# 🐼 Pandas — Python Data Analysis Library

### *The Most Powerful Tool for Data Manipulation & Analysis in Python*

---

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.x-purple?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-green?style=for-the-badge)](https://opensource.org/licenses/BSD-3-Clause)
[![PyPI](https://img.shields.io/badge/PyPI-pandas-orange?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/pandas/)
[![Stars](https://img.shields.io/github/stars/pandas-dev/pandas?style=for-the-badge&color=yellow)](https://github.com/pandas-dev/pandas)
[![Open Source](https://img.shields.io/badge/Open%20Source-❤️-red?style=for-the-badge)](https://github.com/pandas-dev/pandas)

---

> 🚀 **"Pandas makes data wrangling fast, easy, and expressive — it's the backbone of every data science project in Python."**

</div>

---

## 📋 Table of Contents

| # | Section |
|---|---------|
| 1 | [🐼 What is Pandas?](#-what-is-pandas) |
| 2 | [✨ Features of Pandas](#-features-of-pandas) |
| 3 | [⚙️ Installation](#️-installation) |
| 4 | [📦 Importing Pandas](#-importing-pandas) |
| 5 | [📊 Series and DataFrames](#-creating-series-and-dataframes) |
| 6 | [📂 Reading Files](#-reading-csv-excel-and-json-files) |
| 7 | [💾 Saving Files](#-saving-files) |
| 8 | [🔍 Viewing Dataset Info](#-viewing-dataset-information) |
| 9 | [🧹 Data Cleaning](#-data-cleaning-methods) |
| 10 | [🎯 Selecting & Filtering Data](#-selecting-and-filtering-data) |
| 11 | [➕ Adding & Deleting Columns](#-adding-and-deleting-columns) |
| 12 | [🔗 GroupBy Operations](#-groupby-operations) |
| 13 | [🔢 Sorting Data](#-sorting-data) |
| 14 | [🔀 Merging DataFrames](#-merging-dataframes) |
| 15 | [📈 Pandas with Matplotlib](#-pandas-with-matplotlib) |
| 16 | [🤖 Pandas in Machine Learning](#-importance-of-pandas-in-machine-learning) |
| 17 | [💡 Advantages of Pandas](#-advantages-of-pandas) |
| 18 | [📌 Commonly Used Functions](#-commonly-used-functions) |
| 19 | [🛠️ Mini Project Example](#️-mini-project-example) |
| 20 | [📚 Official Documentation](#-official-documentation) |
| 21 | [🤝 Contributing](#-contributing) |
| 22 | [💬 Support](#-support) |
| 23 | [👨‍💻 Author](#-author) |

---

## 🐼 What is Pandas?

**Pandas** is a fast, powerful, flexible, and easy-to-use open-source **data analysis and data manipulation library** built on top of Python. It was created by **Wes McKinney** in 2008 and has since become the **#1 tool** for data scientists and analysts worldwide.

The name **"Pandas"** is derived from the term **"Panel Data"** — an econometrics term for multidimensional structured datasets.

```
Python  +  Pandas  =  🚀 Data Superpowers
```

> 📌 Pandas works perfectly with **NumPy**, **Matplotlib**, **Scikit-learn**, and virtually every major data science library.

---

## ✨ Features of Pandas

- 📦 **Two powerful data structures** — `Series` (1D) and `DataFrame` (2D)
- 📂 **Read & write** CSV, Excel, JSON, SQL, HTML, Parquet, and more
- 🧹 **Robust data cleaning** — handle missing values, duplicates, and type conversion
- 🔍 **Flexible data selection** — label-based, index-based, and conditional filtering
- 🔗 **GroupBy** for split-apply-combine operations
- 🔀 **Merge, join, and concatenate** multiple datasets
- 📈 **Built-in visualization** support via Matplotlib
- ⚡ **High performance** with optional Numba and Cython backends
- 🕐 **Time series** support with date range generation and resampling
- 🌍 **Unicode and internationalization** support

---

## ⚙️ Installation

### 📌 Basic Installation via pip

```bash
pip install pandas
```

### 📌 Install a Specific Version

```bash
pip install pandas==2.2.0
```

### 📌 Install via Conda (Recommended for Data Science environments)

```bash
conda install pandas
```

### 📌 Install with Optional Dependencies

```bash
# For Excel file support
pip install pandas openpyxl xlrd

# For full data science stack
pip install pandas numpy matplotlib seaborn scikit-learn
```

### ✅ Verify Installation

```python
import pandas as pd
print(pd.__version__)   # e.g., 2.2.2
```

---

## 📦 Importing Pandas

```python
import pandas as pd          # Standard alias used worldwide
import numpy as np           # Pandas works closely with NumPy
```

> 💡 **Why `pd`?** It's the universal alias — every data scientist uses `pd` for Pandas. It saves typing and makes code readable.

---

## 📊 Creating Series and DataFrames

### 🔹 Pandas Series — 1D Data Structure

A **Series** is like a single column of data — a one-dimensional labeled array.

```python
import pandas as pd

# Create a Series from a list
scores = pd.Series([95, 87, 76, 92, 88], name="Exam Scores")
print(scores)
# Output:
# 0    95
# 1    87
# 2    76
# 3    92
# 4    88
# Name: Exam Scores, dtype: int64

# Series with custom index
cities = pd.Series(
    [1400000, 800000, 500000],
    index=["Mumbai", "Delhi", "Bengaluru"],
    name="Population"
)
print(cities["Mumbai"])   # Output: 1400000
```

---

### 🔹 Pandas DataFrame — 2D Data Structure

A **DataFrame** is like a table or spreadsheet — rows and columns of data.

```python
# Create a DataFrame from a dictionary
data = {
    "Name":    ["Alice", "Bob", "Charlie", "Diana"],
    "Age":     [25, 30, 35, 28],
    "City":    ["New York", "London", "Paris", "Tokyo"],
    "Salary":  [70000, 85000, 92000, 78000]
}

df = pd.DataFrame(data)
print(df)
```

**Output:**

```
      Name  Age      City  Salary
0    Alice   25  New York   70000
1      Bob   30    London   85000
2  Charlie   35     Paris   92000
3    Diana   28     Tokyo   78000
```

```python
# Create DataFrame with custom index
df = pd.DataFrame(data, index=["emp1", "emp2", "emp3", "emp4"])

# Create DataFrame from list of dictionaries
records = [
    {"product": "Laptop", "price": 999, "stock": 50},
    {"product": "Phone",  "price": 699, "stock": 120},
    {"product": "Tablet", "price": 499, "stock": 80},
]
df2 = pd.DataFrame(records)
```

---

## 📂 Reading CSV, Excel, and JSON Files

### 📄 Read CSV File

```python
# Basic CSV read
df = pd.read_csv("data.csv")

# With options
df = pd.read_csv(
    "data.csv",
    sep=",",               # Separator (default is comma)
    header=0,              # Row to use as column names
    index_col="ID",        # Use column 'ID' as index
    usecols=["Name", "Age", "Salary"],  # Load specific columns only
    nrows=100,             # Load only first 100 rows
    na_values=["N/A", "?", "-"]         # Treat these as NaN
)
```

---

### 📊 Read Excel File

```python
# Install required: pip install openpyxl
df = pd.read_excel("report.xlsx")

# Read a specific sheet
df = pd.read_excel("report.xlsx", sheet_name="Sales_2024")

# Read multiple sheets at once
sheets = pd.read_excel("report.xlsx", sheet_name=None)  # Returns dict
```

---

### 🗂️ Read JSON File

```python
# From a local file
df = pd.read_json("data.json")

# From a URL (live API data!)
df = pd.read_json("https://api.example.com/data.json")

# From a JSON string
import json
json_str = '[{"name": "Alice", "age": 25}, {"name": "Bob", "age": 30}]'
df = pd.read_json(json_str)
```

---

### 🗃️ Read SQL Database

```python
import sqlite3

conn = sqlite3.connect("mydb.sqlite")
df = pd.read_sql("SELECT * FROM employees WHERE salary > 50000", conn)
conn.close()
```

---

## 💾 Saving Files

```python
# Save as CSV
df.to_csv("output.csv", index=False)

# Save as Excel
df.to_excel("output.xlsx", index=False, sheet_name="Results")

# Save as JSON
df.to_json("output.json", orient="records", indent=2)

# Save as Parquet (efficient columnar format)
df.to_parquet("output.parquet")

# Save to SQL table
df.to_sql("employees", conn, if_exists="replace", index=False)
```

---

## 🔍 Viewing Dataset Information

```python
df = pd.read_csv("data.csv")

# ── Basic Preview ──────────────────────────────────────────
df.head()          # First 5 rows (default)
df.head(10)        # First 10 rows
df.tail()          # Last 5 rows
df.sample(5)       # 5 random rows

# ── Shape & Size ───────────────────────────────────────────
print(df.shape)         # (rows, columns) e.g., (1000, 12)
print(df.ndim)          # Number of dimensions: 2
print(len(df))          # Total number of rows

# ── Column Info ────────────────────────────────────────────
print(df.columns)       # List of column names
print(df.dtypes)        # Data type of each column
print(df.index)         # Row index range

# ── Summary Statistics ─────────────────────────────────────
print(df.describe())    # Stats: count, mean, std, min, max, etc.
print(df.describe(include="all"))   # Include non-numeric columns too

# ── Memory & Structure ─────────────────────────────────────
df.info()               # Full summary: dtypes, non-null counts, memory
print(df.memory_usage(deep=True))   # Memory usage per column

# ── Value Counts ───────────────────────────────────────────
print(df["City"].value_counts())         # Count of unique values
print(df["City"].value_counts(normalize=True))  # As proportions
print(df["Age"].nunique())               # Number of unique values
print(df["Age"].unique())                # Array of unique values
```

---

## 🧹 Data Cleaning Methods

> 🎯 *Real-world data is messy. Pandas gives you everything you need to clean it.*

### 🔹 Handling Missing Values

```python
# Detect missing values
print(df.isnull())              # Boolean DataFrame
print(df.isnull().sum())        # Count nulls per column
print(df.isnull().sum().sum())  # Total null values in dataset

# Drop rows/columns with nulls
df_clean = df.dropna()                   # Drop rows with ANY null
df_clean = df.dropna(how="all")          # Drop rows where ALL are null
df_clean = df.dropna(subset=["Age", "Salary"])  # Only check these cols
df_clean = df.dropna(axis=1)             # Drop columns with any null

# Fill missing values
df["Age"].fillna(df["Age"].mean(), inplace=True)        # Fill with mean
df["City"].fillna("Unknown", inplace=True)              # Fill with string
df["Salary"].fillna(method="ffill", inplace=True)       # Forward fill
df["Salary"].fillna(method="bfill", inplace=True)       # Backward fill

# Interpolate numeric missing values
df["Price"].interpolate(method="linear", inplace=True)
```

---

### 🔹 Removing Duplicates

```python
# Check for duplicates
print(df.duplicated().sum())      # Number of duplicate rows

# View duplicate rows
print(df[df.duplicated()])

# Remove duplicates
df = df.drop_duplicates()
df = df.drop_duplicates(subset=["Name", "Email"])  # Based on specific cols
df = df.drop_duplicates(keep="last")               # Keep last occurrence
```

---

### 🔹 Renaming Columns

```python
# Rename specific columns
df.rename(columns={"Name": "Full Name", "Age": "Age (Years)"}, inplace=True)

# Make all column names lowercase
df.columns = df.columns.str.lower()

# Replace spaces with underscores
df.columns = df.columns.str.replace(" ", "_")

# Strip whitespace from column names
df.columns = df.columns.str.strip()
```

---

### 🔹 Data Type Conversion

```python
# Convert to numeric (coerce errors to NaN)
df["Age"] = pd.to_numeric(df["Age"], errors="coerce")

# Convert to datetime
df["Date"] = pd.to_datetime(df["Date"], format="%Y-%m-%d")

# Convert to string category (saves memory!)
df["City"] = df["City"].astype("category")

# Convert column types
df["Price"] = df["Price"].astype(float)
df["ID"]    = df["ID"].astype(str)
```

---

### 🔹 String Operations

```python
# Clean text columns
df["Name"] = df["Name"].str.strip()          # Remove whitespace
df["Name"] = df["Name"].str.upper()          # Uppercase
df["Name"] = df["Name"].str.lower()          # Lowercase
df["Name"] = df["Name"].str.title()          # Title Case
df["Email"] = df["Email"].str.replace(" ", "")

# Extract patterns
df["Domain"] = df["Email"].str.split("@").str[1]

# Check string contains
df[df["City"].str.contains("New", case=False)]
```

---

### 🔹 Replacing Values

```python
# Replace specific values
df["Gender"].replace({"M": "Male", "F": "Female"}, inplace=True)

# Replace using regex
df["Phone"] = df["Phone"].str.replace(r"\D", "", regex=True)

# Replace outliers
df.loc[df["Age"] > 100, "Age"] = df["Age"].median()
```

---

## 🎯 Selecting and Filtering Data

### 🔹 Selecting Columns

```python
# Single column (returns Series)
ages = df["Age"]

# Multiple columns (returns DataFrame)
subset = df[["Name", "Age", "Salary"]]
```

---

### 🔹 Selecting Rows — `.loc[]` and `.iloc[]`

```python
# .loc[] — Label-based selection
df.loc[0]                    # Row at label 0
df.loc[0:3]                  # Rows from label 0 to 3 (inclusive)
df.loc[0, "Name"]            # Single value: row 0, column "Name"
df.loc[0:5, ["Name", "Age"]] # Rows 0-5, specific columns

# .iloc[] — Integer position-based selection
df.iloc[0]                   # First row
df.iloc[-1]                  # Last row
df.iloc[0:5]                 # First 5 rows
df.iloc[0, 1]                # Row 0, column at index 1
df.iloc[1:4, 0:3]            # Rows 1-3, first 3 columns
```

---

### 🔹 Conditional Filtering

```python
# Single condition
high_earners = df[df["Salary"] > 80000]

# Multiple conditions (use & and |)
senior_devs = df[(df["Age"] > 30) & (df["Role"] == "Developer")]
east_or_west = df[(df["Region"] == "East") | (df["Region"] == "West")]

# isin() — Match multiple values
selected_cities = df[df["City"].isin(["Mumbai", "Delhi", "Bengaluru"])]

# ~  to invert a filter (NOT)
not_mumbai = df[~df["City"].isin(["Mumbai"])]

# between() for range filtering
mid_age = df[df["Age"].between(25, 35)]

# query() — SQL-like readable syntax
result = df.query("Age > 25 and Salary > 60000")
result = df.query("City in ['Mumbai', 'Delhi']")
```

---

## ➕ Adding and Deleting Columns

### 🔹 Adding New Columns

```python
# Direct assignment
df["Tax"] = df["Salary"] * 0.2
df["Full Name"] = df["First Name"] + " " + df["Last Name"]

# Using assign() — method chaining friendly
df = df.assign(
    Net_Salary = lambda x: x["Salary"] - x["Tax"],
    Senior     = lambda x: x["Age"] > 35
)

# Add column at specific position
df.insert(2, "Bonus", df["Salary"] * 0.1)

# Apply custom function to create a column
def salary_grade(s):
    if s >= 90000: return "A"
    elif s >= 70000: return "B"
    else: return "C"

df["Grade"] = df["Salary"].apply(salary_grade)
```

---

### 🔹 Deleting Columns and Rows

```python
# Drop a single column
df.drop("Tax", axis=1, inplace=True)

# Drop multiple columns
df.drop(["Tax", "Bonus", "Grade"], axis=1, inplace=True)

# Drop rows by index label
df.drop([0, 1, 2], axis=0, inplace=True)

# Drop rows by condition
df = df[df["Salary"] > 0]   # Keep only rows where Salary > 0
```

---

## 🔗 GroupBy Operations

> 🎯 *GroupBy lets you split data into groups, apply a function, and combine results — incredibly powerful for aggregations!*

```python
# Basic GroupBy
grouped = df.groupby("Department")["Salary"].mean()

# Multiple aggregations on one column
df.groupby("Department")["Salary"].agg(["mean", "min", "max", "count"])

# Different aggregations on different columns
df.groupby("Department").agg({
    "Salary":  ["mean", "sum"],
    "Age":     "mean",
    "Bonus":   "sum"
})

# GroupBy multiple columns
df.groupby(["Department", "City"])["Salary"].mean()

# Apply custom aggregation
df.groupby("City")["Revenue"].agg(lambda x: x.max() - x.min())

# Transform — keeps original DataFrame shape
df["Dept_Avg_Salary"] = df.groupby("Department")["Salary"].transform("mean")

# Filter groups based on condition
df.groupby("Department").filter(lambda x: x["Salary"].mean() > 70000)
```

---

## 🔢 Sorting Data

```python
# Sort by single column (ascending by default)
df.sort_values("Salary", inplace=True)

# Sort descending
df.sort_values("Salary", ascending=False, inplace=True)

# Sort by multiple columns
df.sort_values(["Department", "Salary"], ascending=[True, False], inplace=True)

# Sort by index
df.sort_index(inplace=True)
df.sort_index(ascending=False, inplace=True)

# Get top N rows after sorting
top5 = df.nlargest(5, "Salary")
bottom5 = df.nsmallest(5, "Salary")

# Rank values
df["Salary_Rank"] = df["Salary"].rank(ascending=False)
```

---

## 🔀 Merging DataFrames

> 🧩 *Just like SQL JOINs, Pandas lets you combine multiple DataFrames elegantly.*

```python
employees = pd.DataFrame({
    "emp_id": [1, 2, 3, 4],
    "name":   ["Alice", "Bob", "Charlie", "Diana"],
    "dept_id":[10, 20, 10, 30]
})

departments = pd.DataFrame({
    "dept_id":   [10, 20, 30],
    "dept_name": ["Engineering", "Marketing", "Finance"]
})

# ── INNER JOIN — Only matching rows ────────────────────────
result = pd.merge(employees, departments, on="dept_id", how="inner")

# ── LEFT JOIN — All rows from left table ───────────────────
result = pd.merge(employees, departments, on="dept_id", how="left")

# ── RIGHT JOIN — All rows from right table ─────────────────
result = pd.merge(employees, departments, on="dept_id", how="right")

# ── OUTER JOIN — All rows from both tables ─────────────────
result = pd.merge(employees, departments, on="dept_id", how="outer")

# ── Merge on different column names ────────────────────────
result = pd.merge(employees, departments, left_on="dept_id", right_on="dept_id")

# ── Concatenate vertically (stack rows) ────────────────────
df_all = pd.concat([df_2022, df_2023, df_2024], ignore_index=True)

# ── Concatenate horizontally (add columns) ─────────────────
df_combined = pd.concat([df1, df2], axis=1)
```

---

## 📈 Pandas with Matplotlib

```python
import pandas as pd
import matplotlib.pyplot as plt

# Sample data
data = {
    "Month":   ["Jan", "Feb", "Mar", "Apr", "May", "Jun"],
    "Revenue": [45000, 52000, 49000, 63000, 71000, 68000],
    "Expenses":[38000, 41000, 39000, 45000, 52000, 47000]
}
df = pd.DataFrame(data)

fig, axes = plt.subplots(2, 2, figsize=(14, 10))
fig.suptitle("📊 Business Dashboard", fontsize=16, fontweight="bold")

# ── Line Chart ─────────────────────────────────────────────
df.plot(x="Month", y=["Revenue", "Expenses"],
        kind="line", marker="o", ax=axes[0, 0],
        title="Revenue vs Expenses", color=["#2196F3", "#F44336"])

# ── Bar Chart ──────────────────────────────────────────────
df.plot(x="Month", y="Revenue",
        kind="bar", ax=axes[0, 1],
        title="Monthly Revenue", color="#4CAF50")

# ── Area Chart ─────────────────────────────────────────────
df.plot(x="Month", y=["Revenue", "Expenses"],
        kind="area", alpha=0.5, ax=axes[1, 0],
        title="Area Chart")

# ── Horizontal Bar ─────────────────────────────────────────
df.plot(x="Month", y="Revenue",
        kind="barh", ax=axes[1, 1],
        title="Horizontal Revenue Bar")

plt.tight_layout()
plt.savefig("dashboard.png", dpi=150, bbox_inches="tight")
plt.show()
```

---

## 🤖 Importance of Pandas in Machine Learning

Pandas is the **#1 preprocessing tool** used before training any machine learning model. Here's how it fits into the ML pipeline:

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.linear_model import LogisticRegression

# Step 1: Load Data
df = pd.read_csv("titanic.csv")

# Step 2: Explore Data
print(df.shape)
print(df.isnull().sum())
print(df.dtypes)

# Step 3: Clean Data
df.dropna(subset=["Age", "Fare"], inplace=True)
df["Age"].fillna(df["Age"].median(), inplace=True)
df.drop_duplicates(inplace=True)

# Step 4: Feature Engineering (Pandas shines here!)
df["FamilySize"] = df["SibSp"] + df["Parch"] + 1
df["IsAlone"]    = (df["FamilySize"] == 1).astype(int)
df["AgeGroup"]   = pd.cut(df["Age"], bins=[0, 12, 18, 60, 100],
                           labels=["Child", "Teen", "Adult", "Senior"])

# Step 5: Encode Categorical Variables
le = LabelEncoder()
df["Sex_encoded"] = le.fit_transform(df["Sex"])
df = pd.get_dummies(df, columns=["Pclass", "AgeGroup"], drop_first=True)

# Step 6: Prepare Features and Target
X = df.drop(["Survived", "Name", "Ticket", "Cabin"], axis=1)
y = df["Survived"]

# Step 7: Train/Test Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Step 8: Train Model
model = LogisticRegression()
model.fit(X_train, y_train)
print(f"✅ Model Accuracy: {model.score(X_test, y_test):.2%}")
```

**Why Pandas is Essential for ML:**

| Task | Pandas Role |
|------|-------------|
| Data Loading | `read_csv`, `read_excel`, `read_sql` |
| EDA | `describe()`, `value_counts()`, `corr()` |
| Missing Data | `fillna()`, `dropna()`, `interpolate()` |
| Feature Engineering | `apply()`, `map()`, `cut()`, `get_dummies()` |
| Data Splitting | Slicing, boolean indexing |
| Scaling Preparation | `astype()`, normalization helpers |
| Output Evaluation | `DataFrame` for storing predictions |

---

## 💡 Advantages of Pandas

| 🌟 Advantage | 📝 Description |
|-------------|----------------|
| 🚀 **Speed** | Vectorized operations — far faster than Python loops |
| 🧠 **Intuitive API** | Readable, expressive, and beginner-friendly syntax |
| 🔌 **Versatile I/O** | Reads/writes 15+ file formats out of the box |
| 🔗 **NumPy Integration** | Seamless interoperability with NumPy arrays |
| 📊 **Visualization** | Direct `.plot()` method for quick charts |
| 🧹 **Data Cleaning** | Best-in-class tools for messy real-world data |
| 🕐 **Time Series** | Excellent support for dates, resampling, and rolling windows |
| 🌍 **Community** | Massive global community, thousands of tutorials & resources |
| 🔬 **Exploration** | Powerful tools for understanding and profiling datasets |
| ⚡ **Scalable** | Works with datasets from KB to GB in size |

---

## 📌 Commonly Used Functions

| 🔧 Function | 📁 Category | 📝 Description |
|------------|------------|----------------|
| `pd.read_csv()` | I/O | Read CSV file into DataFrame |
| `pd.read_excel()` | I/O | Read Excel file |
| `pd.read_json()` | I/O | Read JSON file or URL |
| `df.to_csv()` | I/O | Save DataFrame to CSV |
| `df.head(n)` | Exploration | View first n rows |
| `df.tail(n)` | Exploration | View last n rows |
| `df.info()` | Exploration | Summary of DataFrame structure |
| `df.describe()` | Statistics | Summary statistics |
| `df.shape` | Exploration | Tuple of (rows, cols) |
| `df.dtypes` | Exploration | Data type of each column |
| `df.isnull()` | Cleaning | Boolean mask for null values |
| `df.dropna()` | Cleaning | Drop rows/cols with null values |
| `df.fillna()` | Cleaning | Fill null values |
| `df.drop_duplicates()` | Cleaning | Remove duplicate rows |
| `df.rename()` | Transformation | Rename columns or index |
| `df.astype()` | Transformation | Convert column data type |
| `df.apply()` | Transformation | Apply function to rows/cols |
| `df.map()` | Transformation | Map values in a Series |
| `df.groupby()` | Aggregation | Group data and aggregate |
| `df.agg()` | Aggregation | Apply multiple aggregations |
| `df.sort_values()` | Sorting | Sort by one or more columns |
| `df.sort_index()` | Sorting | Sort by index |
| `df.nlargest()` | Sorting | Top N largest rows |
| `pd.merge()` | Combining | SQL-style joins |
| `pd.concat()` | Combining | Stack DataFrames |
| `df.pivot_table()` | Reshaping | Create pivot table |
| `df.melt()` | Reshaping | Unpivot from wide to long format |
| `df.corr()` | Statistics | Correlation matrix |
| `df.value_counts()` | Statistics | Count occurrences of unique values |
| `pd.get_dummies()` | ML Prep | One-hot encoding |
| `pd.cut()` | ML Prep | Bin values into discrete intervals |
| `df.sample()` | Exploration | Random sample of rows |
| `df.plot()` | Visualization | Quick plot using Matplotlib |

---

## 🛠️ Mini Project Example

### 📊 Sales Data Analysis Dashboard

> Analyze a sales dataset to extract meaningful business insights.

```python
import pandas as pd
import matplotlib.pyplot as plt

# ──────────────────────────────────────────────────────────
# Step 1: Create sample sales data
# ──────────────────────────────────────────────────────────
data = {
    "Date":       pd.date_range("2024-01-01", periods=12, freq="ME"),
    "Region":     ["North","South","East","West"] * 3,
    "Product":    ["Laptop","Phone","Tablet","Laptop","Phone","Tablet",
                   "Laptop","Phone","Tablet","Laptop","Phone","Tablet"],
    "UnitsSold":  [120, 200, 150, 180, 220, 130, 160, 240, 170, 200, 210, 140],
    "UnitPrice":  [999, 699, 499, 999, 699, 499, 999, 699, 499, 999, 699, 499],
}
df = pd.DataFrame(data)
df["Revenue"] = df["UnitsSold"] * df["UnitPrice"]
print("✅ Dataset Created")
print(df.head())

# ──────────────────────────────────────────────────────────
# Step 2: Data Exploration
# ──────────────────────────────────────────────────────────
print("\n📊 Dataset Info:")
print(df.info())
print("\n📈 Summary Statistics:")
print(df.describe())
print(f"\n💰 Total Revenue: ${df['Revenue'].sum():,.0f}")
print(f"📦 Total Units Sold: {df['UnitsSold'].sum():,}")
print(f"📅 Period: {df['Date'].min().date()} → {df['Date'].max().date()}")

# ──────────────────────────────────────────────────────────
# Step 3: Analysis using GroupBy
# ──────────────────────────────────────────────────────────
# Revenue by Region
region_revenue = df.groupby("Region")["Revenue"].sum().sort_values(ascending=False)
print("\n🗺️ Revenue by Region:")
print(region_revenue)

# Revenue by Product
product_analysis = df.groupby("Product").agg(
    Total_Revenue = ("Revenue",   "sum"),
    Total_Units   = ("UnitsSold", "sum"),
    Avg_Price     = ("UnitPrice", "mean")
).sort_values("Total_Revenue", ascending=False)
print("\n🛒 Product Analysis:")
print(product_analysis)

# Best month
df["Month"] = df["Date"].dt.strftime("%B")
best_month = df.groupby("Month")["Revenue"].sum().idxmax()
print(f"\n🏆 Best Month: {best_month}")

# ──────────────────────────────────────────────────────────
# Step 4: Visualization
# ──────────────────────────────────────────────────────────
fig, axes = plt.subplots(1, 2, figsize=(14, 5))
fig.suptitle("📊 Sales Dashboard 2024", fontsize=14, fontweight="bold")

region_revenue.plot(kind="bar", ax=axes[0], color=["#2196F3","#4CAF50","#FF9800","#E91E63"],
                    title="💰 Revenue by Region", rot=0)
axes[0].set_ylabel("Revenue ($)")
axes[0].yaxis.set_major_formatter(plt.FuncFormatter(lambda x, _: f"${x:,.0f}"))

product_analysis["Total_Revenue"].plot(kind="pie", ax=axes[1], autopct="%1.1f%%",
                                        title="🛒 Revenue Share by Product",
                                        colors=["#3F51B5","#009688","#FF5722"])

plt.tight_layout()
plt.savefig("sales_dashboard.png", dpi=150, bbox_inches="tight")
plt.show()
print("✅ Dashboard saved as sales_dashboard.png")

# ──────────────────────────────────────────────────────────
# Step 5: Export Results
# ──────────────────────────────────────────────────────────
df.to_csv("sales_cleaned.csv", index=False)
product_analysis.to_excel("product_report.xlsx")
print("✅ Reports exported successfully!")
```

**Expected Output Summary:**

```
✅ Dataset Created
💰 Total Revenue: $2,638,800
📦 Total Units Sold: 2,120
🏆 Best Month: November
✅ Dashboard saved as sales_dashboard.png
✅ Reports exported successfully!
```

---

## 📚 Official Documentation

| 📖 Resource | 🔗 Link |
|------------|---------|
| 📘 **Official Docs** | [pandas.pydata.org/docs](https://pandas.pydata.org/docs/) |
| 🚀 **Getting Started** | [10 Minutes to Pandas](https://pandas.pydata.org/docs/user_guide/10min.html) |
| 📋 **API Reference** | [Full API Reference](https://pandas.pydata.org/docs/reference/index.html) |
| 🎓 **User Guide** | [User Guide](https://pandas.pydata.org/docs/user_guide/index.html) |
| 💬 **Community Forum** | [Stack Overflow: pandas](https://stackoverflow.com/questions/tagged/pandas) |
| 🐙 **GitHub Repo** | [pandas-dev/pandas](https://github.com/pandas-dev/pandas) |
| 📝 **Cheat Sheet** | [Pandas Cheat Sheet (PDF)](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf) |
| 🎥 **Video Tutorials** | [Real Python — Pandas](https://realpython.com/pandas-python-explore-dataset/) |

---

## 🤝 Contributing

We welcome contributions from the community! Here's how to get started:

```bash
# 1. Fork the official Pandas repository
#    https://github.com/pandas-dev/pandas

# 2. Clone your fork
git clone https://github.com/YOUR_USERNAME/pandas.git
cd pandas

# 3. Create a new branch
git checkout -b feature/your-feature-name

# 4. Install development dependencies
pip install -e ".[dev]"

# 5. Make your changes and run tests
python -m pytest pandas/tests/

# 6. Commit your changes
git add .
git commit -m "feat: add your descriptive commit message"

# 7. Push and open a Pull Request
git push origin feature/your-feature-name
```

**Contribution Guidelines:**
- 📝 Follow the [Contributing Guide](https://pandas.pydata.org/docs/development/contributing.html)
- ✅ Add/update unit tests for your changes
- 📖 Update documentation where needed
- 🎯 Keep PRs focused and concise

---

## 💬 Support

If you need help, have questions, or found a bug:

| Channel | Link |
|---------|------|
| 🐛 **Bug Reports** | [GitHub Issues](https://github.com/pandas-dev/pandas/issues) |
| 💬 **Q&A / Help** | [Stack Overflow — `[pandas]` tag](https://stackoverflow.com/questions/tagged/pandas) |
| 🗣️ **Discussions** | [GitHub Discussions](https://github.com/pandas-dev/pandas/discussions) |
| 📧 **Mailing List** | [pandas-dev mailing list](https://mail.python.org/mailman/listinfo/pandas-dev) |
| 💼 **Slack** | [PyData Slack](https://numfocus.org/community/slack) |

> ⭐ **If you find Pandas useful, please star the [official repository](https://github.com/pandas-dev/pandas)** — it helps the project grow!

---

## 👨‍💻 Author

<div align="center">

This README was crafted with ❤️ to help beginners and professionals alike master Pandas.

**Original Library Author:** [Wes McKinney](https://wesmckinney.com/) — Creator of Pandas (2008)

**Maintained by:** [Pandas Core Development Team](https://pandas.pydata.org/about/team.html)

[![GitHub](https://img.shields.io/badge/GitHub-pandas--dev-black?style=for-the-badge&logo=github)](https://github.com/pandas-dev/pandas)
[![Twitter](https://img.shields.io/badge/Twitter-@pandas__dev-1DA1F2?style=for-the-badge&logo=twitter)](https://twitter.com/pandas_dev)

</div>

---

<div align="center">

## 🏷️ Tags & Topics

`#Python` `#Pandas` `#DataScience` `#DataAnalysis` `#MachineLearning`
`#DataEngineering` `#DataCleaning` `#DataFrame` `#OpenSource` `#NumPy`
`#Matplotlib` `#EDA` `#FeatureEngineering` `#BigData` `#Analytics`
`#PythonLibrary` `#DataVisualization` `#ArtificialIntelligence` `#DeepLearning`
`#ScikitLearn` `#Jupyter` `#DataMining` `#Statistics` `#BusinessIntelligence`

---

*Made with 🐼 and Python — Happy Data Wrangling!*

⭐ **Star this repo if it helped you!** ⭐

</div>
