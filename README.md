# BIG-Data and Spark
Processing BigData with Spark


What is Spark

<p><a href="https://spark.apache.org/">Apache Spark</a> is an open source big data processing framework built around speed, ease of use, and sophisticated analytics. It was originally developed in 2009 in UC Berkeley&rsquo;s AMPLab, and open sourced in 2010 as an Apache project.</p>

<p>Spark has several advantages compared to other big data and MapReduce technologies like Hadoop and Storm.</p>

<p>First of all, Spark gives us a comprehensive, unified framework to manage big data processing requirements with a variety of data sets that are diverse in nature (text data, graph data etc) as well as the source of data (batch v. real-time streaming data).</p>

	<p>Spark enables applications in Hadoop clusters to run up to 100 times faster in memory and 10 times faster even when running on disk.</p>

<p>Spark lets you quickly write applications in Java, Scala, or Python. It comes with a built-in set of over 80 high-level operators. And you can use it interactively to query data within the shell.</p>

<p>In addition to Map and Reduce operations, it supports SQL queries, streaming data, machine learning and graph data processing. Developers can use these capabilities stand-alone or combine them to run in a single data pipeline use case.</p>

<p>In this first installment of Apache Spark article series, we&#39;ll look at what Spark is, how it compares with a typical MapReduce solution and how it provides a complete suite of tools for big data processing.</p>

<h2>Hadoop and Spark</h2>

<p>Hadoop as a big data processing technology has been around for 10 years and has proven to be the solution of choice for processing large data sets. MapReduce is a great solution for one-pass computations, but not very efficient for use cases that require multi-pass computations and algorithms. Each step in the data processing workflow has one Map phase and one Reduce phase and you&#39;ll need to convert any use case into MapReduce pattern to leverage this solution.</p>

<p>The Job output data between each step has to be stored in the distributed file system before the next step can begin. Hence, this approach tends to be slow due to replication &amp; disk storage. Also, Hadoop solutions typically include clusters that are hard to set up and manage. It also requires the integration of several tools for different big data use cases (like Mahout for Machine Learning and Storm for streaming data processing).</p>

<p>If you wanted to do something complicated, you would have to string together a series of MapReduce jobs and execute them in sequence. Each of those jobs was high-latency, and none could start until the previous job had finished completely.</p>

<p>Spark allows programmers to develop complex, multi-step data pipelines using directed acyclic graph&nbsp;(<a href="http://en.wikipedia.org/wiki/Directed_acyclic_graph">DAG</a>) pattern. It also supports in-memory data sharing across DAGs, so that different jobs can work with the same data.</p>

<p>Spark runs on top of existing Hadoop Distributed File System (<a href="http://wiki.apache.org/hadoop/HDFS">HDFS</a>) infrastructure to provide enhanced and additional functionality. It provides support for <a href="http://databricks.com/blog/2014/01/21/Spark-and-Hadoop.html">deploying Spark applications</a> in an existing Hadoop v1 cluster (with SIMR &ndash; Spark-Inside-MapReduce) or Hadoop v2 YARN cluster or even <a href="http://mesos.apache.org/">Apache Mesos</a>.</p>

<p>We should look at Spark as an alternative to Hadoop MapReduce rather than a replacement to Hadoop. It&rsquo;s not intended to replace Hadoop but to provide a comprehensive and unified solution to manage different big data use cases and requirements.</p>

<h2>Spark Features</h2>

<p>Spark takes MapReduce to the next level with less expensive shuffles in the data processing. With capabilities like in-memory data storage and near real-time processing, the performance can be several times faster than other big data technologies.</p>

<p>Spark also supports lazy evaluation of big data queries, which helps with optimization of the steps in data processing workflows. It provides a higher level API to improve developer productivity and a consistent architect model for big data solutions.</p>

<p>Spark holds intermediate results in memory rather than writing them to disk which is very useful especially when you need to work on the same dataset multiple times. It&rsquo;s designed to be an execution engine that works both in-memory and on-disk. Spark operators perform external operations when data does not fit in memory. Spark can be used for processing datasets that larger than the aggregate memory in a cluster.</p>

<p>Spark will attempt to store as much as data in memory and then will spill to disk. It can store part of a data set in memory and the remaining data on the disk. You have to look at your data and use cases to assess the memory requirements. With this in-memory data storage, Spark comes with performance advantage.</p>

<p>Other Spark features include:</p>

<ul>
	<li>Supports more than just Map and Reduce functions.</li>
	<li>Optimizes arbitrary operator graphs.</li>
	<li>Lazy evaluation of big data queries which helps with the optimization of the overall data processing workflow.</li>
	<li>Provides concise and consistent APIs in Scala, Java and Python.</li>
	<li>Offers interactive shell for Scala and Python. This is not available in Java yet.</li>
</ul>

<p>Spark is written in <a href="http://www.scala-lang.org/">Scala Programming Language</a> and runs on Java Virtual Machine (JVM) environment. It currently supports the following languages for developing applications using Spark:</p>

<ul>
	<li>Scala</li>
	<li>Java</li>
	<li>Python</li>
	<li>Clojure</li>
	<li>R</li>
</ul>

<h2>Spark Ecosystem</h2>

<p>Other than Spark Core API, there are additional libraries that are part of the Spark ecosystem and provide additional capabilities in Big Data analytics and Machine Learning areas.</p>

<p>These libraries include:</p>

<ul>
	<li><b>Spark Streaming:</b>

<ul>
		<li><a href="https://spark.apache.org/streaming/">Spark Streaming</a> can be used for processing the real-time streaming data. This is based on micro batch style of computing and processing. It uses the DStream which is basically a series of RDDs, to process the real-time data.</li>
 </ul>
	</li>
	<li><b>Spark SQL:</b>
<ul>
		<li><a href="https://spark.apache.org/sql/">Spark SQL</a> provides the capability to expose the Spark datasets over JDBC API and allow running the SQL like queries on Spark data using traditional BI and visualization tools. Spark SQL allows the users to ETL their data from different formats it&rsquo;s currently in (like JSON, Parquet, a Database), transform it, and expose it for ad-hoc querying.</li>
</ul>
	</li>
	<li><b>Spark MLlib: </b>
<ul>
		<li><a href="https://spark.apache.org/mllib/">MLlib</a> is Spark&rsquo;s scalable machine learning library consisting of common learning algorithms and utilities, including classification, regression, clustering, collaborative filtering, dimensionality reduction, as well as underlying optimization primitives.</li>
	</ul>
	</li>
	<li><b>Spark GraphX: </b>
	<ul>
		<li><a href="https://spark.apache.org/graphx/">GraphX</a> is the new (alpha) Spark API for graphs and graph-parallel computation. At a high level, GraphX extends the Spark RDD by introducing the Resilient Distributed Property Graph: a directed multi-graph with properties attached to each vertex and edge. To support graph computation, GraphX exposes a set of fundamental operators (e.g., subgraph, joinVertices, and aggregateMessages) as well as an optimized variant of the Pregel API. In addition, GraphX includes a growing collection of graph algorithms and builders to simplify graph analytics tasks.</li>
	</ul>
	</li>
</ul>

<p>Outside of these libraries, there are others like BlinkDB and Tachyon.</p>

<p><a href="http://blinkdb.org/">BlinkDB</a> is an approximate query engine and can be used for running interactive SQL queries on large volumes of data. It allows users to trade-off query accuracy for response time. It works on large data sets by running queries on data samples and presenting results annotated with meaningful error bars.</p>

<p><a href="http://tachyon-project.org/index.html">Tachyon</a> is a memory-centric distributed file system enabling reliable file sharing at memory-speed across cluster frameworks, such as Spark and MapReduce. It caches working set files in memory, thereby avoiding going to disk to load datasets that are frequently read. This enables different jobs/queries and frameworks to access cached files at memory speed.</p>

<p>And there are also integration adapters with other products like Cassandra (<a href="http://www.datastax.com/dev/blog/accessing-cassandra-from-spark-in-java">Spark Cassandra Connector</a>) and R (SparkR). With Cassandra Connector, you can use Spark to access data stored in a Cassandra database and perform data analytics on that data.</p>

<p>Following diagram (Figure 1) shows how these different libraries in Spark ecosystem are related to each other.</p>

<p><img _href="img://71.png" _p="true" alt="" src="https://cdn.infoq.com/statics_s2_20170711-0402/resource/articles/apache-spark-introduction/en/resources/71.png" style="width: 600px; height: 273px;" /></p>

<p><small><strong>Figure 1. Spark Framework Libraries</strong></small></p>

<p>We&#39;ll explore these libraries in future articles in this series.</p>

<h2>Spark Architecture</h2>

<p>Spark Architecture includes following three main components:</p>

<ul>
	<li>Data Storage</li>
	<li>API</li>
	<li>Management Framework</li>
</ul>

<p>Let&rsquo;s look at each of these components in more detail.</p>

<p><b>Data Storage:</b></p>

<p>Spark uses HDFS file system for data storage purposes. It works with any Hadoop compatible data source including HDFS, HBase, Cassandra, etc.</p>

<p><b>API:</b></p>

<p>The API provides the application developers to create Spark based applications using a standard API interface. Spark provides API for Scala, Java, and Python programming languages.</p>

<p>Following are the website links for the Spark API for each of these languages.</p>

<ul>
	<li><b><a href="http://spark.apache.org/docs/latest/api/scala/index.html#org.apache.spark.package">Scala API</a></b></li>
	<li><b><a href="http://spark.apache.org/docs/latest/api/java/index.html">Java</a></b></li>
	<li><b><a href="http://spark.apache.org/docs/latest/api/python/index.html">Python</a></b></li>
</ul>

<p><b>Resource Management:</b></p>

<p>Spark can be deployed as a Stand-alone server or it can be on a distributed computing framework like Mesos or YARN.</p>

<p>Figure 2 below shows these components of Spark architecture model.</p>

<p><img _href="img://2.png" _p="true" alt="" src="https://cdn.infoq.com/statics_s2_20170711-0402/resource/articles/apache-spark-introduction/en/resources/2.png" style="width: 600px; height: 311px;" /></p>

<p><small><strong>Figure 2. Spark Architecture</strong></small></p>

<h2>Resilient Distributed Datasets</h2>

<p><a href="https://spark.apache.org/docs/latest/programming-guide.html#resilient-distributed-datasets-rdds">Resilient Distributed Dataset</a> (based on Matei&rsquo;s <a href="https://www.cs.berkeley.edu/~matei/papers/2012/nsdi_spark.pdf">research paper</a>) or RDD is the core concept in Spark framework. Think about RDD as a table in a database. It can hold any type of data. Spark stores data in RDD on different partitions.</p>

<p>They help with rearranging the computations and optimizing the data processing.</p>

<p>They are also fault tolerance because an RDD know how to recreate and recompute the datasets.</p>

<p>RDDs are immutable. You can modify an RDD with a transformation but the transformation returns you a new RDD whereas the original RDD remains the same.</p>

<p>RDD supports two types of operations:</p>

<ul>
	<li>Transformation</li>
	<li>Action</li>
</ul>

<p><b>Transformation:</b> <a href="https://spark.apache.org/docs/latest/programming-guide.html#transformations">Transformations</a> don&#39;t return a single value, they return a new RDD. Nothing gets evaluated when you call a Transformation function, it just takes an RDD and return a new RDD.</p>

<p>Some of the Transformation functions are<code> </code><tt>map, filter, flatMap, groupByKey, reduceByKey, aggregateByKey, pipe, and coalesce.</tt></p>

<p><b>Action:</b> <a href="https://spark.apache.org/docs/latest/programming-guide.html#actions">Action</a> operation evaluates and returns a new value. When an Action function is called on a RDD object, all the data processing queries are computed at that time and the result value is returned.</p>

<p>Some of the Action operations are <code>reduce, collect, count, first, take, countByKey, and foreach</code>.</p>

<h2>How to Install Spark</h2>

<p>There are few different to install and use Spark. You can install it on your machine as a stand-alone framework or use one of Spark Virtual Machine (VM) images available from vendors like <a href="http://www.cloudera.com/content/support/en/downloads/quickstart_vms/cdh-5-1-x.html">Cloudera</a>, HortonWorks, or MapR. Or you can also use Spark installed and configured in the cloud (like <a href="http://databricks.com/product">Databricks Cloud</a>).</p>

<p>In this article, we&rsquo;ll install Spark as a stand-alone framework and launch it locally. Spark 1.2.0 version was released recently. We&rsquo;ll use this version for sample application code demonstration.</p>

<h2>How to Run Spark</h2>

<p>When you install Spark on the local machine or use a Cloud based installation, there are few different modes you can connect to Spark engine.</p>

<p>The following table shows the Master URL parameter for the different modes of running Spark.</p>

<p><span style="line-height: 1.2;"><img _href="img://23.png" _p="true" alt="" src="https://cdn.infoq.com/statics_s2_20170711-0402/resource/articles/apache-spark-introduction/en/resources/23.png" style="width: 600px; height: 354px;" /></span></p>

<h2>How to Interact with Spark</h2>

<p>Once Spark is up and running, you can connect to it using the Spark shell for interactive data analysis. Spark Shell is available in both Scala and Python languages. Java doesn&rsquo;t support an interactive shell yet, so this feature is currently not available in Java.</p>

<p>You use the commands <code>spark-shell.cmd and pyspark.cmd</code> to run Spark Shell using Scala and Python respectively.</p>

<h2>Spark Web Console</h2>

<p>When Spark is running in any mode, you can view the Spark job results and other statistics by accessing Spark Web Console via the following URL:</p>

<p><code>http://localhost:4040</code></p>

<p>Spark Console is shown in Figure 3 below with tabs for Stages, Storage, Environment, and Executors.</p>

<p><small><strong>(Click on the image to enlarge it)</strong></small></p>

<p><a _href="resource://4.png" href="https://cdn.infoq.com/statics_s2_20170711-0402/resource/articles/apache-spark-introduction/en/resources/4.png"><img _href="img://4-b.png" _p="true" alt="" src="https://cdn.infoq.com/statics_s2_20170711-0402/resource/articles/apache-spark-introduction/en/resources/4-b.png" style="width: 600px; height: 219px;" /></a></p>

<p><small><strong>Figure 3. Spark Web Console</strong></small></p>

<h2>Shared Variables</h2>

<p>Spark provides two types of shared variables to make it efficient to run the Spark programs in a cluster. These are Broadcast Variables and Accumulators.</p>

<p><b>Broadcast Variables:</b> Broadcast variables allow to keep read-only variable cached on each machine instead of sending a copy of it with tasks. They can be used to give the nodes in the cluster copies of large input datasets more efficiently.</p>

<p>Following code snippet shows how to use the broadcast variables.</p>

<pre>
<code class="language-nolanguage">//
// Broadcast Variables
//
val broadcastVar = sc.broadcast(Array(1, 2, 3))
broadcastVar.value
</code></pre>

<p><b>Accumulators:</b> Accumulators are only added using an associative operation and can therefore be efficiently supported in parallel. They can be used to implement counters (as in MapReduce) or sums. Tasks running on the cluster can add to an accumulator variable using the add method. However, they cannot read its value. Only the driver program can read the accumulator&#39;s value.</p>

<p>The code snippet below shows how to use Accumulator shared variable:</p>

<pre>
<code class="language-nolanguage">//
// Accumulators
//

val accum = sc.accumulator(0, "My Accumulator")

sc.parallelize(Array(1, 2, 3, 4)).foreach(x =&gt; accum += x)

accum.value
</code></pre>

<h2>Sample Spark Application</h2>

<p>The sample application I cover in this article is a simple Word Count application. This is the same example one would cover when they are learning Big Data processing with Hadoop. We&rsquo;ll perform some data analytics queries on a text file. The text file and the data set in this example are small, but same Spark queries can be used for large size data sets, without any modifications in the code.</p>

<p>To keep the discussion simple, we&rsquo;ll use the Spark Scala Shell.</p>

<p>First, let&rsquo;s look at how to install Spark on your local machine.</p>

<p><b>Pre-Requisites:</b></p>

<ul>
	<li>You will need Java Development Kit (JDK) installed for Spark to work locally. This is covered in Step 1 below.</li>
	<li>You will also need to install Spark software on your laptop. The instructions on how to do this are covered in the Step 2 below.</li>
</ul>

<p><b>Note:</b> These instructions are for Windows environment. If you are using a different operating system environment, you&#39;ll need to modify the system variables and directory paths to match your environment.</p>

<p><b>I. INSTALL JDK:</b></p>

<p>1) Download JDK from Oracle website.<a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html"> JDK version 1.7</a> is recommended.</p>

<p>Install JDK in a directory name without spaces. For Windows users, install JDK in a folder like <code>c:\dev</code>, not in &quot;<code>c:\Program Files</code>&quot;. &quot;<code>Program Files</code>&quot; directory has a space in the name and this causes problems when software is installed in this folder.</p>

<p><b>NOTE:</b> <b>DO NOT INSTALL</b> JDK or Spark Software (described in Step 2) in &quot;<code>c:\Program Files</code>&quot; directory.</p>

<p>2) After installing JDK, verify it was installed correctly by navigating to &quot;bin&quot; folder under JDK 1.7 directory and typing the following command:</p>

<p><code>java -version</code></p>

<p>If JDK is installed correctly, the above command would display the Java version.</p>

<p><b>II. INSTALL SPARK SOFTWARE:</b></p>

<p>Download the latest Spark version from <a href="https://spark.apache.org/downloads.html">Spark website</a>. Latest version at the time of publication of this article is Spark 1.2. You can choose a specific Spark installation depending on the Hadoop version. I downloaded Spark for Hadoop 2.4 or later, and the file name is <code>spark-1.2.0-bin-hadoop2.4.tgz</code>.</p>

<p>Unzip the installation file to a local directory (For example, c:\dev).</p>

<p>To verify Spark installation, navigate to spark directory and launch Spark Shell using the following commands. This is for Windows. If you are using Linux or Mac OS, please edit the commands to work on your OS.</p>

<pre>
<code class="language-nolanguage">c:
cd c:\dev\spark-1.2.0-bin-hadoop2.4
bin\spark-shell
</code></pre>

<p>If Spark was installed correctly, you should the see the following messages in the output on the console.</p>

<pre>
<code class="language-nolanguage">….
15/07/17 23:17:46 INFO HttpServer: Starting HTTP Server
15/07/17 23:17:46 INFO Utils: Successfully started service 'HTTP class server' on port 58132.
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /___/ .__/\_,_/_/ /_/\_\   version 2.0.0
      /_/

Using Scala version 2.10.4 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0)
Type in expressions to have them evaluated.
Type :help for more information.
….
15/07/17 23:17:53 INFO BlockManagerMaster: Registered BlockManager
15/07/17 23:17:53 INFO SparkILoop: Created spark context..
Spark context available as sc.
</code></pre>

<p>You can type the following commands to check if Spark Shell is working correctly.</p>

<p><code>sc.version</code></p>

<p>(or)</p>

<p><code>sc.appName</code></p>

<p>After this step, you can exit the Spark Shell window by typing the following command:</p>

<p><code>:quit</code></p>

<p>To launch Spark Python Shell, you need to have Python installed on your machine. You can download and install <a href="http://continuum.io/downloads">Anaconda</a>&nbsp;which is a free Python distribution and includes several popular Python packages for science, math, engineering, and data analysis.</p>

<p>Then you can run the following commands:</p>

<pre>
<code class="language-nolanguage">c:
cd c:\dev\spark-2.0.0-bin-hadoop2.4
bin\pyspark
</code></pre>

<h2>Word Count Application</h2>

<p>Once you have Spark installed and have it up and running, you can run the data analytics queries using Spark API.</p>

<p>These are simple commands to read the data from a text file and process it. We&rsquo;ll look at advanced use cases of using Spark framework in the future articles in this series.</p>

<p>First, let&rsquo;s use Spark API to run the popular Word Count example. Open a new Spark Scala Shell if you don&rsquo;t already have it running. Here are the commands for this example.</p>

<pre>
<code class="language-nolanguage">import org.apache.spark.SparkContext
import org.apache.spark.SparkContext._
 
val txtFile = "README.md"
val txtData = sc.textFile(txtFile)
txtData.cache()
</code></pre>

<p>We call the cache function to store the RDD created in the above step in the cache, so Spark doesn&rsquo;t have to compute it every time we use it for further data queries. Note that cache() is a lazy operation. Spark doesn&rsquo;t immediately store the data in memory when we call cache. It actually takes place when an action is called on an RDD.</p>

<p>Now, we can call the count function to see how many lines are there in the text file.</p>

<p><code>txtData.count()</code></p>

<p>Now, we can run the following commands to perform the word count. The count shows up next to each word in the text file.</p>

<pre>
<code class="language-nolanguage">val wcData = txtData.flatMap(l =&gt; l.split(" ")).map(word =&gt; (word, 1)).reduceByKey(_ + _)

wcData.collect().foreach(println)
</code></pre>

<p>If you want to look at more code examples of using Spark Core API, checkout <a href="http://spark.apache.org/docs/latest/programming-guide.html">Spark documentation</a> on their website.</p>
