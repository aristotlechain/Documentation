Hive
=================

Apache Hive is a data warehouse tool built on top of Hadoop that enables users to perform SQL-like queries on large datasets stored in HDFS. It is particularly useful for those familiar with SQL who want to analyze and process large datasets without learning complex MapReduce programming. Hive translates SQL queries (HiveQL) into MapReduce jobs or other execution engines like Tez and Spark.

Key Features of Hive
---------------------

1. SQL-like Query Language (HiveQL): Similar to SQL but designed for Hadoop.
2. Data Warehousing: Manages large datasets with tools like partitions and bucketing.
3. Integration with Hadoop Ecosystem: Runs on HDFS and integrates with other tools like Pig, Oozie, and Kafka.
4. Supports Multiple File Formats: Such as CSV, Parquet, ORC, and Avro.
5. Extensible: Users can write UDFs (User Defined Functions) to extend Hive’s capabilities.


BEFORE PROCEEDING MAKE SURE HADOOP SETUP IS DONE


Create a Warehouse Directory in HDFS:

```
hdfs dfs -mkdir -p /user/hive/warehouse
hdfs dfs -chmod g+w /user/hive/warehouse
```


Initialize Hive Metastore: Hive uses Derby by default as its metastore. We need to initialize it.

```
schematool -initSchema -dbType derby
```

![img_1.png](screenshots/img_1.png)

![img.png](screenshots/img.png)


Run hive 

```
hive
```

![img_2.png](screenshots/img_2.png)

Commands
-----------

1. Show Database 

```
SHOW DATABASES;
```

![img_3.png](screenshots/img_3.png)


2. Create and Use a Database

```
CREATE DATABASE exam_db;
USE exam_db;
```

![img_4.png](screenshots/img_4.png)


3. Create a Table

Create a simple students table to store ID, name, and age

```
CREATE TABLE students (
  id INT,
  name STRING,
  age INT
) ROW FORMAT DELIMITED 
FIELDS TERMINATED BY ',' 
STORED AS TEXTFILE;
```

![img_5.png](screenshots/img_5.png)

Explanation:
* ROW FORMAT DELIMITED: Data will be separated by a delimiter (comma in this case).
* STORED AS TEXTFILE: The data will be stored in plain text format (you can also use ORC, Parquet, etc.).



4. Insert Data into the Table

INSERT INTO students VALUES (1, 'Alice', 22), (2, 'Bob', 24);

WIP ......
