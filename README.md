# 📊 Customer Churn Analysis Using Python

## 📌 Project Overview

Customer churn is an important business problem for subscription-based companies. Understanding **why customers leave** can help businesses identify high-risk customer groups and improve customer retention.

In this project, I performed **Exploratory Data Analysis (EDA)** on a customer churn dataset using Python.

The analysis focuses on understanding how customer characteristics such as:

* Tenure
* Contract type
* Senior-citizen status
* Gender
* Internet and other services
* Payment method
* Monthly charges
* Total charges

are related to customer churn.

The main objective of this project is to transform raw customer data into **meaningful insights through data cleaning, analysis, and visualization**.

---

# 🎯 Project Objectives

The main objectives of this analysis are:

1. Understand the structure of the customer dataset.
2. Clean and prepare the data for analysis.
3. Identify missing or incorrect values.
4. Analyze the overall customer churn rate.
5. Compare churn across different customer groups.
6. Understand how tenure is related to churn.
7. Analyze the relationship between contract type and churn.
8. Study churn patterns across customer services.
9. Analyze churn according to payment methods.
10. Generate business insights from the visualizations.

---
### Target Variable

The main target variable is:

```text
Churn
```

It contains two categories:

```text
Yes → Customer churned
No  → Customer stayed
```

---

# 🛠️ Technologies Used

The project was created using:

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 📊 Matplotlib
* 📈 Seaborn
* 📓 Jupyter Notebook

---

# 🔄 Project Workflow

The project follows a simple data analytics workflow:

text
Raw Dataset
     ↓
Data Loading
     ↓
Data Understanding
     ↓
Data Cleaning
     ↓
Data Transformation
     ↓
Exploratory Data Analysis
     ↓
Data Visualization
     ↓
Insight Generation
---

# 🧹 Data Cleaning & Preparation

Before creating visualizations, the dataset was inspected using Pandas.

### 1. Loading the dataset

```python
df = pd.read_csv("Customer Churn.csv")
```

The dataset contains:

```text
7,043 rows
21 columns
```

---

### 2. Understanding the data

The following Pandas functions were used:

```python
df.head()
df.info()
df.describe()
df.isnull().sum()
df.duplicated().sum()
```

These helped understand:

* Dataset structure
* Number of rows and columns
* Data types
* Missing values
* Duplicate records
* Numerical statistics

---

### 3. Handling `TotalCharges`

Initially, `TotalCharges` was stored as an object/string column.

Some records contained blank spaces.

The blanks were replaced with `0`, and the column was converted to a numeric data type.

```python
df["TotalCharges"] = df["TotalCharges"].replace(" ", 0)
df["TotalCharges"] = df["TotalCharges"].astype("float")
```

This made the column suitable for numerical analysis.

---

### 4. Converting `SeniorCitizen`

The original column contained:

```text
0
1
```

For easier interpretation during analysis, these values were converted into:

```text
0 → No
1 → Yes
```

This makes the visualizations easier to understand.

---

# 📊 Exploratory Data Analysis

## 1. Overall Customer Churn

The first visualization analyzes the distribution of customers who churned and customers who stayed.

### Output

The dataset contains both:

* Customers who stayed
* Customers who churned

The overall churn rate is approximately **26.54%**.

### Knowledge gained

This provides a baseline understanding of the company's churn situation.

Approximately one out of every four customers in the dataset has churned, making customer retention an important area for further investigation.

---

## 2. Churn Distribution

A count plot was used to compare:

```text
Churn = Yes
Churn = No
```

### Knowledge gained

The visualization clearly shows that customers who stayed are considerably more numerous than customers who churned.

This also demonstrates why simply looking at the number of churned customers is not enough. It is useful to compare churn percentages across different customer groups.

---

## 3. Gender vs Churn

The analysis compares customer churn across:

* Female customers
* Male customers

### Knowledge gained

The churn distribution between males and females is relatively similar.

This suggests that **gender alone does not appear to be a major differentiating factor** in the exploratory analysis.

Therefore, other variables such as contract, tenure, and payment method provide more useful areas for investigation.

---

## 4. Senior Citizen Analysis

The project analyzes the distribution of senior and non-senior customers.

It also compares churn across:

```text
Senior Citizen = Yes
Senior Citizen = No
```

### Knowledge gained

The analysis shows that senior-citizen customers form a smaller portion of the overall customer base, but their churn behavior differs from non-senior customers.

This indicates that **customer age group can be useful when studying churn patterns**.

However, this is an exploratory relationship and does not by itself establish that senior-citizen status causes churn.

---

## 5. Tenure vs Churn

`tenure` represents the number of months a customer has stayed with the company.

The analysis examines churn across different tenure levels.

### Knowledge gained

A clear pattern appears in the analysis:

> Customers with shorter tenure show higher churn.

As customers remain with the company for longer periods, churn generally becomes lower.

### Business meaning

This suggests that the **early stage of the customer relationship can be particularly important for retention**.

A company could therefore pay special attention to new customers and monitor their satisfaction during their initial months.

---

## 6. Contract Type vs Churn

Customers are divided into:

```text
Month-to-month
One year
Two year
```

The project compares churn among these contract types.

### Knowledge gained

The analysis shows a strong difference in churn behavior between contract groups.

Customers with **month-to-month contracts show substantially higher churn**, while customers with longer-term contracts show lower churn.

### Business meaning

Contract structure appears to be an important variable associated with customer retention.

This analysis can help a business understand which customer groups require greater retention attention.

---

## 7. Services vs Churn

The project analyzes several customer services, including:

* Internet Service
* Online Security
* Online Backup
* Device Protection
* Tech Support
* Streaming TV
* Streaming Movies
* Phone Service

### Knowledge gained

Churn behavior varies across different service categories.

The analysis helps identify whether customers using particular services have noticeably different churn patterns.

For example, differences can be observed between customers using different internet service types and between customers with or without additional support/security services.

### Business meaning

Service-level analysis can help a company investigate whether:

* Certain services are associated with higher churn.
* Customers with additional support services have different retention patterns.
* Particular service groups need more customer-engagement strategies.

These plots show **association, not causation**.

---

## 8. Payment Method vs Churn

The project compares churn across different payment methods:

* Electronic check
* Mailed check
* Bank transfer (automatic)
* Credit card (automatic)

### Knowledge gained

The analysis shows noticeable differences in churn across payment methods.

Customers using **electronic check show a relatively high churn pattern** compared with some other payment methods.

### Business meaning

Payment method can therefore be considered an important variable for customer-retention analysis.

Businesses could investigate whether payment experience, convenience, billing preferences, or customer characteristics associated with particular payment methods are related to these differences.

---

# 💡 Key Insights

The exploratory analysis provides several important observations:

### 1. Overall churn

Approximately **26.54%** of customers in the dataset have churned.

### 2. Tenure matters

Customers with shorter tenure show higher churn than customers who have stayed for longer periods.

### 3. Contract type is important

Month-to-month customers have noticeably higher churn compared with customers on longer-term contracts.

### 4. Payment method shows differences

Electronic-check customers show a relatively high churn pattern.

### 5. Gender has limited differentiation

Male and female customers show relatively similar churn distributions in this analysis.

### 6. Senior-citizen status shows differences

Churn behavior differs between senior and non-senior customers.

### 7. Services provide additional segmentation

Different internet and additional service categories show different churn patterns.

---

# 🧠 What I Learned From This Project

This project helped me practice the complete beginner-level data analytics process.

### Python

I learned how to use Python for data analysis.

### Pandas

I practiced:

python
read_csv()
head()
info()
describe()
isnull()
duplicated()
groupby()
agg()
replace()
astype()


### Data Cleaning

I learned how to:

* Detect missing values
* Handle blank values
* Change data types
* Transform categorical values
* Check duplicate records

### Data Visualization

I practiced creating:

* Count plots
* Bar plots
* Pie charts
* Grouped visualizations
* Churn comparisons

using Matplotlib and Seaborn.

### Exploratory Data Analysis

Most importantly, I learned how to move from:

Raw Data
   ↓
Cleaning
   ↓
Visualization
   ↓
Pattern
   ↓
Insight


instead of simply creating charts without interpreting them.

# 🚀 Future Improvements

This project currently focuses on **Exploratory Data Analysis**.

Possible future improvements include:

* Building a customer churn prediction model
* Applying machine learning algorithms
* Feature engineering
* Model evaluation using accuracy, precision, recall and F1-score
* Creating an interactive Power BI dashboard
* Developing a customer-risk segmentation system
* Identifying high-risk customer profiles

---

# ⚠️ Important Note

The findings in this project are based on **exploratory analysis**.
A relationship observed in a visualization does not necessarily mean that one variable causes customer churn.
Further statistical analysis or machine-learning modeling would be required to investigate predictive relationships.
---

# 👨‍💻 Author

**Jatin Mohan Mishra**

#Skills demonstrated:

Python • Pandas • NumPy• Matplotlib • Seaborn • Data Cleaning • EDA • Data Visualization

---

⭐ If you find this project useful, feel free to explore the notebook and analysis.
