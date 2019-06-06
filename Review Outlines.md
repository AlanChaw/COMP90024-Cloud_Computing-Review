# Review Outlines
## Week 1 - History of Cloud Computing and Grid Computing  
1. Cloud Characteristics
	- On-demand (按需) self-service  
	- Networked access  
	- Resource pooling  
	- Rapid elasticity  
	- Measured service
2. Flavours
	- Compute clouds  
	- Data clouds  
	- Application clouds  
	- balabala clouds, etc..  
3. Brief history  
	1)  once had detailed standards  
	2) then had open distributed processing with slightly less strict and compliance(顺从的？) demands  
	3) Mid-90s: **Transparency** and **Heterogeneity**（异质）of computer interactions. Forcus on **computer-computer interaction**.  

4. Grid Computing  
**Grid computing is a processor architecture that combines computer (may be heterogeneous or hypogeneous) resources from various domains to reach a main objective.** In grid computing, the computers on the network can work on a task together, thus functioning as a supercomputer.

## Week 2 - Domain Drivers  
1. Problem
	- More and more data, databases  
	- Distributed, completely heterogeneous data  
	- Data is messy
2. Solution: Cluster and Cloud Computing.  
	Where is Domain drivers computing??????  F\*\*K Richard.  

3. Domain-driven design (From wiki)
Domain-driven design (DDD) is an approach to software development for complex needs by connecting the implementation to an evolving model.  
领域驱动设计是一种通过将实现连接到持续进化的模型来满足复杂需求的软件开发方法.  

## Week 3 - Overview of Distributed and Parallel Computing Systems  
1. Compute Scaling
	- Vertical Computational Scaling (Faster processors)
	- Horizontal Computational Scaling (More processors): Easy to add more, but hard to design and develop. 
	
2. Approaches for Parallelism
	- **Explicit**(明确的) vs **Implicit**(含蓄的) parallelism
		- **Implicit**: Supported by parallel languages and parallelizing compliers. Hard to do.
		- **Explicit**: The programmer is responsible for most of the parallelization effor. Consider SPARTAN.
	- Hardware  
	- Operating System
	- Software / Applications
	- Some or all of those
	
3. Design Stages of Parallel Programs (很像map-reduce?)
	- Partitioning(分割)
	- Communication
	- Agglomeration(聚集)
	- Mapping / Scheduling
	
4. **Erroneous Assumptions of Distributed Systems**
	- The network is reliable  
	- Latency is zero  
	- Bandwidth is infinite
	- The network is secure
	- Topology does not change
	- There is one administrator
	- Transport cost is zero
	- The network is homogeneous
	- Time is ubiquitous(普遍存在的)
	
5. **Challenges with Distribution**
	- Single point failure.
	- General assumptions that typically do not hold in the real world.
	- Dependene analysis is hard for core that uses pointers, recursion, ...;
	- Loops can have unknown number of iterations
	- Access to global resources (e.g. Shared variables)  
	
6. Parallelisation Paradigms(范例)
	- Master Worker/Slave Model
	- Single-Program, Multiple-Data
	- Data Pipelining
	- Divide and Conquer
	- Speculative(投机的) Parallelism 
	- Parametric Computation  

## Week 4 - Spartan HPC System
1. HPC:  
High-performance computing (HPC) is any computer system whose architecture allows for above average performance. A system that is one of the most powerful in the world, but is poorly designed, could be a "supercomputer".

2. Clustered Computing:   
Clustered computing is when two or more computers serve a single resource.  

3. HPC Cluster Design: 
![HPC_Cluster](./Pictures/HPC_cluster.jpg)  

4. Use Spartan:  
	1) Logging in  
	2) Submitting and Running jobs with scripts
5. Shared Memory vs. Distributed Memory
	- Multi-threads: Shared Memory
	- MPI: Distrubuted Memory Parallel Programming

## Week 5 - Cloud Computing, NeCTAR, Ansible, Git
1. The Most Common Cloud Models
	- Deployment Models
		- Private
			- Control, secure, consolidation of resources
			- Utility challange, management overhead(超支)
		- Public
			- Utility computing, Can focus on core business, cost-effective
			- Security proble, loss of control, possible lock-in
		- Community
		- Hybrid (杂交)
			- use privae cloud, but burst into public cloud when needed
			- how to move data?, how to decide which data to be public?
	- Delivery(交付) Models
		- Software as a Service (SaaS)
			- Gmail, office 365...
		- Platform as a Service (PaaS)
			- Google App Engine, Amazon Elastic MapReduce
		- Infrastructure(底部结构) as a Service (IaaS) (primary focus of this course)
			- AWS, Orical Public Cloud, Nectar...  

	![Delivery_models](./Pictures/Delivery_models.jpg)  
	
2. Essential Characteristics (Same as week 1)
	- On-demand self-service (随需自动服务）
	- Broad network access (随时随地用任何网络存取)
	- Resource pooling (多人共享资源池)
	- Rapid elasticity (快速重新部署灵活度)
	- Measured service (被监控与测量的服务)  

3. NeCTAR Research Cloud
	- Based on OpenStack
	- Services
		- Compute service, Image service, Block storage service, object storage service ...

4. Automation (Ansible, specifically)
	- Deploying complex cloud systems requires a lot of moving parts
	- Automation provides a record of what you did
	- Codifies knowledge about the system
	- Makes provess repeatable and programmable

5. Ansible
	- Easy to learn: Playbooks in YAML, templates in Jinja2, sequential execution.
	- Minimal requirements: Single command to install, uses ssh to connect to target machine
	- Repeatable
	- Extensible
	- Supports push or pull
	- Rolling updates
	- Intentory management (存货管理？)

6. Git
	- Distributed (decentralized) version-control system. 
	- Keep tracking changes
	- Revert to a specific checking point
	- Work with people

## Week 6 - Web Services, ReST Services, Twitter, Docker and Containerisation
1. SoA (Service-oriented Architectures)  
	When components are distributed, they have to interact in more loosely-coupled ways instead communicate directly.
	
2. SoA Core ideas
	- A set of externally facing services
	- An architectural pattern based on service providers
	- A set of architectural principles, patterns and criteria
	- A programming model complete with standards, tools and technologies
	- A middleware solution optimized for service assembly, orchestration, monitoring, and management

3. SoA Design Principles  

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

4. SoA for the Web: Web Services
	- Web services used to implement service-oriented architectures
	- Web服务是一种服务导向架构的技术，通过标准的Web协议提供服务，目的是保证不同平台的应用服务可以互操作 (from wiki)
	- Two main flavours
		- SOAP-based web services (Simple Object Access Protocol - 简单对象访问协议, 数据交换的协议规范, 交换带结构信息)
		- ReST-based web services (Representational State Transfer - 表现层状态转移, 资源在网络中以某种表现形式进行状态转移)
	- Both use HTTP, hence can run over the web

5. SOAP vs ReST
	- Two patterns to call services over HTTP
	- SOAP WS is built upon the **Remote Procedure Call** paradigm
		- 过程远程调用(RPC): 是一个计算机通信协议。该协议允许运行于一台计算机的程序调用另一台计算机的子程序，而程序员无需额外地为这个交互作用编程。
	- ReST is centered around resources, and the way they can be manipulated remotely.
	- **ReST is a style** to use HTTP instead of a protocol
	- **SOAP is a stack of protocols** that covers every aspect of using a remote service, from service discovery, balabala...

6. WSDL - Web Services Description Language (Web 服务描述语言)
	- An XML-based interface description language that describes the functionality offered by a web service.
	- WSDL provides a **machine-readable** description.
		- How the service can be called
		- what parameters it expects
		- what results/data structures it returns

7. Resource-Oriented Architecture (ROA)
	- ROA is a way of turning a problem into a ReSTful web service
		- Everything in ReST is considered as resource
		- Client requests resources through URL, an URL is a resource
		- Use POST，GET，PUT，DELETE orperations to create, retrieve, update, and delete resource, use uniform interface
	- Procedure
		- Client requests resource through URL
		- Server sends representation of resource
		- This puts the client in a certain state
		- Representation contains URLs allowing navigation
		- Client follows URL to fetch another resource
		- This transitions client into another state

8. ReST best practices
	- Keep your URLs short
	- URLs should be opaque (不透明的) ids that are meant to be discovered by following hyperlinks, not by client
	- Use nouns, not verbs
	- Make all GETs side-effect free to make request safe
	- Use links in your responses to requets, the response itself contains info about what's the next step to take
	- Minimize the use of query strings
	- Use HTTP status codes to convey errors/success

9. ReST principles
	- Addressability (可寻址能力)
	- Uniform Interface
	- Resources and Representations instead of RPC (Remote Procedure Call Protocol - 过程远程调用， C/S架构)
		- RPC need to expose the availables functions, but ReSTful systems no need to learn about functions, just find resources by following links from other resources
	- HATEOAS (Hypermedia as the Engine of Application State - 超媒体作为应用状态的引擎)
		- Resources representations contain links to identified resources
		- Making resources **Navigatable**

10. HTTP Methods
	- HTTP methods can be
		- Safe
		- Idempotent (幂等, 幂等是指重复调用多次操作和进行一次操作的结果是一致的)
		- Neither
	- Safe methods
		- Do not change, repeating a call is equivalent to not making a call at all
	- Idempotent methods
		- Effect of repeating a call is equivalent to making a single call
	- GET, OPTIONS, HEAD - Safe
	- PUT, DELETE - Idempotent
	- POST - Neither safe nor idempotent

11. ReST 2.0
	- Motivation
		- Everything as a service (EaaS)
		- Vast number of entities and services
		- Link services together to create workflows and mashups (混搭)
	- Solution
		- Extend API notation from mainly desktop applications to web apps and mobile platforms
		- Create API hubs that aim to facilitate the sharing and usage of services

12. Containerisation
	- Similar concept of resource **isolation** and **allocation** as a VM
	- Without bundling the entire hardware env. and full OS
	- Containerization allows **virtual instances** to share a single host OS to reduce these wasted resources (drivers, binaries, libraries), since each container only holds the application and related binaries. The rest are shared among the containers.
	- Virtualization vs Containerization  

		Virtualization | Containerization 
		:---- | :--- 
		Run on virtual hardware, have own OS kernels | Share same OS kernel
		Communication through Ethernet devices | IPC mechanisms (pipes, sockets)
		Security depends on hypervisor | Security requires close scrutiny (监视)
		A bit slow performance | near native performance
		File systems and libraries are not shared | File systems can be shared, libraries are shared
		Slow startup time | fast startup time
		Large storage | Small storage
		
13. Docker (Container Orchestration tool)
	- Docker is currently the leading software container platform
	- Container: a process behaves like an independent machine
	- Image: a blueprint for a container
	- Dockerfile: the recipe to create an image

