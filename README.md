# 📊 SQL Data Cleaning & Analysis — Layoffs Dataset & Missing Value Handling

This repository contains two SQL-based data preprocessing projects:

1. **Layoff Data Cleaning & Standardization** – A complete end-to-end data cleaning workflow using MySQL.  
2. **Sales Data Missing Value Handling** – Using SQL techniques like COALESCE, window functions, and recursive CTEs to estimate missing values.

Both projects demonstrate practical, industry-relevant SQL concepts used in data analysis, data engineering, and ETL pipelines.

---

## 📁 Project Structure


---

## 🗂️ 1. Layoff Data Cleaning (layoff_analysis.sql)

### ✅ Overview
This SQL project focuses on cleaning and preparing a global layoffs dataset. The workflow includes:

- Creating staging tables  
- Identifying & removing duplicates  
- Standardizing inconsistent values  
- Converting text dates into SQL DATE format  
- Cleaning NULL and blank fields  
- Finalizing a clean dataset  

### 🔧 Techniques Used

- **CTEs (Common Table Expressions)**
- **ROW_NUMBER()** for duplicate detection  
- **TRIM(), LIKE, REPLACE()** for standardization  
- **Date conversion using `STR_TO_DATE()`**  
- **JOIN-based NULL value updates**
- **Removing incomplete rows**

### 📝 Key Steps

- Detect and remove duplicates:
```sql
ROW_NUMBER() OVER(PARTITION BY company, location, industry, total_laid_off, percentage_laid_off, 'date', stage, country, funds_raised_millions)

