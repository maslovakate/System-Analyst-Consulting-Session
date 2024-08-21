# System Analyst Training Session

## Intro to Pandas for System Analysts
In the world of data analysis, system analysts often find themselves working extensively with databases and SQL to query, manipulate, and analyze data. SQL is an essential tool for interacting with structured data in relational databases, allowing for efficient data retrieval and manipulation through a declarative language.

However, as data becomes increasingly complex and diverse, there are limitations to what SQL alone can achieve, especially when it comes to advanced data manipulation, transformation, and analysis tasks. This is where Pandas, a powerful data manipulation library in Python, comes into play. Pandas provides a flexible and expressive way to work with structured data, complementing and enhancing the capabilities of SQL.

## Benefits of Pandas Over SQL
- **Working with Diverse Data Structures:**
  - **Pandas:**
    - **Versatility with Different Data Types**. Pandas can handle a wide variety of data structures, including data from **CSV files**, **Excel sheets**, **JSON**, **HTML tables**, and even **time-series data**. This makes Pandas incredibly versatile for data analysts who often need to work with data from various sources beyond just relational databases.
    - **DataFrames and Series**. In Pandas, data is typically stored in DataFrames, which are 2D labeled data structures that can hold different types of data in each column (e.g., integers, floats, strings). Pandas also supports Series, which are 1D arrays that can be used for simpler datasets or individual columns of a DataFrame.
  - **SQL:**
    - **Relational Databases Only**. SQL is inherently tied to relational databases, meaning it works best with structured, tabular data stored in tables with predefined schemas. While SQL can handle different data types (like integers, strings, and dates), it is limited to the tabular format defined by the database schema.
    - **Limited Flexibility**. To work with other data formats in SQL, you would often need to first import or convert the data into a relational format, which can be cumbersome and time-consuming.

- **In-Memory Operations:**
  - **Pandas:** Operates directly in memory, allowing for quick iteration and experimentation with data. This is particularly useful for exploratory data analysis (EDA), where analysts need to try different approaches and see immediate results.
  - **SQL:** Works with data stored on disk, which can lead to slower performance, especially with large datasets or when performing multiple joins and complex aggregations.

- **Integration with Other Tools:**
  - **Pandas:** Seamlessly integrates with other Python libraries such as NumPy, Matplotlib, and Scikit-learn, making it a versatile tool for data analysis, visualization, and machine learning.
  - **SQL:** Primarily focused on querying and managing data within a database, with limited native support for advanced analytics or visualization.

By leveraging both SQL and Pandas, system analysts can maximize their efficiency and effectiveness in handling a wide range of data tasks, from simple queries to complex transformations and analyses.

# Approaches to solving standard problems Pandas vs SQL
https://media.licdn.com/dms/document/media/D561FAQGSIx_aExvz1w/feedshare-document-pdf-analyzed/0/1723738960495?e=1724889600&v=beta&t=hN7t06uFPCec2wxi_6GxZpmnQOJCXsvjZpRouHwMkKQ

# The Importance of Data Quality Checks
In the realm of data analysis, the quality of the data you work with is paramount. No matter how sophisticated your analysis techniques or tools may be, the results are only as reliable as the data that underpins them. This is why it is crucial to perform thorough checks on data to ensure it meets the necessary standards before diving into analysis or modeling. Specifically, we focus on four key dimensions of data quality: Completeness, Consistency, Accuracy, and Integrity. Each of these dimensions plays a critical role in ensuring that your data is both reliable and meaningful.

## 1. Completeness
- **Definition**: Completeness refers to the extent to which all required data is present.
- **Example:** Checking for missing values in a DataFrame.

```import pandas as pd

# Sample DataFrame
data = {
    'id': [1, 2, 3, 4, 5],
    'name': ['Alice', 'Bob', 'Charlie', None, 'Eve'],
    'age': [25, 30, 35, 40, None]
}
df = pd.DataFrame(data)

# Check for missing values
missing_values = df.isnull().sum()

# Print missing values
print("Missing Values:\n", missing_values)```

## 2. Consistency
- **Definition:** Consistency ensures that data follows the same format or structure throughout the dataset.
- **Example:** Checking for consistent data types in each column

```# Check data types of each column
data_types = df.dtypes

# Print data types
print("Data Types:\n", data_types)```

Another example is checking if certain columns that should contain only a specific set of values actually do.

```# Suppose 'age' should only contain integers greater than 0
inconsistent_age = df[~df['age'].between(1, 100, inclusive='both')]

# Print inconsistent age entries
print("Inconsistent Age Values:\n", inconsistent_age)```

## 3. Accurancy
- **Definition:** Accuracy ensures that data correctly reflects the real-world values it represents.
- **Example:** Checking if the 'age' column contains only realistic ages.

```# Assume realistic ages are between 0 and 120
inaccurate_age = df[~df['age'].between(0, 120, inclusive='both')]

# Print inaccurate age values
print("Inaccurate Age Values:\n", inaccurate_age)```

You can also use external reference data to cross-check the accuracy of certain fields, such as addresses or product IDs.

## 4. Integrity
- **Definition:** Integrity refers to the logical coherence of the data, ensuring that relationships between data points are correct.
- **Example:** Checking if all id values in one table exist in another (foreign key relationship).

```Sample DataFrames
df_customers = pd.DataFrame({
    'customer_id': [1, 2, 3, 4],
    'name': ['Alice', 'Bob', 'Charlie', 'David']
})

df_orders = pd.DataFrame({
    'order_id': [101, 102, 103, 104],
    'customer_id': [1, 2, 5, 3]  # Note that customer_id 5 does not exist in df_customers
})

## Check for referential integrity
missing_customers = df_orders[~df_orders['customer_id'].isin(df_customers['customer_id'])]

## Print orders with missing customer references
print("Orders with Missing Customer References:\n", missing_customers)```

This will identify any rows in df_orders where the customer_id does not exist in df_customers, indicating a potential integrity issue.

## Summary:
- **Completeness:** Use isnull() to check for missing data.
- **Consistency:** Use dtypes to check data types and validate expected ranges or formats.
- **Accuracy:** Validate data against realistic boundaries or external references.
- **Integrity:** Use isin() to ensure that relationships between tables are maintained.
These checks help ensure that your data is reliable and ready for analysis, preventing errors and inconsistencies in downstream processes.
