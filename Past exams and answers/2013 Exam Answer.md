## 2013 Exam Answers

### Question 1

#### (1A)

**Grid Computing**: Grid computing is a processor architecture that combines computer (may be heterogeneous or hypogeneous) resources from various domains to reach a main objective. In grid computing, the computers on the network can work on a task together, thus functioning as a supercomputer.

**Cluster Computing**: Clustered computing us when two or more computers serve a single resource. This improves performance and provides redunddancy; typically a collection of smaller computers strapped together with a collection of smaller computers strapped together with a high-speed local network.

**Cloud Computing**: jargon term without a commonly accepted non-ambiguous definition, a synonym for distributed computing. There are 5 characteristics: On-demand self-service, Networked access, Resource pooling, Rapid elasticity, Measured service.


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

**Challenges of its practical implementation**:
Limitations: Proportion of speed up depends on parts of program that can't be parallelised.

#### (2B)

**Actual performance of cluster may vary**: ???

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

### (3B)

**CAP theorem supported by non-SQL technology (CouchDB)**:

Availability and Partition-tolerance: Multi-Version Concurrency Control (MVCC)

**CAP theorem supported by relational database technology (PostGreSQL)**:

Consistency and Availability: Two phase commit

**Advantage of MapReduce compared to other more traditional data processing**: ???

MapReduce Algorithms: 

- Map: Distributes data across machines
- Reduce: Summarize the mapped data until the result is obtained

Advantages: 

1. Scaling: can achieve scalability.
2. Lower cost: open source framework such as Hadoop.
3. Volume of data: large amount of data.
4. Types of data: can apply on semi-structured and unstructured data.

### Question 4

#### (4A)

**Compare and Contrast ReST and SOAP**

- Two patterns to call services over HTTP
- SOAP WS is built upon the Remote Procedure Call paradigm
- ReST is centered around resources, and the way they can be manipulated remotely.
- ReST is a style to use HTTP instead of a protocol
- SOAP is a stack of protocols that covers every aspect of using a remote service, from service discovery

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
??? 
Advantages: Run on virtual hardware and have own OS kernels, Large storage
Disadvanages: Security depends on hypervisor, Slow startup time, 

- **Typical steps to support live migration of virtual machine**: Stage 0: Pre-Migration, Stage 1: Reservation, Stage 2: Iterative Pre-copy, Stage 3: Stop and copy, Stage 4: Commitment, Stage 5: Activation


### Question 6

#### (6A) 
- **single sign-on**: A property of access control of multiple related, yet independent, software systems. With this property, a user logs in with a single ID and password to gain access to any of several related systems.

- **public key infrastructure**: 公钥基础建设. PKI(CA)将⽤用户的个⼈人身份跟公开密钥链接在⼀一起

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
- Characteristics: On-demand self-service(随需⾃自动服务),  Broad network access (随时随地⽤用任何⽹网络存取), Resource pooling (多⼈人共享资源池), Rapid elasticity (快速重新部署灵活度), Measured service (被监控与测量量的服务).







