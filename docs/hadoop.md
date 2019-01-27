Study Hadoop

# Korean Books
- [빅데이터 - 하둡, 하이브로 시작하기](https://wikidocs.net/book/2203)

# Hadoop HW Requirements 
Hadoop HW requirements are related to job type as below

| HW | Job | 
| --- | --- |
| CPU | Query |
| Memory | Spark processing |
| Disk | Ingestion |

## NameNode 
### Heap memory
* Namespace object = file inodes + blocks (that point to block files on the DataNodes.)
* Approx. 150 bytes for a namespace object
    * 1GB Mem for 7M objects (=1GB/150b)(without RPC, etc.)
    * 0.14GB for 1M objects
    * 1GB Mem for 2M files
 
#### Apache Hadoop
* https://issues.apache.org/jira/browse/HADOOP-1687
    * File: 125 bytes
    * Directory: 155 bytes
    * Block: 184 bytes

#### HDP Hadoop2.3 ~ 2.6
* https://docs.hortonworks.com/HDPDocuments/HDP2/HDP-2.3.2/bk_installing_manually_book/content/ref-80953924-1cbf-4655-9953-1e744290a6c3.1.html
* https://docs.hortonworks.com/HDPDocuments/HDP2/HDP-2.6.5/bk_command-line-installation/content/configuring-namenode-heap-size.html
    * 1GB Mem. for 1M files
    * 26GB Mem. for 40-50M files
    * 59GB Mem. for 100-125M files
    * 104GB Mem. for 150-200M files

#### Cloudera CDH5.16.1, Hadoop2.6 
* https://www.cloudera.com/documentation/enterprise/5-16-x/topics/admin_nn_memory_config.html
    * 1GB for 1M blocks (1 kB for a block) in a conservative way (2 blocks for a file)
  

#### Trivial
* https://dzone.com/articles/hadoop-cluster-capacity-planning-of-name-node
    * 64GB for 100M files
    * 64GB for 5-50 nodes
    * 128GB for 50 ~ 1000 nodes