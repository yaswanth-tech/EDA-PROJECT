# Data Cleaning and Exploratory Data Analysis

## 📌 Project Overview

This project focuses on **Data Cleaning and Exploratory Data Analysis (EDA)** using Python and Pandas.

The main objective is to prepare a raw dataset for analysis by identifying and handling:

- Missing values
- Inconsistent values
- Duplicate records
- Incorrect or unwanted data formats
- Categorical data inconsistencies
- Basic statistical information

After cleaning the dataset, exploratory analysis is performed to understand the data and identify useful patterns.

---

## 🎯 Objectives

- Load and inspect the dataset.
- Identify missing and null values.
- Handle missing values appropriately.
- Detect and correct inconsistent values.
- Remove unnecessary spaces and formatting issues.
- Check and remove duplicate records.
- Perform basic data exploration.
- Prepare a clean dataset for further analysis.

---

## 🛠️ Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Google Colab**
- **Matplotlib**
- **Seaborn**

---

## 📂 Dataset

The project uses a dataset containing demographic and employment-related information.

Important columns include:

- Age
- Workclass
- Final Weight
- Education
- Education Number
- Marital Status
- Occupation
- Relationship
- Race
- Gender
- Capital Gain
- Capital Loss
- Hours per Week
- Native Country
- Income

---

## 🔄 Data Cleaning Process

### 1. Loading the Dataset

The dataset is loaded using Pandas.

```python
import pandas as pd

df = pd.read_csv("dataset.csv")
```

### 2. Understanding the Dataset

The dataset is inspected using:

```python
df.head()
df.shape
df.info()
df.describe()
```

### 3. Identifying Missing Values

Missing values are checked using:

```python
df.isnull().sum()
```

Values represented using `?` are converted into missing values:

```python
df = df.replace("?", pd.NA)
```

### 4. Handling Missing Values

Missing values can be handled using suitable methods such as:

- Mean
- Median
- Mode
- Constant values

For categorical columns, the mode can be used:

```python
df["Workclass"] = df["Workclass"].fillna(df["Workclass"].mode()[0])
```

### 5. Handling Inconsistency

Inconsistent categorical values are identified using:

```python
df["Gender"].unique()
```

Extra spaces can be removed using:

```python
df["Gender"] = df["Gender"].str.strip()
```

Different representations of the same value can be standardized:

```python
df["Gender"] = df["Gender"].replace({
    "M": "Male",
    "male": "Male",
    "F": "Female",
    "female": "Female"
})
```

### 6. Removing Duplicates

Duplicate records are checked:

```python
df.duplicated().sum()
```

Duplicates can be removed using:

```python
df = df.drop_duplicates()
```

### 7. Final Verification

After cleaning, the dataset is checked again:

```python
print(df.isnull().sum())
print(df.shape)
```

---

## 📊 Exploratory Data Analysis

Basic analysis is performed to understand the dataset.

Examples include:

```python
df["Age"].mean()
df["Age"].median()
df["Age"].min()
df["Age"].max()
```

Categorical distributions can be checked using:

```python
df["Education"].value_counts()
```

---

## 📈 Data Visualization

Matplotlib and Seaborn can be used to visualize relationships and distributions.

Example:

```python
import matplotlib.pyplot as plt
import seaborn as sns

sns.histplot(df["Age"])
plt.show()
```

---

## 🔍 Key Data Cleaning Tasks

| Task | Method |
|---|---|
| Missing values | `isnull()` / `fillna()` |
| Inconsistent values | `replace()` |
| Extra spaces | `str.strip()` |
| Duplicate records | `drop_duplicates()` |
| Data inspection | `info()` |
| Statistical analysis | `describe()` |
| Category analysis | `value_counts()` |

---

## 📁 Project Structure

```text
Data-Cleaning-EDA/
│
├── dataset.csv
├── Data_Cleaning_EDA.ipynb
└── README.md
```

---

## 🚀 How to Run

1. Open the Google Colab notebook.
2. Upload the dataset.
3. Run the cells sequentially.
4. Perform data cleaning.
5. Verify the cleaned dataset.
6.
