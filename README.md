# System Analyst Training Session

## Intro to Pandas for System Analysts
In the world of data analysis, system analysts often find themselves working extensively with databases and SQL to query, manipulate, and analyze data. SQL is an essential tool for interacting with structured data in relational databases, allowing for efficient data retrieval and manipulation through a declarative language.

However, as data becomes increasingly complex and diverse, there are limitations to what SQL alone can achieve, especially when it comes to advanced data manipulation, transformation, and analysis tasks. This is where Pandas, a powerful data manipulation library in Python, comes into play. Pandas provides a flexible and expressive way to work with structured data, complementing and enhancing the capabilities of SQL.

## Benefits of Pandas Over SQL
- **Working with Diverse Data Structures:**
 - **Pandas:**
    - **Versatility with Different Data Types**. Pandas can handle a wide variety of data structures, including data from CSV files, Excel sheets, JSON, HTML tables, and even time-series data. This makes Pandas incredibly versatile for data analysts who often need to work with data from various sources beyond just relational databases.
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
