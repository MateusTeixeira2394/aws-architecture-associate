# 1. Amazon Athena

Amazon Athena is an interactive query service that allows you to analyze data in Amazon S3 using standard SQL. It is serverless, meaning you don’t need to manage infrastructure, and you only pay for the queries you run. Athena can process structured, semi-structured, and unstructured data in a variety of formats, including CSV, JSON, Parquet, and Avro.

## 1.1. Some key features of Amazon Athena include

- **Integration with S3:** You can query data directly from S3 without needing to move or load it into Athena.
- **SQL Queries:** You can use standard SQL queries via Presto (underlying query engine).
- **Serverless:** No need to manage servers; scaling is automatic.
- **Pay-per-query:** You only pay for the amount of data scanned during queries, which can be optimized by using compressed and partitioned data formats like Parquet.

It’s typically used for ad-hoc data analysis, data exploration, and building analytics workflows with other AWS services like AWS Glue, for data cataloging and ETL processes.