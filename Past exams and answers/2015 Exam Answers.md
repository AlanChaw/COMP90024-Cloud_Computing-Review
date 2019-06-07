# 2015 Exam Answers
## Question 1   

**A) Erroneous assumptions in designing large-scale distributed systems**    

- The network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure
- Topology does not change
- There is one administrator
- Transport cost is zero
- The network is homogeneous
- Time is ubiquitous (普遍存在的)

**B) Cloud Computing systems do not solve many key challanges of large-scale DS, discuss**  

- Single point failure
- General assumptions that typically do not hold in the real world
- Dependene analysis is hard for core that uses pointers, recursion, ...;
- Loops can have unknown number of iterations
- Access to global resources (e.g. Shared variables)

## Question 2
**A) SOA**

	Principle | Chinese | Description
	:---- | :--- | :--- 
	Standardized service contract | 标准服务契约 | 服务要遵循一个服务描述
	Service loose coupling |  服务松耦合 | 服务之间的依赖要最小化
	Service abstraction | 服务抽象 | 服务将自己的业务逻辑封装起来，对外部世界是隐藏的
	Service reusability | 服务复用 | 业务逻辑切割成多个服务以实现复用的最大化
	Service autonomy | 服务自治 | 服务应该有对它们封装的逻辑的控制权
	Service statelessness | 服务无状态 | 理想情况下，服务应该是没有状态的
	Service discoverablity | 服务发现 | 服务可以被发现，通常通过一个接口注册
	Service composability | 服务组合 | 一个大问题可以被分割成很多小问题
	Service granularity | 服务粒度 | 选择合适的服务粒度
	Service normalization | 服务标准化
	Service optimization | 服务最优化
	Service relevance | 服务关联
	Service encapsulation | 服务封装 | 内部实现对用户是隐藏的
	Service location transparency | 服务地点透明 | 用户可以调用服务而无论服务的实际网络位置是什么



**B) Why and how Cloud infrastructures benefited from SOA** 

A Service-oriented Architecture can serve many goals:  

- **A set of externally facing services** that a business wants to provide to their customers or partners/collaborators
- **An architectural pattern** based on service providers, one or more brokers, and service requestors based on agreed service descriptions
- **A set of architectural principles**, patterns and criteria that support modularity, encapsulation, loose coupling, separation of concerns, reuse and composability
- **A programming model complete with standards**, tools and technologies that supports development and support of services (note that there can be many flavours of services)
- **A middleware solution optimized** for service assembly, orchestration, monitoring, and management. Can include tools and approaches that combine services together, e.g. as workflows.


## Question 3
**A) ReST based web services compared to SOAP based web services for implementing SoA**

SOAP vs ReST  

- Two patterns to call services over HTTP
- SOAP WS is built upon the **Remote Procedure Call** paradigm
	- 过程远程调用(RPC): 是一个计算机通信协议。该协议允许运行于一台计算机的程序调用另一台计算机的子程序，而程序员无需额外地为这个交互作用编程。
- ReST is centered around resources, and the way they can be manipulated remotely.
- Actually **ReST is more of a style** to use HTTP than a separate protocol 
- **SOAP is a stack of protocols** that covers every aspect of using a remote service, from service discovery, to service description, to the actual request/response
- 简单来说，SOAP使用WSDL(仅支持XML), 请求中包含了谁调用的服务，需要哪些参数，需要什么数据结构被返回，所以相对比较复杂. ReST是一种更轻量的风格（不是协议），既可以用XML也可以用JSON进行数据交换，而且是基于ROA的，认为一切都是资源，使用ReSTful风格的API对资源进行请求和操作.


**B) HTTP - Safe and Idempotent**

1. **Safe**: Do not change, repeating a call is equivalent to not making a call at all
2. **Safe example**: GET, OPTIONS, HEAD
3. **Idempotent**: Effect of repeating a call is equivalent to making a single call
4. **Idempotent example**: PUT (update), DELETE
5. **Neither safe nor Idempotent**: POST


## Question 4
**A)**

1. **HPC - Data parallelization**: 所谓数据级并行，是指处理器能同时运行多条数据。
2. **HPC - Compute parallelization**: 并行计算（英语：parallel computing）一般是指许多指令得以同时进行的计算模式。在同时进行的前提下，可以将计算的过程分解成小部分，之后以并发方式来加以解决。
3. **Wall-time**: 进程起止所耗墙上时钟时间，也叫real time. 进程从开始执行到完成，所经历的墙上时钟时间（实际时间）


**B) Commands of Edwards server (SPARTAN)**  
  
	#SBATCH --time=01:00:00  
	#SBATCH --nodes=1
	#SBATCH --ntasks=1
	#SBATCH --cpus-per-task=16

**C) why is the accuracy of the wall-time important to users**

CPU-time: 进程时间也称CPU时间，用以度量进程使用的中央处理器资源。  

- real < CPU  表明进程为计算密集型（CPU bound），利用多核处理器的并行执行优势
- real ≈ CPU  表明进程为计算密集型，未并行执行
- real > CPU  表明进程为I/O密集型 （I/O bound），多核并行执行优势并不明显


**D) Compute parallelization - *Task farming* and *single program multiple data*.**

- Task farming: like divide and conquer with **master doing both split and join operation**
- Single program multiple data: 
	- Commonly exploited model – Bioinformatics, MapReduce, ...
	- Each process executes the **same piece of code**, but on different parts of the data
	- Data is typically split among the available processors
	- Data splitting and analysis can be done in many ways


## Question 5
**A) Technical and non-technical issues for development and delivery of *security-oriented Clouds*.**  

1. Technical Challenges of Security
	- Authentication (身份鉴定?)
	- Authorisation (授权)
	- Audit/accounting (审计)
	- Confidentiality (保密性)
	- Privacy (隐私)
	- Fabric management (组织管理?)
	- Trust (信任)

2. Non-technical Challenges of Security
	- Grids and Clouds (IaaS) should allow users to compile codes that do stuff on physical/virtual machines
	- Should try to develop generic security solutions
	- Clouds should allow scenarios that stretch inter-organisational security

**B)**  

**a.** What is *federated authentication*, Advs and disadvs of Shibboleth for security.  

- Federated identity is related to single sign-on (SSO), in which a user's **single authentication ticket**, or token, is trusted across **multiple IT systems or even organizations**.
- 信息技术中的联合身份是将人的电子身份和属性联系起来的手段，存储在多个不同的身份管理系统中。 联合身份与单点登录相关，其中用户的单一身份验证票证或令牌在多个IT系统甚至组织中受信任. 


**b.** Why isn't Shibboleth used to access Cloud-based systems more generally?  


## Question 6
**A) Cloud based IaaS, PaaS, SaaS, and give examples**  

- IaaS: Infracture as a Service - AWS, Orical Public Cloud, Nectar
- PaaS: Platform as a Service - Google App Engine, Amazon Elastic MapReduce
- SaaS: Software as a Service - Gmail, Office 365

**B) Adv, disadvs of public, private, hybrid clouds**

- Private
	- Control, secure, consolidation of resources
	- Utility challange, management overhead(超支)
- Public
	- Utility computing, Can focus on core business, cost-effective
	- Security proble, loss of control, possible lock-in
- Hybrid (杂交)
	- use privae cloud, but burst into public cloud when needed
	- how to move data?, how to decide which data to be public?

**C) Challenges in delivering hybrid clouds**

- How do you move data/resources when needed?
- How to decide (in real time?) what data can go to public cloud?
- Is the public cloud compliant with PCI-DSS (Payment Card Industry – Data Security Standard)?


## Question 7 
**Applications can be deployed on Clouds by: Creations and deployment of virtual images (snapshots) . Or through scripting the installation and configuration of software applications.**

**a. benefits and drawbacks of the two approches**  

- Snapshot
	- Benefits: easy to create snapshot and copy the state of one VM to another, no need to write script, easy to operate when deploying small number of VMs
	- Drawbacks: Requires mass labor work when have hundreds of instances to deploy. Deploying complex cloud systems requires a lot of moving parts. Easy to forget what software you installed, and what steps you took to configure the system

- Automation
	- Benefits: Provides a record of what you did, Codifies knowledge about the system, Makes process repeatable and programmable
	- Drawbacks: Have to program and test the scripts mannually. More labor work when the cloud is small. 

**b. Mechanisms used to support these approaches. Refer to specific tools used to support these processes on the Nectar research cloud**

 - Snapshot: NeCTAR Cloud support image service that users can create their own snapshots or use exsisting snapshots of virtual images.
 - Automation: Ansible - An automation tool for configuring and managing computers. Finer grained set up and configuration of software packages

**c. Typical steps to support live migration of VM instances using a Cloud facility such as the Nectar Research Cloud**  

- Stage 0: **Pre-Migration** - Active VM on Host A
- Stage 1: **Reservation** - Initializa a container on the host B
- Stage 2: **Iterative Pre-copy** - Enable shadow paging, copy dirty pages in successive rounds
- Stage 3: **Stop and copy** - Suspend VM on host A, generate ARP to redirect traffic to host B, sync all remaining VM state to host B
- Stage 4: **Commitment** - VM state on host A is released
- Stage 5: **Activation** - VM starts on Host B, connects to local devices, resumes normal operation
