This is a self-made resume written while studying the material for the **HCNA-BCCP Huawei Certified Network Associate-Building Cloud Computing Platform**

The official material can be found [here][a7c749f4]

  [a7c749f4]: http://support.huawei.com/learning/trainFaceDetailAction?lang=en&pbiPath=term1000025174&courseId=Node1000007639 "link to Huawei web"




## Certification Main Objetives

- Describe the basic concept and values of Cloud Computing
- Be familiar with the features and concept of virtual technologies
- Be familiar with the basic structure of Huawei Cloud Computing solution
- Describe the hardware structure of FusionCloud
- Be familiar with the software structure of FusionCloud
- Master the configuration of Huawei Cloud Computing hardware
- Master the configuration of Huawei Cloud Computing software
- Master the configuration of Huawei Cloud Computing service

## Index

  - OHC11081 Cloud Computing Concepts and Values
  - OHC11082 Virtualization Technology
  - OHC11083 Huawei FusionCloud Solutions
  - OHC11084 Huawei Cloud Computing Hardware System
  - OHC11085 FusionCompute Architecture
  - OHC11086 FusionManager Architecture Principles
  - OHC11087 FusionAccess Architecture Principles
  - OHC11088 FusionCloud Solution Deployment

# 1 Cloud Computing Concepts and Values
----------------------------------------------

Key characteristics of cloud computing are On-demand self-service, Location-independent resource pool (ubiquitous network access over the Internet), Pay per use, Elasticity.


Cloud computing is a Computing/Storage Network. It includes devices for data processing (servers), data storage and data communications (switches); and services for virtualization, scheduling and management, and the providing platform.

Other characteristics are low-cost servers, distributed software and automatic management.

Cloud computing is an integration of grid computing, distributed computing, parallel computing, network storage technologies, virtualization, load balancing, and other
traditional computer and network technologies.

Deployment methods: private (organizations), public (telecom carrier), community (shared infraestructure) and hybrid cloud.

##### Bussiness models:
  - infraestructure as a Service (IaaS).Processors, storage devices, networks.
  - Platform as a Service (PaaS). Application development platforms such as Java and .Net.
  - Software as a Service (SaaS). Applications wich run on cloud computing infraestructure. Such as CRM, ERP and OA.

##### Other concepts:
  - Web 1.0 is the idea of users obtaining in*formation through web browsers.
  - Web 2.0 works the idea of let the users be creators and authors on the internet.

##### Key technologies:
![Key technology](image1.jpeg)

- Servers, large memory and high [IOPS](https://en.wikipedia.org/wiki/IOPS).
- Storage devices, high IOPS, linked cloning, thin provisioning and snapshot functions.
- Switches, high-density and low-cost.
- VMs, virtualization software platform for resource pools.
- Distributed computing, scheduling and adjustment.
- Data center security.
- Management software, integrated and automatic.

Can be classified into three aspects: architecture, hardware, and software.
Architecture:
- Scale up (vertical expansion): Adds storage capacity to existing systems.
- Scale out (horizontal expansion): Adds nodes. Each node can provide storage, proccessing, and I/O bandwith.

Storage system:
- The distributed storage system consolidates low-cost and SATA hard disks on servers into storage resource pools.

Data center Networking:
- The service data flow (VMs) trend changes from vertical traffic to horizontal traffic.
- Development of [layer 2](https://en.wikipedia.org/wiki/Data_link_layer) network.

##### Benefits of cloud computing
The virtualization supports scalability of servers:
- Each server is virtualized into multiple VMs.
- VM specifications (CPU and memory) can be flexibly changed to increase or reduce the numbers of VM.
- Physical memory resources can be virtualized into more virtual memory resources.
- The expansion of servers can be implemented using the PXE or an ISO file.
- Cloud-based service systems employ batch VM deployment.
- - Resources can be deployed in large scale in short time.
- Resources can be dynamically expanded and shrunk.
- Less manual operations due to the automatic deployment.
- Deployments times changes from a month to minutes.

##### Data centralization for information security
- Data is transferred through HTTPS.
- System access requires certificates or accounts.
- Secure architecture and [VMM](https://en.wikipedia.org/wiki/Virtual_Machine_Manager) to isolate VMs from each other. Automatic security management.
- Trend Micro antivirus software.

##### Smart scheduling for energy saving
- Intelligent scheduling policies.
- Dynamic power management (DPM).

##### Reduced noise and power consumption
##### Efficient maintenance for cost reduction
##### Seamless switchover and mobile office
You can log in to the system desktop using various terminals at any time. The data and desktops uniformly run and are stored on the data center. The [Hot Swap](https://en.wikipedia.org/wiki/Hot_swapping) mode is supported for terminal replacement.

##### In-service upgrade and expansion
![upgrade](image2.jpeg)

##### Unified management
Huawei cloud solutions supports:
- The ability to manage physical servers, switches, and Huawei firewall devices (E1000 and E8000) in a unified manner.
- Mainstream servers and storage devices from other vendors.
- Both, Huawei Virtualization software FusionCompute and VMware.

##### cloud computing Application and examples
![cloud computing growth](image3.jpeg)

- Amazon EC2 supports VM leasing used in Linux and Windows, data processing, and storage leasing.
- Microsoft azure provides the VM development platform Visual Studio, which is based on Windows server and Linux systems.
- Alibaba cloud server, Elastic Compute Service (ECS).

##### Huawei Cloud Computing Solutions
Huawei FusionCloud solution is composed by four products:
  - FusionSphere. Cloud OS. Optimum cost effectiveness. Horizontal fusion.
  - FusionCube. Converged Appliance. Bussiness agility. Vertical Fusion.
  - FusionAccess. Desktop Cloud. Secure, efficient, user experience.
  - FusionInsight. Big data analysis. Easy-to-use, secure, reliable.

![Huawei desktop cloud case](image4.jpeg)

# 2 Virtualization technology
------------------------------------------------------
Virtualization converts "physical" resources into "logical" resources.
- Zoning. Multiple VMs can run on the same physical server.
- Isolation. VMs on the same server are isolated from each other.
- Encapsulation. Each VM is saved in a file. You can migrate and copy the file in order to migrate and copy the VM.
- Hardware-independence. VMs can run on any server without requiring any modifications on servers.

Concepts: Host machine(physical), guest machine (virtualized), Guest Os and Host OS, Hypervisor(VMM).

- Hosted virtualization: virtualization management software functions as a common application running on the underlying OS.
- Bare-metal virtualization: Hypervisor is a VM monitor that runs directly on physical hardware.
- OS-level virtualization: The host OS allocates hardware resources and separate virtual servers from each others.


Virtualization covers computing virtualization, storage virtualization, network virtualization.

#### Types of computing virtualization
- CPU virtualization: Multiple VMs share the same CPU. Sensitive instructions in VMs are intercepted, simulated and executed.
- Memory virtualization: Multiple VMs share the same physical memory and they need to be isolated from each other.
- I/O virtualization: Multiple VMs share the same physical device, such as a disk or a network adapter. Those I/O devices are multiplexed using time-division technology.

##### CPU virtualization
- VMs share the same CPU. Using timer interrupts, a mechanism similar to that used on raw OSs, instructions are trapped to the VMM upon triggering "interrupt" and are then scheduled based on the scheduling policy.
- Hypervisor get the instruction and put them into queue.
- An x86 processor has four priorities in protected mode, Ring 0 (for OS kernel), Ring 1 (OS Services), Ring 2 (OS services), and Ring 3 (applications).
- The typical virtualization approaches are privilege deprivileging and trap-and-emulation. Guest OSs run at a non-privileged level (deprivileging) whereas the VMM runs at the highest privilege level (full control of system resources).

##### Memory virtualization
![Memory virtualization](image4.jpeg)
The key point of memory virtualization lies in introducing a new layer of address space, that is, the physical address space of clients. Clients think that they run in the actual
physical address space; however, they access physical addresses through the VMM in fact.
The VMM saves the mapping table that records relationships between clients' address spaces and physical machines' address spaces.

##### I/O virtualization
The VMM intercepts the client OSs'access requests on devices and uses software to simulate itself as the actual device.

The front-end driver (blkfront) forwards data to the back-end driver (blkback) through the interfaces provided by the VMM.
Using the back-end driver, VMs'data is processed in a time-division multi-channel manner.

Discover a device:
- The device information about all VMs is saved on the XenStore of Domain0.
- The XenBus (a paravirtualization driver for Xen) on VMs communicates with the XenStore of Domain0 to obtainc device information.
- The front-end driver for the device is loaded.

Intercept device data:
- The front-end device forwards data completely to the back-end driver through the interfaces provided by the VMM.
- The back-end driver processes VM data on a time and channel basis.

#### Storage virtualization
Definition:
- Logical layer storage from physical storage devices.
- Admins adjust resources.
- Centralization of storage devices.

##### Raw Device + Logical Volume
- Storage devices (SAN or local disks) are mounted on hosts. Is the most direct control method. Raw devices are divided into blocks of 1Gb.
- Simple I/O paths and highest read & write peformance.
- No support for advanced services.


##### Storage Device Virtualization.
- Advanced storage functions such as thin provisioning, snapshot, and linked clone.
- Only for Huawei Advanced SAN and FusionStorage.


##### Host storage virtualization + File System
- Allows hosts to manage VM disk files through file system.
- Support for heterogeneous storeage devices and servers.
- Rich advanced functions, independent of hardware devices.
- Performance loss due to long I/O paths.

#### Network Virtualization

* A server can be virtualized into many hosts, meeting the inter-VM communication requirements.
* Dynamic migration of VMs.

##### Large Layer 2 Network and Technology
* Fiber Channel over Ethernet (FCoE) maps fiber channels (FCs) to Ethernet and inserts FC information to to Ethernet packets. Dedicated FCs are not necessary.
* FCoE transmit over the same cable LAN and FC SAN data.
* I/O integration maximizes return of investment (ROI).
* Data Center Bridging (DCB) build a losless Ethernet network.
* Both Ethernet and the FCoE protocol can run properly over Ethernet networks.


* SPB: Shosrtest Path Bridging
* TRILL: Transparent Interconnection of Lots of Links

Feature | SPB   | TRILL
--      |---    |--
Camp    |  Huawei, Avaya, HP, Ericsson and AL | Cisco, Huawei, Brocade, HP, IBM  
VM live migration  | supported  |  Supported
Multi-tenant      | 16 million  (24bit) | 4000 (12bit)
Convergence Speed  | Slow  | Fast
Compatibility  | Not supported   | Supported  (with existing switches)

##### Virtual switching
![Virtual switching](image6.jpeg)
* vSwitch (virtual switch) implements Layer 2 Ethernet switching
functions on servers **CPUs**, including VM switching, QoS control, and security isolation.
* eSwitch (embedded switch) implements Layer 2 Ethernet switching
functions on servers **network** adapters, including VM switching, QoS control, and security
isolation.

##### Huawei's network virtualization solution
* Implements a central management for distributed virtual switching using vSwitches or eSwitches.
* Supports large Layer 2 solutions provided by network devices.

#### VMs
* A VM has a built-in OS, which is specified by the administrator when delivering the instructions for creating VMs.
* I is also possible to use a ISO file to install an OS.

Example of the process:
![creating a VM](image7.jpeg)

# 3 Huawei FusionCloud Solutions
-------------------------------------------------
FusionCloud is the general brandname for Huawei cloud computing solution. It includes **FusionSphere** cloud operating system(OS), **FusionCube** converged appliance, **FusionAccess** desktop cloud and **FusionInsight** big data analysis.

### Huawei FusionSphere Solution
It includes the following modules:
* UltraVR: manages remote disaster recovery (DR).
* HyperDP: manages the backup implementing VM-level backup management.
* FusionCompute: virtualizes computing resources. VMs are created using FusionCompute.
* FusionStorage: virtualizes storage resources integrating local disks on generic servers, providing distributed [Server SAN](http://www.tomsitpro.com/articles/server-san-architecture-explained,2-768.html) capabilities.

![FusionSphere Version Overview](image8.jpeg)

The FusionSphere Operation Insight (SOI) implements advanced analysis on running systems. It collects and display VM performance indicators in the FusionSphere cloud system, models and analyzes collected data, and provides suggestions on system performance management. Displays indicators ins terms of health, risks, and efficiency.
Fusion Sphere SOI not only displays historical data, but also predicts future trends.

### Huawei FusionCube Solution
Fusioncube has three main features: converged, simple, and powerful.
**Converged** means that integrates computing, storage, network resources, virtualization platforms, databases, and application software.
The core of the FusionCube integration is the distributed cloud computing software (FusionCompute, FusionManager and FusionStorage).
![FusionSphere Version Overview](image8.jpeg)
**Simple** means that FusionCube supports resource sharing, and capacity expansion. The software and hardware are all Huawei-developed products.
The distributed cloud computing software virtualzes different hardware resources into a unified pool of virtual resources.
FusionCube supports linear and smooth expansion in capacity of blades, subracks and cabinets, which ensures uninterrupeted operation of upper-layer applications irrespective of changes in hardware.
**Powerful**. Software-defined storage architecture(FusionStorage) that eliminates I/O performance bottlenecks.
FusionStorage employs distributed server SAN architecture, high-speed IB networks and SSDs.
FusionCube can be used for desktop virtualization, Enterprise cloud data centers and Database acceleration.


### Huawei FusionAccess Solution
One FusionAccess can handle up to 20.000 virtual desktops.

# 4 Huawei Cloud Computing Hardware System
------------------------------------------------
#### Cloud Computing Hardware Overview
Huawei devices are compatible with mainstream servers and storage devices from vendors such as IBM, HP, and Dell.
It is composed by TCs on the user side; and on the data center side it has server, storage and network.
### servers
##### E9000 server
This blade server integrates elastic computing, storage, and networking resources.
It features reliability, availability and serviceability (RAS), high computing density, energy saving, high-midplane bandwith, intelligeent management and service, elastic configuration, flexible expansion for computing and storage resources, low latency, and network acceleration.

###### High-Performance compute mode:
* Supports full series of Intel x86 CPUs.
* Supports compute nodes of various specifications: 2-socket, 4-socket, half-width, and full-width compute nodes.
* Supports various network ports on mezz modules and acceleration cards.

###### Built-in Large-capacity storage:
* A half-width storage resource expansion module is integrated with half-width compute node to form a full-width compute node.
* Supports fifteen 2.5-inch Serial Attached SCSI (SAS) or Serial Advanced Technology Attachment (SATA) or Solid-state drives (SSDs). SCSI refers to Small Computer System Interface.
* Supports disk installation through removable drive trays and hot swap.
* Supports power-off protection for the write cache.

###### Hardware Overview
![E9000 Hardware Overview](image10.jpeg)
* 8 full-width comopute nodes or 16 half-width for flexible slot configuration.
* A half-width slot supports a compute node with two sockets and 24 DIMMS, or two sets two sets of two sockets and eight DIMMs.
* A full-width slot supports a compute node with four sockets and 48 DIMMs.
* A chasis provides the computing density of 64 processors or 768 cores with a maximum memory capacity of 12 TB.
* The maximum mid-plane switch capacity reaches 15.6 Tbit/s.
* Four switch modules (in two pairs) support Ethernet, fibre channel (FC), fibre channel over Ethernet (FCoE), and Infiniband(IB) swithching protocols and provide I/O ports on panels.

**E9000 Management Module**
The MM910 manages E9000 blade server chassis and compiles with IPMI v2.0 specifications. It provides functions including remote startup, shutdown, reset, logging, hardware monitoring, SOL, KVM over IP, virtual media, fanmonitoring, and PSU monitoring. It also supports 1+1 redundancy.
The MM910 provides local KVM ports for server management.
Each chassis is configured with two MM190s inactive/standby mode. They support active/standby swithover and hot swap.

**E9000 compute Nodes**
* CH121 half-width. 2x8-core E5-2690 CPU. 24 x DIMM, max of 768GB
* CH222 full-width. idem + 15x2.5-inch disks, suitable for big data and distributed processing.
* CH240 full-width. Four E5-4600 CPUs. 48 x DIMM, max of 1.5 TB. 8x2.5-inch disks suitable for database applications.
* CH240 full-width. Four E7-4800 CPUs. 32 X DIMM, max of 1.0 TB. 8x2.5-inch disks, max of 8 TB suitable for database applications.

**E9000 Switch Modules**
From 10GE to 40GE and 100GE. Each E9000 chassis provides 128 10GE upstream ports, and support various interfaces types, such as Ethernet, IB, and FC.
IB QDR/FDR and Infiniband quad data rate/fourteen data rate.
A transparent interconnection of lots of links (Trill) can meet random VM migration, non-blocking, low-delay data forwarding, multi-tenant, and large network scale.

**Mezz Modules on E9000 Compute Nodes**
The mezz module is used for I/O expansion and supports NICs and SAS cards.

##### RH2288H server
It supports HPC, databases, virtualization, basic enterprise applications, and telecommunication service applications.

### Storage devices
##### OceanStor 5600/5800 V3
* Supports 16Gbit/s FC and 10 Gbit/s FCoE host ports. Up to 40 GB/s of bandwith, 4 TB cache capacity, and 8 PB storage capacity.
* SAN and NAS converged to reduce total cost of ownership (TCO).
* Scabalability up to eight controllers.
* Storage 5600 V3 5800 V3 uses disk and controller separation architecture (3U independent engine).
* Controller module and BBUs support redundancy and provide high availability.
* Controller enclosures can be managed in a cascading manner.
* All ports use a modular design, facilitating replacement and upgrade.
* 4 U of 75 x 3.5-inch disks in a 5 row x 15 columns
* Disk enclosures connect to controller enclosures using Mini SAS HD cables or are cascaded to other disk enclosures to implement capacity eexpansion.

### Switches
##### S5700 Series GE Switch
* ESD: Electrostatic discharge jack
* Developed by Huawei based on versatile routing platform (VRP)
* dual power supply sockets and hardware-based Ethernet OAM.
* 10 GE uplink capacity.
* Energy Efficient Ethernet (EEE).
* S5700 supports intelligent stack (iStack).

##### S6700 high-density full-10GE box-type Switch
For long distance stack, a maximun of 40 Km and 48 ports in 1 U.

### TCs
Huawei can provide of different Thin Clients. Some TC can be hardened, such as forbidding use of USB flash drives.

### Typical Hardware Deployment Modes of Cloud Computing
* Typical virtualization configuration: E9000 (Half-width blade) + IP/FC SAN+GE /10GE switches, and software FusionCompute+FusionManager.
* Virtualization configuration: RH2288H + IP/FC SAN+GE/10GE switches.
* When FC SAN are used for networking, FC switches need to be added.

##### Standard desktop Cloud
E9000 + IPSAN + GPU(optional) + GE/10GE switches + TCs(optional), software FusionCompute + FusionManager + FusionAccess, and 5000 VMs in a cluster.

The standard desktop solution does not support automatic deployment and preinstallation.

GPU solution: Each full-width blade supports four Q2000 GPUs or four Q4000 GPUs. A 1.5 U blade supports four GPUs.

##### Desktop Cloud Appliances
* RH2288 + FusionStorage + GE/10GE switches + TCs(optional), and software FusionCompute + FusionManager + FusionAccess + FusionStorage.
The appliance supports automatic deployment and pre-installation and 3000 VMs in a cluster.
* E9000 (full-width) + FusionStorage + GE/10 GE switches + TCs (optional), and software FusionCompute + FusionManager + FusionAccess + FusionStorage.
The appliance supports automatic deployment and pre-installation and 3000 VMs in a
cluster.

# FusionCompute Architecture
----------------------------------------------------------
![FusionCompute](image11.jpeg)
* Resource virtualization virtualizes physical resources. For example, one 2.4 GHz CPU can be virtualized to three vCPUs with the specifications of 1.2 GHz, 0,8 GHz, and 0.4 GHz, respectively for three VMs.
* *FusionManager is cloud management* software.
* *FusionCompute virtualizes* x86 servers, storage and network devices into elastic IT resource pools.

#### FusionCompute Customer Values
##### Improving Resource utilization
Integration ratio: for example, 70 VMs are created on six blade servers, the integration ratio is 11:1 (round up 70/6).
##### Improving the availability
High availability (HA). This feature minimizes the downtime caused byt routine maintenance.
Fault Tolerance (FT) ensures an expected performance in the case of one or more failed components
#### FusionCompute System Architecture
* Virtual Resource Management (VRM)
* Virtual Node Agent (VNA)
* Management Interface, such as WebUI.
* Policy-based distributed resource management services.
* REST APIs are open source management interfaces for WebUI.
* Basic computing resource management services.
* Data service provides data access services.
* Connectivity services allows upper-layer management to gain access to underlying CNAs and databases.
* Databases uses Huawei-developed GaussDB database to store various management data.

##### Flexible and Scalable
* VRM is the FusionCompute management node, which is responsible for resource allocation
and scheduling, and provides unified O&M, resource monitoring, and resource management
functions.
* CNA implements virtualization.
  * Each logical cluster supports 128 physical servers.
  * Each logical cluster supports 3000 VMs.
  * HA design and VRM (on VMs or physical servers) deployed in active/standby mode ensure system availability.
  * Large-capacity design is used to cascade a max of 16 VRMs to support 4096 physical servers and 80,000 VMs.
* A pair of VRM nodes manages small-scale data centers to ensure thin provisioning. Large-scale data centers are managed by multiple cascaded VRMs.
* Two VRM nodes are promoted as the Primary Domain Coontroller (PDC). The web clients of all VRMs must be connected to the VRMs functioning as the PDC.

#### FusionCompute Features
**Compatibility with Special OSs in the industry**
Xen architecture and PV driver.
Huawei has paravirtualization (PV) driver developing capabilities, allowing FusionCompute to be compatible with new OSs.
FusionCompute is compatible with mainstream Windows and Linux OSs.
**Flexible VM Configuration Adjustment**
- Quality of Service (QoS) is used to measure transmission quality.
- The VM hot CPU and memory add functions must be supported by OSs. Therefore, FusionCompute does not support hot CPU and memory remove.
- FusionCompute supports online capacity expansion and disk reduction.
- Vertical scalability (scale-up): improves the VM resource configurations to provide better performance and QoS.
- Horizontal expansion (scale-out): adds nodes to improve the performance and Qos of the entire cluster.

**Memory Overcommitment, Increasing the VM Density by 50%**
* The memory over commitment function is configurable.

* Memory sharing and copy on write: The VMs sharing memory must run the same OS.
  * Memory sharing enables VMs to share the same physical memory space. In this case, the memory is read-only for these VMs.
  * Copy on write: If data must be written to the memory space, VMs create another memory space and modify the mapping.

* Memory swapping enables VM data that has not been accessed for a long time to be moved from the VM's memory space to a storage device, and the system creates a mapping for this movement path. The data is moved back to the
VM's memory space when the VM needs the data. The unused memory is swapped to the VM storage space. The large memory pages are supported in this technology.
* Memory balloon. The Hypervisor uses the memory bubble technology to release memory of idle VMs for VMs with a high memory usage to use.
* The balloon driver applies for an available memory page in the source VM, grants the page to the target VM according to the grant table, and updates the mapping between the physical addresses and VM machine addresses in the table.

**VM Live Migration**
* heterogeneous CPUs indicate different CPUs from the same vendor.¿?
* Memory compression technology is used to compress the memory data, reducing network bandwith.
* FusionCompute uses the zero-memory compression technology to store only copy of the zero-memory pages (which is simmilar to deduplication).

**VM HA** (High Availability)
FusionSphere 3.1 supports VM HA.
FusionSphere enhanced the HA mechanism by introducing VRM-independent HA. The enhancement enables a single node to be automatically elected as the master node when you create a HA cluster. The master node maintains management and
storage heartbeats with slave nodes. A loss of the heartbeat enables the master node to trigger VM HA. Management plane heartbeat is implemented by heartbeat packet transmission, and storage plane heartbeat is implemented by writing data to files. The loss of both management and storage heartbeats will trigger VM HA. Users can configure whether to use the management plane or non-management plane to detect storage heartbeats based on the network plane loads.
  * Limitation 1: The VRM-independent HA can be used only when all hosts in the cluster use Virtual Image Management System (VIMS) storage.
  * Limitation 2: To ensure reliability, a cluster that has VRM-independent HA enabled can accommodate a maximum of 32 hosts.

**FT** (Fault Tolerance)
Differences between FT and HA:
  * FT synchronizes data between the active and standby nodes in real time. Short time and High costs. Only applies to key systems with HA requirements.
  * HA uses the dynamic scheduling policy, which migrates the VM that is faulty to the destination host. Slower but low cost.

**Dynamic Resource Scheduling**
* Supports manual or automatic configuration of scheduling policies.
* The load balancing is implemented in a logical cluster.
* In Huawei server solution, a logical cluster includes 128 servers.
* If a performance load of all VMs in a cluster is lower than the scheduling baseline, the scheduling is not enabled, even if the load variance exceeds the threshold specified by users.

**Dynamic Power Management**
* DPM policies can be configured and DPM takes effect only when DRS is configuredd for the cluster. DRS is required to migrate VMs when the system executes the DPM policies.
* The thresholds ranging from coservative to radical indicate the energy-saving policies with different sensitivities.

**Fine-Grained  Resource Management of QoS, Ensuring VIP Service Availability**
* QoS is used to measure the transmission quality.
* The CPU QoS cannot temporarily add CPUs to a VM.
* The memory and network QoS mechanism are similar.

**Architecture of NUMA Affinity-based Scheduling**
* NUMA. Each physycal computer has multiple CPUs connected by a front side bus. The CPUs and the corresponding memory modules constitute a NUMA system.
* A CPU and its interconnected memory constitute a node.
* RAM. Random Access Memory.
* NUMA nodes are introduced in physical servers to improve memory access efficiency of CPUs. A CPU can achieve its maximun memory access efficieny when accesing memory within its own NUMA node. But, if any VM OS or applcation requires a second NUMA node, the overall performance will deteriorate. In this case, Guest NUMA, and enhanced NUMA feature, enables that the NUMA topology is transparently transmitted to the VM and enables VM to preferably use memory resources on one NUMA node, thereby improving memory performance.

**GPU Hardware Virtualization**
Technical Principle:
Multiple vGPUs are created on a physical GPU, which can use Direct Memory Access (DMA) to directly obtain the 3D commands delivered to the vGPU driver by graphics applications. After the GPU renders the graphics, it stores the graphics to the video RAM of each vGPU. Then the vGPU driver in the VMs can directly captuure rendering data from the physycal memory.

**Remote CD/DVD-ROM Driver Mounting**
A VM can read data of the CD-ROM drive attached to the host.

**Virtual Cluster File System - VIMS**
The Virtual Image Management System (VIMS) has the following features:
* Opensource OCFS2
* Manages the VM image and configuration files as files
* Uses jbd2 to record logs
* Uses distributed lock mechanism to ensure data read/write consistency
* Uses the disk heartbeat to detect the connection status with the SAN
* Uses the network heartbeat to detect the connection status between the nodes.

Thin provisioning: The allocated space is separated from the actual space.

**Storage Live Migration, preventing Service Downtime During Storage System Maintenance**
* Supports data migration between clusters.
* implements power-off maintenance for the storage system.
* Optimizes VM storage I/O performance.

**Storage Thin Provisioning, Dramatically Reducing Storage Investment**
* The disk space size a VM user can use is the configured space only. The space that can be allocated to a VM is adjustable based on actual usage.
* Supports storage reclamation.
* Reduces the storage cost up to 40%
* Large storage capacity and low IOPS requirements.
* Compared with common storage modes, thin provisioning allows a storage device to support more VMs. Therefore, the IOPS of a single VM reduces.

**Linked clone Technology, Improving Management Efficienci and Saving storage Space**
* Multiple linked clones can share one master disk which requires cache acceleration, and each linked clone must also have one delta disk. If multiple users share a master disk, the costs can be reduced. The size of a delta disk is about
1/3 that of the master disk. Therefore, the costs can be reduced by 60%.
* The test period is 12 seconds.

**RDM for Storage Resources**
* Raw Device Mapping (RDM) allows VMs to directly access a physical storage device.
* SCSI is a protocol to connect a host to a storage device, in a distance of 25 meters or shorter.
* Logical Unit Number(LUN) is a logical disk that comprises all or some physical disks on a SAN storage device.


**Support for VXLAN**
VXLAN adopts an outer User Datagram Protocol (UDP) tunnel as a data link layer
and transfers original data packets as tunnel payloads. With the outer UDP tunnel,
inner payload data can be quickly transferred on the layer 2 and layer 3 networks.
* New packet format: VXLAN outer encapsulation (tunnel) + Original inner payloads: Virtual network identifier (VNID) can be extended from 12 bits (4096) to 24 bits (16 million), and can be transmitted across the layer 2 network.
* Virtual tunnel end point (VTEP), a logical entity, is used for VXLAN packet encapsulation and decapsulation. It is assigned an IP address of the physical network to connect to the physical network.
* A VXLAN gateway is defined in the VXLAN network to implement communication between virtual networks and between virtual networks and physical networks.

**10GE Gateway for Key Applications and I/O-Demanding Scenarios**
Differente hardware devices support different technologies for VMs to communicate with external networks.
* Common vNIC
  * The hypervisor (dom0) implements network I/O between VMs in the same host, or VM's external data transmissions
* VMDq-enabled NIC
    * Huawei-developed intelligent network interface card (iNIC) supports the Virtual Machine Queues (VMDq) technology.
    * VMDq implements layer 2 classifier/sorter using hardware. Data packages are directly sent to NIC queues based on MAC addresses and VLAN information without passing through the domain 0.
* SR-IOV
  * This allows physical NIC to create multiple physical functions (PFs), each of which provides multiple virtual functions (VFs).
  * This feature allows a VM to exclusively use a VF which is derived from a PF. The VM can drectly use physical NIC without CPU overhead caused by virtual swithching.
  * Live migration and snapshot features are unavailable on SR-IOV.

#### FusionCompute specifications
![FusionSpecs](image12.jpeg)
![FusionSpecs](image13.jpeg)
![Fusionspecs](image14.jpeg)


As a mature open-source software product based on Xen, FusionCompute has made significant system simplification, security hardening, and function enhancement.
Therefore, it consumes little resources and can be installed on a server with only 8 GB memory (48 GB is recommended) and 16 GB hard disk space.

# FusionManager Architecture and Basic Principles
--------------------------------------------------
FusionManager resolves the preceding problems of Managing heterogeneous virtualization platforms, for example, Huawei's FusionCompute and VMware's vCenter.

Centrally managing physical devices, for example, monitoring servers, CPU temperatures, fans and receiving alarms.

Secure Network Isolation.

Allocating virtual resources.

Centrally manage multiple and independent data centers.

Introduction of the concept of VDC:
A VDC is the primary unit of virtual resources managed in the FusionManager system. Several VDCs can manage the all the virtual resources.
Each VDC can contain multiple users that are managed by the VDC admin, who can add or delete users to or from a VDC and configure each user.

### Core features

![FusionManager](image15.jpeg)

* FusionManager provides:

  * Resource pool management capability:
    * Managing heterogeneous virtualization platforms, for example, Huawei's FusionCompute and VMware's vCenter.
    * Centrally managing hardware, for example, physical servers from Huawei, HP, and Dell, storage devices (IP SAN and FusionCompute SAN), and network devices (switches and firewalls).
    * Centrally managing alarms reported by various Huawei components and hardware devices.

  * Multi-DC management:
    * Multi-tenant management capability.
    * Automatic application management capability. FusionManager supports application template creation and rapid provisioning of application templates.

### Multi-Tenant ¬ Multi-VDC management
A VDC is a unit of virtual resources assigned for tenants.

A tenant is called an account in industry, a project in OpenStack, or an org in VMware. Usually, a tenant is a independent user or an enterprise.

A VDC is a unit of virtual resources assigned for tenants.


### Secure and Isolated Network Environment Provided by a VPC

* Isolated environment: The VPC provides isolated VMs and network environments, meeting the requirements of isolating networks between various departments.

* Comprehensive services: Each VPC can provide the independent virtual firewalls, elastic IP addresses, virtual LBs, security groups, super VLANs, IPSec VPNs, and NAT gateway services. Some of these functions are provided using virtual service appliance (VSA).

* Flexible networking: The VPC provides multiple networking modes, such as direct network, routing network and internal network.

* Convenient charging method: FusionManager provides pay-per-use and traffic-based resource charging modes.

### Design Concepts
![Virtualization Hierarchy](image16.jpeg)

### Public vs Private Cloud Scenarios
In a public cloud scenario, FusionManager allows the system admin to build, manage, and perform maintenance for a cloud platform.

In a private is the same as public, but also allows to users to complete resource creation, resource management, and resource usage statistics.

### Administrator - Service & Operation Administrators
System Admins can be classified into the service administrtor and operation administrator.
* The service admin is responsible for service operation.
* The operation admin builds, manges, and performs maintenance for resource pools.

### Tenant/User/Quota
* A VDC is a unit of virtual resources assifned for tenants.
  * A tenant is called an account in industry, a project in OpenStack, or an org in VMware.
  * For example: Amazon is a well-known public cloud carrier. An individual customer or enterprise can register Amazon. In this case, the individual customer or enterprise is called a tenant.
* Quota restricts the amount of resource used by tenants.
* a user in FusionManager can play different roles in different VDCs, that is, a user can exist in multiple VDCs.

### Architecture Reference
FusionManager uses service-oriented Architecture (SOA) to support application delopment. The core components in SOA are described in the next picture:

![FusionManger Components](image17.jpeg)
* *Northbound*
  * FusionManager probides multiples northbound interfaces, including RESTful, SOAP, Java SDK, and SNMP interfaces.
* *Southbound*
  * FusionManager can monitor and manage heterogeneous hardware devices. FusionManager also provides drivers required for new hardware based on its extensive monitoring framework. Users can put drivers into use after hot loading these drivers on FusionManager.
  * FusionManager supports Huawei's FusionCompute and VMware's virtualization platforms using the drivers. FusionManager is planned to support Microsoft's Hyper-V soon.

## FusionManager Core Functions
The tree root is the menu name, and the modules below the  root are core functions.

![FusionManager Core Functions](image18.jpeg)

**Multi-DC Management**
* FusionManager can be deployed in Top-Local mode when managing multiple data centers. This mode is also called distributed deployment architecture.
* In this deployment mode, each Local FusionManager node manages the resources in a single data center. The Top FusionManger node itself uses the resources in the entire data center (by FusionSphere cascading on web client) to prvide tenants with services.
* the *Top FusionManager administrator* and *Local FusionManager administrator* are *service admin* and *operation admin*, respectively.

**Heterogeneus Virtual Resource Management**
FusionManager uses separate drivers for various virtualization platforms, such as VM, disk, and network management.

Huawei's FusionCompute virtualization uses REST interfaces to interact with drivers. VMware's vCenter uses VMware's SDK to interact with drivers.

A third party can also use FusionManager's open REST interfaces to perform secondary development.

**Hardware Device Management and Monitoring**
* FusionManager monitors and manages servers, network devices (such as switches, firewalls, and load balancers), and storage devices (such as IP SAN and FC SAN).
* New plug-ins can be developed for new hardware and be hot loaded to the system.
* Device alarms are sent to FusionManager using Simple Network Management Protocol (SNMP).
* Device maintenance operations are performed using Intelligent Platform Management Interface (IPMI) and SNMP protocols.

**VPC Management**
* Users can create their own VPCs in a VDC
* Users canuse various network services, such as routers and virtual load balancers (VLBs) in a VPC
* In tenant view, users can clearly view the VPC network topology, which facilitates VPC mintenance and management.
* The VPC security management functions are implemented on firewalls:
  * In hardware firewall networking, multiple virtual firewalls are created using the virtualization capability of the hardware firewall.
  * The software firewall is similar to the hardware firewall, but the hardware uses Huawei's software virtualization solution to virtualize software firewalls. Each software firewall runs on one VM.
* The router capability of the VPC is provided by firewalls or switches based on the actual physical networking.
