# **Design and Implementation of a PySpark-Based Medallion Data Lake and Incremental ETL Pipeline**

**Course:** Big Data Computing  
**Course Code:** NOC\_CS189  
**Submitted by:** Neha Jain  
**Institution:** JK Lakshmipat University, Jaipur

## **1\. Project Overview**

This project demonstrates the design and implementation of a data lake pipeline using PySpark and Apache Spark. It uses a synthetic e-commerce dataset containing customer, product and order information.

The pipeline follows the Medallion Architecture, which organises data into three layers: Bronze, Silver and Gold. It also demonstrates incremental ETL processing so that new and updated records can be processed without performing a complete refresh every time.

## **2\. Objectives**

* Build a data processing pipeline using PySpark.  
* Implement Bronze, Silver and Gold layers.  
* Clean and validate source data.  
* Store processed data in Parquet format.  
* Demonstrate incremental ETL with new and updated records.  
* Perform sales analysis using Spark DataFrames.  
* Demonstrate MapReduce operations using Spark RDDs.  
* Create visualisations from the processed data.

## **3\. Technologies Used**

* Python  
* Apache Spark  
* PySpark  
* Google Colab  
* Google Drive  
* Parquet  
* Matplotlib  
* Graphviz  
* GitHub

## **4\. Pipeline Architecture**

The project uses the Medallion Architecture:

* **Bronze Layer:** Stores the source data in its original form in Parquet format.  
* **Silver Layer:** Cleans and validates the data, removes duplicates, handles invalid records and selects the latest order versions.  
* **Gold Layer:** Contains processed data and sales summaries for analysis.

The incremental ETL process handles new records and updates and maintains an audit record.

## **5\. Dataset Description**

A synthetic e-commerce dataset was created for this project. It contains:

| Dataset | Records |
| :---: | :---: |
| Customers | 6 |
| Products | 6 |
| Orders – Batch 1 | 17 |
| Orders – Batch 2 | 8 |
| **Total source records** | **37** |

The order batches include new records, updated records, duplicate entries and invalid records to demonstrate data cleaning and incremental processing.

## **6\. Key Implementation Features**

* Reading CSV files using Spark DataFrames.  
* Writing data in Parquet format.  
* Data cleaning and validation.  
* Duplicate detection and removal.  
* Handling invalid records separately.  
* Selecting the latest version of an order.  
* Calculating gross revenue, discount amount and net revenue.  
* Generating sales summaries by product, category, city, order status and date.  
* Demonstrating MapReduce using Spark RDD transformations.  
* Comparing full-refresh and incremental processing results.

## **7\. Results**

The pipeline successfully processed the source data and produced the following results:

* 6 customer records and 6 product records in the Silver layer.  
* 17 valid and unique orders in the final Silver layer.  
* 4 invalid order records identified and stored separately.  
* 6 Gold datasets generated for analysis.  
* 5 new orders inserted during incremental processing.  
* 3 existing orders updated.  
* 9 orders remained unchanged.  
* Full-refresh and incremental results matched, with zero differences.  
* Final data-quality checks reported no missing mandatory values, duplicate order IDs or invalid customer and product references.

The total calculated net value of the 17 orders was ₹302,050.

## **8\. Project Limitations**

The project was implemented in Google Colab using Spark in local mode. The dataset is synthetic and small, so the project demonstrates the pipeline design and processing logic rather than large-scale performance.

Incremental processing uses Spark DataFrame operations and Parquet snapshots. Transactional upserts using Delta Lake or Apache Iceberg and automated scheduling are not included.

## **9\. Future Scope**

The project can be extended by using larger real-world datasets, deploying Spark on a distributed cluster, implementing transactional storage with Delta Lake or Apache Iceberg, and adding automated pipeline scheduling and monitoring.

## **10\. Conclusion**

This project provided practical experience in building a PySpark-based data pipeline. It demonstrated how data can be stored, cleaned, validated, transformed and analysed through the Medallion Architecture. It also showed how incremental ETL can process new and updated records while maintaining consistency with a full refresh.

---

**Note:** The dataset used in this project is synthetic and was created for academic demonstration.

