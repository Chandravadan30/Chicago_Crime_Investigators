Here is a description formatted for a GitHub project's `README.md` file.

---

# Chicago Crime Analysis with Apache Spark

This project uses Apache Spark to perform a comprehensive analysis of the "Crimes - 2001 to Present" dataset from the City of Chicago's data portal. The primary goal is to load, clean, transform, and analyze over a million rows of data to identify crime trends and patterns.

## 🚀 Project Objectives

* Utilize **Apache Spark** to handle a large-scale dataset efficiently.
* Define a proper **schema** to ensure data integrity upon loading.
* Perform **data cleaning** and **transformation** to prepare the data for analysis.
* Conduct **exploratory data analysis (EDA)** to uncover insights from the data.

## 💻 Technical Workflow

### 1. Data Ingestion & Setup
* Initializes a `SparkSession`.
* Defines a custom `StructType` schema to accurately map the CSV data.
* Loads the Chicago crime dataset (over 7 million rows) into a Spark DataFrame.

### 2. Data Cleaning & Preparation
* **Null Value Removal:** Drops all rows containing any null values.
* **Type Conversion:** Converts the `Date` column from a string to a proper `timestamp` data type for time-based analysis.
* **Temporal Filtering:** Filters the entire dataset to include only records from the **last ten years**.
* **Crime Type Filtering:** Removes records associated with the following `Primary Type` categories:
    * `'NON-CRIMINAL (SUBJECT SPECIFIED)'`
    * `'OTHER OFFENSE'`
    * `'STALKING'`
    * `'NON - CRIMINAL'`
    * `'ARSON'`
* **Data Normalization:** Merges similar crime categories to consolidate the data. For example, `Primary Type` entries like `'SEX OFFENSE'` and `'PROSTITUTION'` are grouped under a single, unified category.

### 3. Data Analysis & Insights
The project answers several key questions about crime in Chicago:

1.  **Year-wise Crime Trend:**
    * Analyzes and presents the trend of total crimes per year for the last ten years.

2.  **Peak Crime Hour:**
    * Determines the hour of the day (0-23) during which the highest number of crimes are reported.

3.  **Top 10 Crimes:**
    * Identifies the ten most frequent `Primary Type` crimes in the cleaned dataset.
    * The results are presented as a bar chart for clear visualization.

## 🛠️ Technologies Used

* **Apache Spark (PySpark)**
* Spark SQL & DataFrames
* (For visualization) Matplotlib / Seaborn
