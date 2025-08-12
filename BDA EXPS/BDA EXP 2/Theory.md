# Experiment No. 2  
## Use of Sqoop Tool to Transfer Data between Hadoop and Relational Database Servers  
**A. Sqoop – Installation**  
**B. Execution of Basic Commands of Hadoop Ecosystem Component Sqoop**

---

## Aim  
Installation of Sqoop and transfer of data between Hadoop and relational database servers using Sqoop.

---

## Objective  
To transfer data between Hadoop and relational database servers using Sqoop.

---

## Outcome  
Students should be able to transfer data between Hadoop and relational database servers using Sqoop.

---

## Theory  
**Sqoop** (SQL-to-Hadoop) is used to efficiently transfer data between relational databases (such as MySQL, Oracle) and data warehouses like Hadoop HDFS (Hadoop Distributed File System).  

- **Import**: When data is transferred from a relational database to HDFS.  
- **Export**: When data is transferred from HDFS to a relational database.  

When importing data into HDFS, we can use **Apache Hive** to provide an SQL-like interface for querying data stored in HDFS.

---

## Importing Data from MySQL to HDFS  

To store data in HDFS, Apache Hive can be used as it integrates with Hadoop and provides an SQL-like interface.  

---

## Sqoop Installation & Data Transfer Process  

### Step 1: Start MySQL Database
```bash
mysql -u root -p cloudera
# Experiment No. 2  
## Use of Sqoop Tool to Transfer Data between Hadoop and Relational Database Servers  

---

## Step 2: Check Databases in MySQL
```sql
SHOW DATABASES;
USE retail_db;
SHOW TABLES;
SELECT * FROM categories;
58 rows selected
sqoop import \
--connect jdbc:mysql://localhost/retail_db \
--username root \
--password cloudera \
--table categories \
--target-dir /user/cloudera/test_import \
-m 1
hadoop fs -ls -R /user/cloudera/test_import
hadoop fs -cat /user/cloudera/test_import/part-m-00000
sqoop import \
--connect jdbc:mysql://127.0.0.1:3306/database_name_in_mysql \
--username root \
--password cloudera \
--table table_name_in_mysql \
--hive-import \
--hive-table database_name_in_hive.table_name_in_hive \
--m 1
sqoop import \
--connect jdbc:mysql://127.0.0.1:3306/database_name_in_mysql \
--username root \
--password cloudera \
--table table_name_in_mysql \
--hive-import \
--hive-table database_name_in_hive.table_name_in_hive \
--m 1


