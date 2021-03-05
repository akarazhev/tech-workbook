# Big data technology stack

The following describes each technology in different layers. Of course, each layer is not strictly divided in the literal sense. For example, Hive provides both data processing functions and data storage functions, but it is classified as a data analysis layer here.

## 1. Data acquisition and transmission layer

### Flume
Flume is a distributed, reliable, and highly available system for data collection, aggregation and transmission. Commonly used in log collection systems, it supports customizing various data senders to collect data, simple pre-processing of data through custom interceptors, and transmission to various data receivers such as HDFS, HBase, and Kafka. Previously developed by Cloudera, later incorporated into Apache

### Sqoop
Sqoop is a tool for data import and export through a set of commands. The underlying engine relies on MapReduce and is mainly used for data import and export between Hadoop (such as HDFS, Hive, HBase) and RDBMS (such as mysql, oracle)

### Kafka
It is a Distributed messaging system. Producer (producer)-consumer (consumer) model. Provides features similar to JMS, but is completely different in design and does not follow JMS specifications. For example, Kafka allows multiple consumers to actively pull data, while only peer-to-peer consumers in JMS will actively pull data. Mainly used in data buffering, asynchronous communication, data collection, system coupling, etc.

### The Pulsar
It is Similar to Kafka, but Pulsar supports multi-tenancy and has the concept of assets and namespaces. Assets represent tenants in the system. Assuming a Pulsar cluster is used to support multiple applications, each asset in the cluster can represent an organization’s team, a core function or a product line. An asset can contain multiple namespaces, and a namespace can contain any number of topics

## 2. Data storage layer

### HBase
It is a nosql database system with high reliability, high performance, column-oriented, scalability, and typical key/value distributed storage. It is mainly used for massive structured and semi-structured data storage. . It is between nosql and RDBMS. Data can only be retrieved through the row key and the range of the row key. Row data storage is atomic and only supports single row transactions (multiple table joins can be realized through hive support, etc.) Complex operation). HBase query data function is very simple, does not support complex operations such as join, does not support cross-row and cross-table transactions

### Kudu
It is a distributed database based on columnar storage between HDFS and HBase. Kudu support the real-time performance of HBase, the high throughput of HDFS, and the SQL support of traditional databases

### The HDFS
Its is a distributed file storage system has the characteristics of high fault-tolerant, high throughput, and high available. HDFS is very suitable for applications on large-scale data sets, provides high-throughput data access, and can be deployed on inexpensive machines. It relaxes the requirements of POSIX, so that it can achieve stream access (data in the file system. It mainly provides massive data storage services for various distributed computing frameworks such as Spark, MapReduce, etc., while the underlying data storage of HDFS and HBase also depends on HDFS

## 3. Data analysis layer

### Spark
Spark is a fast, versatile, scalable, fault-tolerant, memory iterative computing big data analysis engine. The current ecosystem mainly includes SparkRDD and SparkSQL for batch data processing, SparkStreaming and Structured-Streaming for stream data processing, Spark MLLib for machine learning, Graphx for graph computing, and SparkR for statistical analysis. Support Java, Scala, Python, R multiple data languages

### Flink
A great distributed big data processing(compute) engine can do calculations on limited data streams and wireless data streams. Flink was developed on the basis of streaming at the beginning of its design, and then entered the batch processing field. Compared with spark, it is a real-time computing engine in the true sense.

### Storm
It is a distributed real-time computing system managed by Apache after being open sourced by Twitter. Storm is a data stream processing computing engine without batch processing capabilities. Storm provides a low-level API. Users need to implement a lot of complex logic by themselves.

### Hive
It is a data warehouse tool depends on Hadoop. It can map structured data files to a database table and provide HQL statement (SQL-like language) query function. Storage depends on HDFS. Support multiple computing engines, such as Spark, MapReduce (default), Tez; support multiple storage formats, such as TextFile, SequenceFile, RCFile, ORC, Parquet (commonly used); support multiple compression formats, such as gzip, lzo, snappy (commonly used) ), bzip2

### Tez
Tez supports an open source computing framework for DAG operations. Compared with MapReduce, the performance is better, mainly because it describes the job as a DAG (directed acyclic graph), which is similar to Spark

### Pig
This application is based on Hadoop’s large-scale data analysis platform. It contains a scripting language called Pig Latin to describe data flow, an engine that executes data flow processing in parallel, and provides a simple operation and parallel computing for complex massive data. Programming interface. Pig Latin itself provides many traditional data operations, and allows users to develop some custom functions to read, process and write data. The language’s compiler will convert SQL-like data analysis requests into a series of optimized processing MapReduce operation

### Phoenix 
It is built on a SQL layer on HBase, allowing us to manipulate data in HBase through standard JDBC API. Completely ​​written in Java like JDBC driver embedded in HBase. It will generate standard JDBC result sets by transforming queries into HBase scans

## 4. OLAP Engine

### Druid
It is an open source, column-based, distributed, storage system suitable for real-time data analysis, capable of rapid aggregation, flexible filtering, millisecond-level queries and low-latency data import. By using Bitmap indexing to accelerate the query speed of column storage, and using the CONCISE algorithm to compress bitmap indexing, the generated segments are much smaller than the original text file, and the coupling between its various components is low. If real-time data is not required Real-time nodes can be completely ignored

### Kylin
It was originally developed by eBay Inc and contributed to the distributed analysis engine of the open source community. Provides SQL query interface and multidimensional analysis (OLAP) capabilities on Hadoop/Spark to support ultra-large-scale data, which can query huge Hive tables in sub-seconds. The user needs to have a deep understanding of the data warehouse model and build a cube. It can work with a variety of visualization tools so that users can use BI tools to analyze Hadoop data.

### Impala 
A big data query and analysis engine that provides high-performance, low-latency interactive SQL query functions for HDFS, HBase and other data is open sourced by Cloudera. It is based on Hive, uses Hive metadata to calculate in memory, and has the advantages of real-time, batch processing, high concurrency, etc.

### Presto’s
It is an open source distributed big data SQL query engine is suitable for interactive analysis and query. Data from multiple data sources can be merged, and data can be read directly from HDFS, without a lot of ETL operations.

## 5. Resource Management

### Yarn
Yarn is a resource scheduling platform, responsible for allocating resources and scheduling for computing programs, and does not participate in the internal work of user programs. Core components include ResourceManager (global resource manager, responsible for resource management and allocation of the entire system), NodeManager (resource and task manager on each node)

### Kubernetes,
It is also known as K8s, it is an open source platform for automated container operations that provides resource scheduling, deployment and operation, balanced disaster tolerance, service registration, capacity expansion and contraction, and other functions for containerized applications. It is specifically embodied in automated container deployment and replication, expansion or contraction of the container scale at any time, organization of containers into groups, and provision of load balancing among containers. Kubernetes supports docker and Rocket, and Docker can be regarded as a low-level component used internally by Kubernetes

### Mesos
It is similar to Yarn and is also a distributed resource management platform that runs in a unified resource management environment for MPI and Spark jobs. It supports Hadoop2.0.

## 6. Workflow Scheduler

### Oozie
It is a task scheduling framework based on workflow engine can provide scheduling and coordination of MapReduce and Pig tasks

### Azkaban
It is an open sourced by LinkedIn and is more lightweight than Oozie. Used to run a set of tasks in a specific order within a workflow, establish dependencies between tasks through a kv file format and provide users with an easy-to-use web interface to maintain and track the workflow of allowed tasks

## 7. Other

### Ambari
A web-based installation and deployment tool supports the management and monitoring of most Hadoop components, such as HDFS, MapReduce, Hive, Pig, HBase, etc.

### Zookeeper
It is a distributed coordination service is to provide coordination services for user’s distributed applications, such as master-slave coordination, dynamic online and offline server nodes, unified configuration management, distributed shared locks, etc. It is also a distributed program (deploy odd number of units, As long as more than half of the zookeeper nodes survive, the zookeeper cluster can provide services normally),an open source implementation of Google Chubby