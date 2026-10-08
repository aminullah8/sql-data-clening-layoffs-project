Layoffs Data Cleaning & Analysis Using SQL

📌 Project Overview

This project focuses on cleaning and preparing a layoffs dataset using MySQL.

The main goal was to transform a raw and messy dataset into a clean, consistent, and analysis-ready dataset by identifying and removing duplicate records, standardizing data, handling null values, and correcting inconsistent entries.

This project demonstrates practical SQL skills used in Data Analytics and Data Science.

---

🎯 Objectives

- Remove duplicate records
- Standardize inconsistent data
- Handle null and blank values
- Correct inconsistent company, industry, and country names
- Convert data into appropriate formats
- Create a clean dataset for further analysis
- Practice advanced SQL concepts such as CTEs and Window Functions

---

🛠️ Tools & Technologies

- MySQL
- SQL
- Common Table Expressions (CTEs)
- Window Functions
- ROW_NUMBER()
- UPDATE
- DELETE
- ALTER TABLE
- Data Cleaning Techniques

---

📂 Dataset

The dataset contains information about company layoffs, including:

- Company
- Location
- Industry
- Total Laid Off
- Percentage Laid Off
- Date
- Company Stage
- Country
- Funds Raised in Millions

---

🔄 Data Cleaning Process

1. Remove Duplicate Records

Used ROW_NUMBER() with a CTE to identify duplicate records.

WITH duplicate_cte AS (
    SELECT *,
           ROW_NUMBER() OVER (
               PARTITION BY
                   company,
                   location,
                   industry,
                   total_laid_off,
                   percentage_laid_off,
                   date,
                   stage,
                   country,
                   funds_raised_millions
           ) AS row_num
    FROM layoffs
)
SELECT *
FROM duplicate_cte
WHERE row_num > 1;

2. Standardize Data

Standardized inconsistent values such as:

- Company names
- Industry names
- Country names
- Extra spaces
- Blank values

3. Handle Null and Blank Values

Identified missing values and converted blank values to NULL where appropriate.

4. Remove Unnecessary Records

Removed records that were not useful for the analysis or could not provide meaningful information.

5. Verify the Clean Dataset

After cleaning, queries were used to verify that:

- Duplicate records were removed
- Data was consistent
- Missing values were handled
- The dataset was ready for analysis

---

📊 Key SQL Concepts Practiced

This project helped me practice:

- SELECT
- WHERE
- UPDATE
- DELETE
- ALTER TABLE
- GROUP BY
- ORDER BY
- CASE
- Common Table Expressions (CTEs)
- Window Functions
- ROW_NUMBER()
- Data Standardization
- Data Validation

---

📁 Project Structure

Layoffs-SQL-Project/
│
├── README.md
├── layoffs.csv
└── layoffs_data_cleaning.sql

---

🚀 Future Improvements

After completing the data-cleaning stage, the cleaned dataset can be used for further analysis, such as:

- Companies with the highest layoffs
- Layoffs by year
- Layoffs by industry
- Layoffs by country
- Companies with the largest percentage layoffs
- Layoff trends over time
- Companies that raised the most funding before layoffs

---

👨‍💻 Author

Amin Ullah

Aspiring Data Analyst / Data Scientist

Skills: SQL | Data Cleaning | Data Analysis | MySQL

---

⭐ Project Purpose

This project is part of my Data Analytics and Data Science learning journey, where I am building practical projects to strengthen my SQL and data-handling skills.
