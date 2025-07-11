## 📊 Data Cleaning using SQL – Portfolio Project

This project demonstrates **practical SQL data cleaning skills** using a real-world dataset of **tech layoffs (2022) from Kaggle**.

**Dataset:** [Layoffs 2022 - Kaggle](https://www.kaggle.com/datasets/swaptr/layoffs-2022)

The primary goal is to clean, standardize, and prepare this dataset for further analysis using **SQL best practices**.

---

## 📌 Objectives

✅ Create a **staging table** to safely clean the data while preserving the raw dataset.

✅ Identify and **remove duplicates** accurately.

✅ **Standardize data** for consistency across the dataset.

✅ Handle **NULL values** appropriately for analysis readiness.

✅ Remove **unnecessary rows and columns**.

✅ Ensure **date formats are corrected** for easy time-based analysis.

---

## 🛠️ Steps Performed

### 1️⃣ Create Staging Table

* Cloned raw data into a staging table for safe cleaning:

  ```sql
  CREATE TABLE layoffs_staging LIKE layoffs;
  INSERT layoffs_staging SELECT * FROM layoffs;
  ```

---

### 2️⃣ Remove Duplicates

* Used `ROW_NUMBER()` with `PARTITION BY` to identify duplicates accurately.
* Deleted duplicate rows while ensuring legitimate entries like **Oda** were retained.
* Used a secondary staging table (`layoffs_staging2`) for structured duplicate removal.

---

### 3️⃣ Standardize Data

* Converted empty strings in `industry` to `NULL`.
* Populated missing industries using non-null entries from the same company.
* Standardized `industry` values (e.g., unified “Crypto Currency”, “CryptoCurrency” → “Crypto”).
* Cleaned `country` field to remove trailing periods (e.g., “United States.” → “United States”).
* Converted `date` column to proper `DATE` data type using `STR_TO_DATE`.

---

### 4️⃣ Handle Null Values

* Retained `NULL` in `total_laid_off`, `percentage_laid_off`, and `funds_raised_millions` for analysis accuracy.
* Removed rows where both `total_laid_off` and `percentage_laid_off` were `NULL` and uninformative.

---

### 5️⃣ Final Cleanup

* Dropped helper columns (`row_num`) used during duplicate removal.
* Ensured a **clean, analysis-ready dataset** in `layoffs_staging2`.

---

## 🧩 Tools & Skills Applied

✅ **SQL** (window functions, CTEs, cleaning strategies)

✅ **Data Cleaning & Preprocessing**

✅ **Exploratory Data Preparation**

✅ **Date formatting & standardization**

✅ **Real-world problem-solving workflow**

---

## 📈 Next Steps (Optional)

* Perform **EDA and visualizations** on the cleaned dataset.
* Build **dashboards using Power BI or Tableau**.
* Apply **SQL analytical queries** for trend analysis on layoffs.

---

## 🚀 How This Helps

This project **demonstrates your readiness for Data Analyst roles** by showcasing:

* **structured SQL cleaning workflow**.
* Understanding of **data cleaning best practices**.
* Ability to work with **real-world messy datasets**.
