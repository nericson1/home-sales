# home-sales

## Overview

This repository contains just one file titled `home_sales.ipynb`, which serves to demonstrate understanding of how to use PySpark to read in a CSV file and transform that into a temporary table view for SQL querying.

The ipynb file was written using Google Colab and downloaded once the code was functional and completed. After necessary dependencies were imported, a Spark Session was initiated and a dataframe was created from `home_sales_revised.csv`; the CSV was retrieved from AWS. A temporary table view of the dataframe was created and a series of SQL queries were made using Spark. Comparisons were made between the time cost of querying the data traditionally vs after caching the table vs from parquet data. The findings are as follows:

- Traditional spark.sql query took 0.689 seconds to complete
- The same spark.sql query from the cached table took 0.498 seconds to complete
- The same spark.sql query from the parquet data table took 0.533 seconds to complete

The above numbers tell us that when handling very large datasets, either caching a table for querying or writing the data into parquet format are the most time efficient ways to get results. Querying from the original table will still lead to the same results, however it may take longer than can be afforded when working with big data.

## References

All necesssary resources were provided during in class instruction so I did not need to use outside references.
