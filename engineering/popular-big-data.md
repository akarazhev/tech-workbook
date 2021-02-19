# Popular Open Source Big Data Technologies (by Andy Grove)

## Apache Arrow
Apache Arrow is a cross-language development platform for in-memory data. It specifies a standardized language-independent 
columnar memory format for flat and hierarchical data, organized for efficient analytic operations on modern hardware. 
It also provides computational libraries and zero-copy streaming messaging and interprocess communication. 
Languages currently supported include C, C++, Go, Java, JavaScript, Python, Ruby, and Rust.

In my opinion, the great promise of Apache Arrow is that it will be possible for multiple platforms and languages 
to interoperate efficiently without the need to copy or serialize data into different formats.

## Apache Beam
Apache Beam Provides a single programming model for both batch and streaming use cases. 
It is essentially an abstraction layer that allows jobs to be executed on different runtimes. 
It is supported by Apache Apex, Apache Flink, Apache Gearpump, Apache Spark, Apache Samza, and Google Dataflow.

## Apache Drill
Apache Drill is a distributed query engine that is particularly good at executing SQL against schema-less data.

## Apache Flink
Apache Flink is a framework and distributed processing engine for stateful computations over unbounded and bounded data streams. 
Flink has been designed to run in all common cluster environments, perform computations at in-memory speed and at any scale.

Apache Flink is JVM based and supports Java and Scala. It appears to overlap heavily with the streaming features of 
Apache Spark.

## Apache Gearpump (Incubating)
Apache Gearpump is a real-time big data streaming engine. Different to other streaming engines, Gearpump’s engine is 
event/message based.

## Apache Hadoop
Hadoop is one of the most overloaded and misused terms in the industry. It seems to cover many projects. 
At the core of Hadoop though is the Hadoop Distributed File System (HDFS). 
Think of this as a poor man’s S3 that can be run in your data center or on your laptop.

Hadoop also provides a resource manager called YARN and a distributed data processing framework called MapReduce that 
runs on YARN. Hadoop was industry changing at the time but is now largely superceded by other technologies, in my opinion.

## Apache Hive
Apache Hive is a data warehouse software project built on top of Apache Hadoop for providing data query and analysis. 
Hive gives an SQL-like interface to query data stored in various databases and file systems that integrate with Hadoop.

Apache Hive also introduced some components that are leveraged by other open source projects:

Hive Metastore is a component for storing meta data about data sources. This is used in Apache Spark and PrestoDB.
Hive Server is a standalone server that uses the Thrift protocol to allow clients to execute queries against a Hive warehouse. 
There is a Hive JDBC driver too. Apache Spark has a Spark SQL Thift Server component that embeds a Hive Server in 
a Spark context to support interactive queries.

## Apache Kudu
Apache Kudu is a columnar distributed database that supports fast reads and writes. It supports key lookups, range scans, 
and simple predicates. It does not support SQL directly.

## Apache Impala
Apache Impala provides low latency and high concurrency for BI/analytic queries on Hadoop (not delivered by batch 
frameworks such as Apache Hive). Impala also scales linearly, even in multitenant environments.

## Apache Spark
Apache Spark allows distributed queries to be executed on a cluster. It is implemented in Scala but supports other 
languages as well.

Pros:
- Relatively easy to learn (as long as you know Java or ideally Scala already)
- Writing functional code in Scala + Spark can be quite elegant
- Easy to have custom code executed as part of a distributed job
- Excellent SQL support
- Advanced query optimizer
- Supports both batch and stream use cases

Cons:
- Non deterministic use of memory (largely due to the nature of JVM and garbage collection)
- Large overhead in query planning / code generation phase makes it perform badly for small interactive queries
- Largely row-based internally rather than columnar
- Many related projects are quite flaky and cause headaches in production e.g. Spark Jobserver, Spark SQL Thrift Server

## Apache Parquet
Apache Parquet is a columnar storage format available to any project in the Hadoop ecosystem, 
regardless of the choice of data processing framework, data model or programming language.

## Apache Storm
Apache Storm makes it easy to reliably process unbounded streams of data, doing for realtime processing what Hadoop 
did for batch processing.

In my opinion, Storm is a low level framework rather than a platform. It is also quite dated. I would recommend looking 
at Flink or Spark instead.

# Notable non-Apache Projects

## Dremio
Dremio is an elastic compute platform built on Apache Arrow with an advanced query optimizer. It looks very interesting.

## PrestoDB
PrestoDB is a distributed cluster for performing read-only queries against HDFS data sources. It leverages 
the Hive Metastore from Apache Hive.

## RAPIDS
The RAPIDS suite of open source software libraries gives you the freedom to execute end-to-end data science and 
analytics pipelines entirely on GPUs. It relies on NVIDIA® CUDA® primitives for low-level compute optimization, 
but exposes that GPU parallelism and high-bandwidth memory speed through user-friendly Python interfaces.

# Big data & open source platform management, cluster management and monitoring systems

## Clodera Manager
A web-based application for deploying and managing CDH clusters developed by Cloudera. 
It has functions such as automatic cluster installation, centralized management, cluster monitoring, 
and alarms which greatly saves cluster deployment time moreover it reduces operation and maintenance costs. 
It greatly improves the efficiency of cluster management, but the problem is that it is not an open source version.

## Hue
Hue is a Hadoop UI system (Hadoop User Experience) contributed by Cloudera to the open source community. 
Hue is based on the Python Web framework Django and evolved from Cloudera Desktop.

A browser based graphical system, quickly develop and debug various applications in the ecosystem of Hadoop. 
Using Hue, you can interact with the Hadoop cluster on the browser specific web console to analyze and process data, 
such as operating data on HDFS, running MapReduce Job, Hue also gives the ability to execute Hive SQL statements, 
browsing HBase database, running Sqoop and writing Oozie workflow. 
Its visual analysis is particularly special for big data analysis and development on the Hadoop platform.

## Apache Ambari
Hortonworks contributed the Ambari as a Hadoop platform management software to the Apache Foundation. 
The basic functions of this framework are as follows

1. Installation
2. Management
3. Operation
4. Maintenance of Hadoop components
5. Web UI for visual cluster management

All the above features simplifies the installation and use of the big data platform.

## Dr.Elephant
It is a tool for proper performance monitoring and tuning of Hadoop and Spark based tasks. 
It was open sourced by the LinkedIn team in 2016 and has been used in the company for 2 years before going open source. 
Dr.Elephant automatically collect and analyze the metrics of the task, and then display them in a simple and elegant way. 
The design idea of ​​Dr.Elephant is to guide developers to optimize their jobs through the results of job analysis, 
thereby improving developer efficiency and cluster resource utilization.

## Ganglia
This software framework initiated by UC Berkeley later it becomes the open source tool, 
it is design for cluster monitoring specially for measuring thousands of nodes. 
The major components of Ganglia includes gmond, gmetad, and a web front end. 
Ganglia mostly used to monitor system performance, CPU, memory, hard disk utilization and operation, I/O load, and network traffic. 
In Ganglia, you easily watch the working status of each node through the curve, 
and you can adjust and allocate system parameters to improve the overall system performance.

## Zabbix
Zabbix is ​​an open source distributed enterprise-level monitoring solution based on a web interface. 
After released in 2004, Zabbix maintained and updated by the Alexei Vladishev team, and supported by Zabbix SIA. 
Zabbix with help C/S mode collects data and B/S mode help out data display and configuration for the web. 
Zabbix has the ability to monitor millions of indicators collected from thousands of servers, virtual machines and network devices in real time.

Zabbix provides the following features

1. Monitor various network parameters
2. Ensure the safe operation of the server system
3. Flexible notification mechanism
4. Quickly to locate various problems

You can also use Zabbix to store the data of reports, real-time graphical data and achieve 7x24-hour centralized monitoring of the monitoring host.

## Apache Eagle
Eagle mainly includes high scalability, high scalability, low latency, dynamic coordination and other features, supports real-time monitoring of data behavior, 
It can immediately detect access to sensitive data or malicious operations, and immediately take countermeasures. 
Apache Eagle provides a set of efficient distributed streaming strategy engine with real-time, scalability, easy expansion, and friendly interaction. 
It integrates machine learning to specific user behavior and provides real time protection of big data in the Hadoop ecosystem.