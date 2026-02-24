# 🦠 COVID-19 Data Analysis Project (Python)

## 📌 Project Overview
This mini project focuses on analyzing COVID-19 data using Python.  
The dataset was downloaded from Kaggle in CSV format and analyzed using Jupyter Notebook.

The main objective of this project is to perform data cleaning, data exploration, and data analysis to find meaningful insights about COVID-19 confirmed, death, and recovered cases across different regions.

---

## 📂 Dataset
- Source: Kaggle
- File Format: CSV
- Dataset contains:
  - Region / Country
  - Date
  - Confirmed Cases
  - Death Cases
  - Recovered Cases

---

## 🛠️ Technologies Used
- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Seaborn

---

## 🔎 Project Workflow

### 1️⃣ Import Required Libraries

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```

---

### 2️⃣ Load the Dataset

```python
df = pd.read_csv("covid_19_data.csv")
df.head()
```

---

### 3️⃣ Check for Null Values

```python
df.isnull().sum()
```

### 🔥 Visualize Null Values using Heatmap

```python
sns.heatmap(df.isnull())
plt.show()
```

---

## 📊 Data Analysis Tasks

### ✅ 1. Show number of Confirmed, Death and Recovered cases in each region

```python
df.groupby('Region')[['Confirmed', 'Deaths', 'Recovered']].sum()
```

---

### ✅ 2. Remove all records where Confirmed cases are less than 10

```python
df = df[df['Confirmed'] >= 10]
df.head()
```

---

### ✅ 3. In which region maximum number of Confirmed cases were recorded?

```python
df.groupby('Region')['Confirmed'].sum().sort_values(ascending=False).head(1)
```

---

### ✅ 4. In which region minimum number of Death cases were recorded?

```python
df.groupby('Region')['Deaths'].sum().sort_values().head(1)
```

---

### ✅ 5. How many Confirmed, Death and Recovered cases were reported from India till 29 April 2020?

```python
india_data = df[df['Region'] == 'India']
india_data = india_data[india_data['Date'] <= '2020-04-29']
india_data[['Confirmed', 'Deaths', 'Recovered']].sum()
```

---

## 📈 Skills Practiced
- Data Cleaning
- Handling Missing Values
- Data Filtering
- GroupBy Operations
- Sorting Values
- Data Visualization using Seaborn
- Basic Exploratory Data Analysis (EDA)

---

## 🚀 How to Run This Project

1. Clone the repository:

```bash
git clone https://github.com/your-username/covid19-data-analysis.git
```

2. Open Jupyter Notebook:

```bash
jupyter notebook
```

3. Run all cells step by step.

---

## 📌 Conclusion
This project helped in understanding:
- How to work with real-world datasets
- How to clean and prepare data
- How to answer analytical questions using Pandas
- How to visualize missing data
- How to extract meaningful insights from data

---

## 🙌 Author
Kishore E


---

⭐ If you found this project helpful, please give it a star!
