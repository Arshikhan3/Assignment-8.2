# Assignment-8.2
● Explain the core changes made in Hadoop 2.x

Ans: Many changes are there in hadoop 2.x. They are as follows:
1.Single point of Failure - Each cluster has a single NameNode and if that machine is not available, whole cluster will be not available.It is rectified in hadoop 2.x

2.High Availability - If the NameNode process or machine fails, then the entire cluster will not be available until either the NameNode is rebooted or it is assigned and started on another machine. Any restarted NameNode is not available until it gets heartbeat messages from the data nodes with the block locations for all of the files on the data nodes. This can take hours for large clusters which results in decreased availability when there is an unexpected outage.
Hadoop 2 remedied this situation by adding support for HDFS high-availability (HA).
In this implementation there is a pair of namenodes in an active-standby configuration. In the event of the failure of the active namenode, the standby takes over its duties to continue servicing client requests without a significant interruption.

3.Nodes Limitation (4000 - to unlimited)
4.Allows other applications also to integrate with HDFS.
5.Decentralize JobTracker power to data-nodes. Entire job tracker architecture changed.
6.Map-reduce slots are changed static to dynamic.
7.Support both Interactive,graph iterative algorithms.

● Explain the difference between MapReduce 1 and MapReduce 2 / Yarn?

Ans: Hadoop 1.x                                                                             Hadoop 2.x
1. JobTracker keeps track of resource                                1. Resource Utilization is taken care by ResourceManager 
    utilization and job monitoring.                                     and NodeManager, whereas job monitoring is
                                                                        taken care by ApplicationMaster.

2. Suited for maximum of 4000                                        2. It can scale up to 10000 nodes
     nodes and 40000 tasks.                                             and 100000 tasks.


3. TaskTracker is configured with                                    3. Resources are dynamic and finegrained.
   static slots. Moreover, a map tasks                                   This leads to better cluster utilization.
   can not run on reduce slot. So cluster
   utilization is low.
                                                                                                                        
4. Supports only MapReduce                                            4. Supports processing models other
    processing model.                                                                     than Map Reduce.

