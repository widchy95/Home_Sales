# Home_Sales.ipynb

## Overview
This project focuses on analyzing home sales data using Apache Spark, a powerful big data processing framework. The analysis is implemented in Python, utilizing Spark SQL to run complex queries efficiently. The dataset includes information such as home prices, the number of bedrooms and bathrooms, the year homes were built, and various other attributes that provide insights into the housing market.

## Objectives
The primary objectives of this project are:

1. **Data Ingestion:**
   - Load the home sales data from a CSV file hosted on AWS S3 into a Spark DataFrame.

2. **Data Exploration and Transformation:**
   - Create temporary views of the data to enable SQL-based querying.

3. **Data Analysis:**
   - Perform SQL queries to extract insights such as:
     - Average home prices for specific attributes (e.g., number of bedrooms, bathrooms, year built).
     - Price trends based on home characteristics and viewing ratings.

4. **Optimization:**
   - Cache temporary tables to improve query performance.
   - Use Parquet format for data storage and partitioning to enhance efficiency.

5. **Performance Comparison:**
   - Compare runtimes of queries executed on cached data, uncached data, and data stored in Parquet format.

## Steps

### 1. Data Loading
The dataset is loaded directly from an S3 URL into a Spark DataFrame. The schema is inferred automatically.

### 2. Data Transformation
A temporary view, `home_sales`, is created to allow for SQL queries on the data. This enables rapid analysis and filtering of data based on specific conditions.

### 3. SQL Queries
Several queries are executed to derive insights:
- **Average price for four-bedroom houses sold per year.**
- **Average price of homes with specific attributes (e.g., 3 bedrooms and 3 bathrooms) by year built.**
- **Average price of homes meeting specific criteria such as size and number of floors.**
- **Average price per view rating for homes with prices above a threshold, sorted by view rating.**

### 4. Performance Optimization
- **Caching:**
  - Temporary tables are cached to improve the runtime of repeated queries.
- **Parquet Format:**
  - The dataset is saved in Parquet format, partitioned by `date_built`, to enable efficient querying.

### 5. Performance Comparison
Query runtimes are compared for cached data, uncached data, and Parquet-formatted data, demonstrating the performance benefits of Spark's optimization techniques.

### 6. Cleanup
- Cached tables are uncached to free up memory resources.

## Key Technologies
- **Apache Spark**: For big data processing and SQL-based analysis.
- **Python**: Programming language used for scripting.
- **Parquet**: A columnar storage format for efficient data retrieval and storage.
- **AWS S3**: Source of the dataset.


## Results
- Insights into home pricing trends based on attributes like bedrooms, bathrooms, year built, and view ratings.
- Demonstrated the performance improvements achieved through caching and Parquet format.

## Conclusion
This project highlights the capabilities of Apache Spark for big data analysis and showcases how data optimization techniques can significantly improve query performance. The analysis provides valuable insights into home sales trends and characteristics.

## Prepared by
**Widchy Joachim**  
Data Analyst  
[GitHub Repository](https://github.com/widchy95/Home_Sales)
