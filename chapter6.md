# Partitioned Datasets

Partition-Based Dataset is an abstraction layer on top of the Apache Ignite storage and computational capabilities that allow us to build algorithms in accordance with zero ETL and fault tolerance principles.

A main idea behind the partition-based datasets is the classic MapReduce approach implemented using the Compute Grid in Ignite.

The most important advantage of MapReduce is the ability to perform computations on data distributed across the cluster without involving significant data transfers over the network. This idea is adopted in the partition-based datasets in the following way:



1. Every dataset is spread across partitions;
2. Partitions hold a persistent training context and recoverable training data stored locally on every node;
3. Computations needed to be performed on a dataset splits on Map operations which executes on every partition and Reduce operations which reduces results of Map operations to one final result.

**Training Context \(Partition Context\) **is a persistent part of the partition which is kept in an Apache Ignite, so that all changes made in this part will be consistently maintained until a partition-based dataset is closed. Training context survives node failures but requires additional time to read and write, so it should be used only when it's not possible to use partition data.

**Training Data \(Partition Data\)** is a part of the partition that can be recovered from the upstream data and context at any time. Because of this, it is not necessary to maintain partition data in some persistent storage, so that partition data is kept on every node in local storage \(On-Heap, Off-Heap or even in GPU memory\) and in case of node failure is recovered from upstream data and context on another node.



> _Why have partitions been selected as dataset and learning building blocks instead of cluster nodes?_



One of the fundamental ideas of an Apache Ignite is that partitions are atomic, which means that they cannot be split between multiple nodes \(see this page for more details\). As a result in the case of rebalancing or node failure, a partition will be recovered on another node with the same data it contained on the previous node.

In case of a machine learning algorithm, it's vital​ because most of the ML algorithms are iterative and require some context maintained between iterations. This context cannot be split or merged and should be maintained in a consistent state during the whole learning process.

