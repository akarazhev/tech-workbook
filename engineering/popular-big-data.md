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