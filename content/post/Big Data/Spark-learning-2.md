---
title: "Big Data Learning Day-2"
date: 2023-03-28T02:21:23+11:00
draft: false
---

# Introduction
After this article, I will record some experience of learning big data.




# Content
## 1. Spark core module

![Spark Module](https://raw.githubusercontent.com/JackyWang96/BlogSite/master/photos//Spark%20module.png)
 ****
- **Spark Core:**

The most basic and core functions of Spark are provided in Spark Core
 ****
- **Spark SQL:**

Spark SQL is the component that Spark uses to manipulate structured data. With Spark SQL, users can query data using SQL or the Apache Hive version of the SQL dialect (HQL).
 ****
- **Spark Streaming:**

Spark Streaming is a component on the Spark platform that performs stream computing for real-time data, and provides a rich API for processing data streams.

## 2. Spark running model

 ****
- **Local model:**

    An environment that executes Spark code locally without requiring any other node resources <br><br><br>

 ****
 
- **Standalone model:**

    Submit the application to the corresponding cluster for execution, using the cluster mode running on Spark's own nodes, which is what we call the standalone deployment (Standalone) mode.

    Online monitor: Use the Master resource to monitor the Web UI interface: http://linux1:8080

 ****

- **Yarn model:**

    The Yarn mode can utilize the resources of the Hadoop cluster, and the Spark application is submitted to the YARN cluster. Provides functions such as dynamic resource allocation and job recovery, suitable for large-scale production environments.

    The Standalone mode is more suitable for small-scale testing and development environments.

 ****

- **K8S & Mesos model:**

    Mesos is an open source distributed resource management framework under Apache. It is known as the kernel of a distributed system. It is widely used in Twitter and manages the application deployment on more than 300,000 Twitter servers.