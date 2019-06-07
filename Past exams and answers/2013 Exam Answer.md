## 2013 Exam Answers

### Question 1

#### (1A)

**Grid Computing**: Grid computing is a processor architecture that combines computer (may be heterogeneous or hypogeneous) resources from various domains to reach a main objective. In grid computing, the computers on the network can work on a task together, thus functioning as a supercomputer.

网格计算是分布式计算的一种，也是一种与集群计算非常相关的技术。如果我们说某项工作是分布式的，那么，参与这项工作的一定不只是一台计算机，而是一个计算机网络，显然这种“蚂蚁搬山”的方式将具有很强的数据处理能力。网格计算的实质就是组合与共享资源并确保系统安全。

**Cluster Computing**: Clustered computing us when two or more computers serve a single resource. This improves performance and provides redunddancy; typically a collection of smaller computers strapped together with a collection of smaller computers strapped together with a high-speed local network.

计算机集群将一组松散集成的计算机软件或硬件连接起来高度紧密地协作完成计算工作。在某种意义上，他们可以被看作是一台计算机。集群系统中的单个计算机通常称为节点，通常通过局域网连接，但也有其它的可能连接方式。集群计算机通常用来改进单个计算机的计算速度和/或可靠性。一般情况下集群计算机比单个计算机，比如工作站或超级计算机性价比要高得多。

**Cloud Computing**: jargon term without a commonly accepted non-ambiguous definition, a synonym for distributed computing. There are 5 characteristics: On-demand self-service, Networked access, Resource pooling, Rapid elasticity, Measured service.

云计算是最新开始的新概念，它不只是计算等计算机概念，还有运营服务等概念了。它是分布式计算、并行计算和网格计算的发展，或者说是这些概念的商业实现。云计算不但包括分布式计算还包括分布式存储和分布式缓存。分布式存储又包括分布式文件存储和分布式数据存储。

**并行计算**：并行计算或称平行计算是相对于串行计算来说的。并行计算（Parallel Computing）是指同时使用多种计算资源解决计算问题的过程。为执行并行计算，计算资源应包括一台配有多处理机（并行处理）的计算机、一个与网络相连的计算机专有编号，或者两者结合使用。并行计算的主要目的是快速解决大型且复杂的计算问题。

**分布式计算**：分布式计算这个研究领域，主要研究分散系统（Distributed system）如何进行计算。分散系统是一组计算机，通过计算机网络相互链接与通信后形成的系统。把需要进行大量计算的工程数据分区成小块，由多台计算机分别计算，在上传运算结果后，将结果统一合并得出数据结论的科学。


#### (1B)

**Key Challenges of Large-scale distributed Systems**:

- Single point failure.
- General assumptions that typically do not hold in the real world.
- Dependene analysis is hard for core that uses pointers, recursion, ...;
- Loops can have unknown number of iterations
- Access to global resources (e.g. Shared variables)


### Question 2

#### (2A)

**Amdahl's law**: Amdahl's law is a formula which gives the theoretical speedup in latency of the execution of a task at fixed workload that can be expected of a system whose resources are improved.

If 95% of the program can be parallelized, the theoretical maximum speedup using parallel computing would be 20*, no matter how many processors are used.

<p align="center"><img src="./Pictures/amdahl2.png" width = "80%"/></p> 


**Challenges of its practical implementation**:
Limitations: Proportion of speed up depends on parts of program that can't be parallelised.

Challenges: MPI communication cost time.


Differences between two laws:

- Amdahl: 假设你要开60公里，你前一个小时只开了30公里(serial部分)，你后面30公里无论开多快(parallel部分)，你的平均速度都不可能到90公里/h

- Gaustafson: 我们不假设你到底要开多远，你前一个小时只开了30公里，只要你之后开的足够快(有足够多的时间和距离)，你总能达到平均90公里/h的速度

#### (2B)

**Actual performance of Edward cluster may vary**: ???

**How Edward cluster set up to minimize this**: ??? 

**What user can do to optimize their throughput of cluster**: ???

**Challenges on HPC facilities**: ???


### Question 3

#### (3A)

**Consequences of Brewer's CAP theorem on distributed databases**:

Brewer's CAP theorem: Consistency, Availability and Partition-Tolerance.

- Consistency: every client receiving an answer receives the same answer from all nodes in the cluster.

- Availability: every client receives an answer from any node in the cluster.

- Partition-Tolerance: the cluster keeps on operating when one or more nodes cannot communicate with the rest of the cluster.

<p align="center"><img src="./Pictures/CAP.jpg" width = "50%"/></p> 

### (3B)

**CAP theorem supported by non-SQL technology (CouchDB)**:

Availability and Partition-tolerance: Multi-Version Concurrency Control (MVCC)

**CAP theorem supported by relational（traditional) database technology (PostGreSQL)**:

Consistency and Availability: Two phase commit

**Advantage of MapReduce compared to other more traditional data processing**: ???

MapReduce Algorithms: 

- Map: Distributes data across machines
- Reduce: Summarize the mapped data until the result is obtained

Advantages: 

1. Scaling: can achieve scalability.
2. Lower cost: open source framework such as Hadoop is free.
3. Volume of data: large amount of data.
4. Types of data: can apply on semi-structured and unstructured data.

### Question 4

#### (4A)

**Compare and Contrast ReST and SOAP**

SOAP vs ReST  

- Two patterns to call services over HTTP
- SOAP WS is built upon the **Remote Procedure Call** paradigm
	- 过程远程调用(RPC): 是一个计算机通信协议。该协议允许运行于一台计算机的程序调用另一台计算机的子程序，而程序员无需额外地为这个交互作用编程。
- ReST is centered around resources, and the way they can be manipulated remotely.
- Actually **ReST is more of a style** to use HTTP than a separate protocol 
- **SOAP is a stack of protocols** that covers every aspect of using a remote service, from service discovery, to service description, to the actual request/response
- 简单来说，SOAP使用WSDL(仅支持XML), 请求中包含了谁调用的服务，需要哪些参数，需要什么数据结构被返回，所以相对比较复杂. ReST是一种更轻量的风格（不是协议），既可以用XML也可以用JSON进行数据交换，而且是基于ROA的，认为一切都是资源，使用ReSTful风格的API对资源进行请求和操作.


(LMS Discussion Board)

See the example of AURIN for SOA in lecture  - includes ReST services, Spatial Services, SOAP services etc etc. Rest provides a well defined interface (PUT, POST, GET etc) and whilst it doesn't have the equivalent of WSDL, the point is that a well defined Rest interface should not need it since you can discover, navigate and use the service without a specific WSDL-like interface to describe it. Rest abstracts from the inner workings of how systems are realised that address Core Ideas (Lecture 6, slide 5)

#### (4B)

**Differences on PUT and POST methods**

PUT: Update Resource, Idempotent

POST: Create Resource, Neither safe nor idempotent


### Question 5

#### (5A)
- **Virtual Machine Monitor/Hypervisor (VMM)**: The virtulisation layer between the underlying hardware and the VMs and guest operating systems it supports.

- **Full Virtualization**: allow an unmodified guest OS to run in isolation by simulating full hardware

- **Para-virtualization**: VMM/Hypervisor exposes special interface to guest OS for better performance. Requires a modified Guest OS

- **Shadow page tables**: VMM maintains shadow page tables in lock-step (锁步) with the page tables

- **Hardware virtualization and software virtualization differ in shadow page tables**: 

- **Advantages and disadvantages of virtual machines**: 

	Virtual machine: A representation of a real machine using hardware/software that can host a guest operating system.

	Advantages: 
		
	1. Can use multiple operating system environments on the same computer.
	2. Virtual machines can provide an instruction set architecture, or ISA, structure different than the actual computer. 
	3. When you create your virtual machine, you create a virtual hard disk. So, everything on that machine can crash, but if it does, it won’t affect the host machine.

	Disadvanages: 
	
	1. Virtual machines are less efficient than real machines because they access the hardware indirectly.  
	2. When several virtual machines are running on the same host, performance may be hindered if the computer it’s running on lacks sufficient power. 
	3. A virtual machine can be infected with the weaknesses of the host machine. 

- **Typical steps to support live migration of virtual machine**: 

	- Stage 0: Pre-Migration
	- Stage 1: Reservation
	- Stage 2: Iterative Pre-copy
	- Stage 3: Stop and copy
	- Stage 4: Commitment
	- Stage 5: Activation

### Question 6

#### (6A) 
- **single sign-on**: A property of access control of multiple related, yet independent, software systems. With this property, a user logs in with a single ID and password to gain access to any of several related systems.

- **public key infrastructure**: 公钥基础建设. PKI(CA)将⽤用户的个人身份跟公开密钥链接在一起

- **certification authority**: 证书颁发机构. Trusted authority whi issuing, revoking, stroing certificates.

- **registration authority**: 注册中⼼. Prove who you are to CA

- **identity provider**: A system entity that creates, maintains, and manages identity information for principals while providing authentication services to relying applications within a federation or distributed network.

#### (6B)

**Challenges in supporting fin-grained security in Cloud environment**:

**Authentication** 身份鉴定

**Authorisation** 授权

**Audit** 审计

**Confidentiality** 保密性

**Privacy** 隐私

**Fabric management** 组织管理理

**Trust** 信任

**Single sign-on**: 

1. The Grid model needed
2. Currently not solved for Cloud-based Iaas
3. Onus is non-Cloud developers to define this

**Auditing**: logging, intrusion detection, auditing of security in external computer facilities.

**Deletion**: 

1. data deletion with no direct hard disk
2. scale of data

**Liabiliry**

**Licensing**: 

1. many license models
2. challenges with the cloud delivery model

**Workflows**:

1. Many workflows tools for combing SoA services
2. Many workflows models.
3. Serious challenges of defining, enforcing, sharing, enacting
4. Security-oriented workflows

### Question 7

#### (7A) 

**Big Data challenges**:

- Volume (数据量量) 
- Velocity (速度) 
- Variety (多样性) 
- Veracity (准确性)


#### (7B)

**NeCTAR Research Cloud to tackle these big data challenges**:

NeCTAR Research Cloud (Infrastructure(底部结构) as a Service (IaaS)):

- Based on OpenStack
- Services: Compute service, Image service, Block storage service, object storage service
- Characteristics: 
	- On-demand self-service(随需⾃自动服务)
	- Broad network access (随时随地⽤用任何⽹网络存取)
	- Resource pooling (多⼈人共享资源池)
	- Rapid elasticity (快速重新部署灵活度)
	- Measured service (被监控与测量量的服务).






