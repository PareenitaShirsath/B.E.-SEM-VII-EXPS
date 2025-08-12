Prerequisites: - Java Development Kit (JDK) installed on your system - A compatible operating system (e.g., Ubuntu, CentOS) - Hadoop distribution (e.g., Apache Hadoop, Cloudera Hadoop) 
Step 1: Install Java 
1. Check if Java is already installed: java -version 
2. If not, install JDK: sudo apt-get install openjdk-8-jdk (for Ubuntu-based systems) 
Step 2: Download and Install Hadoop 
1. Download Hadoop from the official Apache Hadoop website: 
https://hadoop.apache.org/releases.html 
2. Extract the downloaded tarball: tar -xzvf hadoop-<version>.tar.gz 
3. Move the extracted folder to a suitable location: sudo mv hadoop-<version> /usr/local/hadoop 
Step 3: Configure Hadoop Environment Variables 
1. Set JAVA_HOME environment variable: export 
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64 
2. Set HADOOP_HOME environment variable: export HADOOP_HOME=/usr/local/hadoop 
3. Add Hadoop binaries to PATH: export 
PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin 
Step 4: Configure Hadoop Configuration Files 
1. Edit core-site.xml: sudo nano $HADOOP_HOME/etc/hadoop/core-site.xml - Add the following configuration: 
<configuration> 
<property> 
<name>fs.defaultFS</name> 
<value>hdfs://localhost:9000</value> 
</property> 
</configuration> 
2. Edit hdfs-site.xml: sudo nano $HADOOP_HOME/etc/hadoop/hdfs-site.xml - Add the following configuration: 
<configuration> 
<property> 
<name>dfs.replication</name> 
<value>1</value> 
</property> 
<property> 
<name>dfs.namenode.name.dir</name> 
<value>file:///usr/local/hadoop/hadoop_data/hdfs/namenode</value> 
</property> 
<property> 
<name>dfs.datanode.data.dir</name> 
<value>file:///usr/local/hadoop/hadoop_data/hdfs/datanode</value> 
</property> 
</configuration> 
Step 5: Format HDFS 
1. Format the HDFS file system: hdfs namenode -format 
Step 6: Start Hadoop Services 
1. Start the HDFS service: start-dfs.sh 
2. Start the YARN service: start-yarn.sh 
Step 7: Verify Hadoop Installation 
1. Check the HDFS file system: hdfs dfs -ls / 
2. Run a sample MapReduce job: hadoop jar 
$HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-<version>.jar 
wordcount /input /output 
Basic Hadoop Commands: - hdfs dfs -ls: List files and directories in HDFS - hdfs dfs -mkdir: Create a new directory in HDFS - hdfs dfs -put: Upload a file to HDFS - hdfs dfs -get: Download a file from HDFS - hadoop jar: Run a MapReduce job 
