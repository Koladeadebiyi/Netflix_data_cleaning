# 🎬 Netflix Data Cleaning Project

## 📌 Project Overview

This project focuses on cleaning and preparing the Netflix Movies and TV Shows dataset for analysis using Python and Pandas.

The dataset contains real-world data issues such as:

* Missing values
* Mixed data types
* Inconsistent formatting
* Multi-value columns

The goal is to transform the dataset into a clean, structured format suitable for analysis and visualization.

---
https://roadmap.sh/projects/cleaning-netflix-dataset
## 📂 Dataset

Source: Kaggle Netflix Dataset
Contains information about movies and TV shows including:

* Title
* Director
* Cast
* Country
* Release year
* Duration
* Genre

---

## Data Cleaning Approach

Instead of blindly removing data, each column was analyzed and cleaned based on its meaning and importance.

### 1. Initial Exploration

* Used `.head()`, `.info()`, `.describe()`
* Identified missing values and incorrect data types

---

### 2. Handling Missing Values

| Column     | Action                | Reason                    |
| ---------- | --------------------- | ------------------------- |
| director   | Filled with "Unknown" | Many missing values       |
| cast       | Filled with "Unknown" | Not critical for analysis |
| country    | Filled & simplified   | Needed consistency        |
| date_added | Dropped missing rows  | Very few missing          |
| rating     | Filled or left as is  | Minimal impact            |

---

### 3. Fixing Data Types

* Converted `date_added` to datetime format
* Enabled time-based analysis

---

### 4. Cleaning Mixed Data (`duration` column)

Problem:

* Movies → "90 min"
* TV Shows → "1 Season"

Solution:

* Split into:

  * `duration_int` (numeric)
  * `duration_type` (min / Season)

This allows:

* Average movie duration analysis
* TV show season analysis

---

### 5. Cleaning Multi-Value Columns

`country` column contained multiple values:

* Example: "United States, India"

Solution:

* Extracted the first country using:

```python
.str.split(',').str[0]
```

---

### 6. Removing Duplicates

* Checked and removed duplicate rows to ensure data integrity

---

### 7. Final Output

* Exported cleaned dataset:

```
netflix_cleaned.csv
```

---

## 🛠 Tools Used

* Python
* Pandas
* VS Code
* Git & GitHub

---

## 📊 Key Learning Outcomes

* Understanding real-world messy data
* Column-by-column cleaning strategy
* Handling missing values intelligently
* Fixing mixed data types
* Structuring data for analysis

---

## 📎 How to Run

1. Clone the repository

```bash
git clone <your-repo-link>
```

2. Open in VS Code

3. Install dependencies

```bash
pip install pandas
```

4. Run the notebook or script
