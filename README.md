# Data-preprocessing

# Synthetic Data Report

## Introduction
For **Assignment 3**, we were tasked with exploring synthetic data to simulate real-world scenarios containing various data types, missing values, and inconsistencies. The goal of this assignment was to apply data preprocessing techniques, including cleaning, transforming, visualizing, and analyzing the data using R. Additionally, the assignment required us to provide insights and visualizations based on the processed data.

## Task 1: Data Overview
In **Task 1**, we were required to load the dataset and get an overview of the data using `head()`, `summary()`, and `str()`. The dataset contains 100 rows and 6 columns with various data types and missing values. The columns are as follows:

- **ID**: Unique identifier (integer)
- **Age**: (integer)
- **Income**: (numeric)
- **Purchase_Amount**: (numeric)
- **City**: (character)
- **Purchase_Date**: (character)
- **Membership**: (character)

Next, I used **piping** to identify columns with missing values, and found that **Age**, **City**, and **Purchase_Date** are the only columns with missing values. Furthermore, the `str()` function showed that the data types for **Purchase_Date** (character) and **Membership** (character) are not appropriate and need to be corrected to **Date** and **Factor**, respectively.

## Task 2: Counting Missing Values
In this task, I was assigned to use `sapply()` and `is.na()` to count the number of missing values in each column. I found that:

- **Age**: 1 missing value
- **City**: 31 missing values
- **Purchase_Date**: 23 missing values

Next, I visualized the missing values in these columns, as shown in the following figures:

(Insert your visualizations here)

After visualizing the missing values, I addressed them by replacing them with the mean or mode where appropriate:

- For the **Age** column, missing values were replaced with the mean age of `49.24`.
- In the case of **City**, missing values were replaced with `"Unknown"`.
- Missing values in the **Purchase_Date** column were imputed with the mode `"2024-01-01"`.

## Task 3: Correcting Data Types
As mentioned earlier, the data types for **Purchase_Date** and **Membership** were incorrect. To address this, I converted:

- **Purchase_Date** from a character type to a **Date**.
- **Membership** from a character type to a **Factor**.

## Task 4: Visualizations
As part of this task, I created the following visualizations:

1. **Histogram for Purchase_Amount**: This histogram indicates the typical spending range.
2. **Boxplot for Income**: The boxplot shows that there are no points lying outside the "whiskers," indicating that there are no outliers.
3. **Bar Chart for City Distribution**: The bar chart highlights that `"Unknown"` contributed the most to the dataset, while `"New York"` had the lowest number of occurrences.

## Task 5: Subsetting Data
I created a subset where **Age** is greater than 30 and **Income** is greater than $50,000, resulting in a data frame with 62 observations. Additionally, I filtered rows for Membership tiers `"Gold"` and `"Platinum"`.

## Bonus Tasks

1. **Cleaning City Names**: Special characters in City names were removed using `gsub()`.
2. **Membership Label Clean**: Numbers were removed from Membership labels. For example, `"Ba45sic"` was cleaned to `"Basic"`.
3. **Extracting Date Components**: I created a new column to capture the year and month from **Purchase_Date** for time-based analysis using the **data.table** library.

---

Feel free to refer to this report for a detailed overview of the assignment process and its outcomes. If you have any questions or feedback, don't hesitate to reach out!

