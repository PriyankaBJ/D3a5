# D3a5

1. Explain what is High availability of Namenode.

In Hadoop cluster HDFS is used to store big data.In HDFS NameNode is a master daemon.

The namenode holds all the metadata about the big data stored in hadoop file system.

In hadoop cluster if it had a single NameNode, and that machine or process became unavailable,

the entire cluster would be unavailable until the NameNode was either restarted or started on a separate machine.

When namenode fails to perform then in order to ensure high availability of data standby node becomes active.

The standby node then starts performing the job of namenode.

In this way the high availability of of namenode is ensured.


2. Explain what is check pointing and how it is useful.

Checkpointing is very important in order to maintain file system metadata in HDFS.

It’s required for efficient NameNode recovery and restart.The responsibility of  NameNode is storing the HDFS namespace. 

This includes directory tree, file permissions and the mapping of files to block IDs. It’s important that this metadata (

and all changes to it) are safe for stable storage.

The filesystem metadata is stored in two different constructs: the fsimage and the edit log. The fsimage

is a file that represents a point-in-time snapshot of the filesystem’s metadata. Checkpointing is a process that takes an

fsimage and edit log and compacts them into a new fsimage. This way, instead of replaying a potentially unbounded edit log,

the NameNode can load the final in-memory state directly from the fsimage. This is a far more efficient operation and reduces

NameNode startup time.

3. Explain what is HDFS federation.

The solution to expanding Hadoop clusters indefinitely is to federate the NameNode. Before Hadoop 2 entered the scene, 

Hadoop clusters had to live with the fact that NameNode placed limits on the degree to which they could scale. Few clusters were 

able to scale beyond 3,000 or 4,000 nodes.

