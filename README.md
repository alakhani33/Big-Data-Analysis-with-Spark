
# Big Data Analysis with Spark

This project analyzes big data with **Spark**, **PySpark** and **Spark SQL**, demonstrating the power of distributed computing and parallel programming. The solution also shows how partitioning, caching, and parquet-formatting of data can help optimize performance.

The notebook guides you through:

## Project Workflow

1. **Initialize Spark Session**
   - Create a Spark session to enable DataFrame and SQL operations.
2. **Load CSV Data**
   - Load the home sales dataset from a CSV file into a Spark DataFrame.
3. **Register SQL View**
   - Register the DataFrame as a temporary SQL view to run SQL queries on it.
4. **Query and Analyze Data**
   - Perform SQL queries to extract insights, including:
     - The number of homes sold per city
     - The average price of homes per city
     - The maximum and minimum home prices in specific locations
5. **Calculate Aggregates**
   - Compute descriptive statistics (mean, max, min) for different regions.
6. **Optional Visualizations**
   - (Add any visualization if needed using matplotlib, seaborn, or Spark plotting libraries)

## Dataset

The dataset `home_sales_revised.csv` contains columns such as:
- `id`: unique transaction ID
- `date`: sale date
- `price`: sale price
- `bedrooms`: number of bedrooms
- `bathrooms`: number of bathrooms
- `sqft_living`: living area square footage
- `sqft_lot`: lot size
- `floors`: number of floors
- `waterfront`: waterfront view indicator
- `view`: quality of view
- `condition`: condition score
- `grade`: construction grade
- `sqft_above`: square footage above ground
- `sqft_basement`: square footage basement
- `yr_built`: year built
- `yr_renovated`: year renovated
- `zipcode`: postal code
- `lat`: latitude
- `long`: longitude

## How to Run

1. Clone this repository or download the notebook.
2. Make sure **PySpark** is installed in your Python environment.
3. Place the `home_sales_revised.csv` file in the same directory as the notebook or update the path accordingly.
4. Run the notebook in Jupyter or another compatible environment.

## Example Code Snippet

```python
spark_session = SparkSession.builder.appName("HomeSalesAnalysis").getOrCreate()
sales_data_df = spark_session.read.csv("home_sales_revised.csv", header=True, inferSchema=True)
sales_data_df.createOrReplaceTempView("sales_data_table")
spark_session.sql("SELECT * FROM sales_data_table LIMIT 5").show()
```

