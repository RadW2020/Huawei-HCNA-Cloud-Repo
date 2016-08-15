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

# Cloud Computing Concepts and Values
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

# Virtualization technology
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

# Huawei FusionCloud Solutions
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

## Huawei Cloud Computing Hardware System
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
* CH240 full-width. Four E7-4800 CPUs. 32 X DIMM, max of 1.0 TB. 8x2.5-inch disks, max of 8 TB suitablee for database applications.

**E9000 Switch Modules**
From 10GE to 40GE and 100GE. Each E9000 chassis provides 128 10GE upstream ports, and support various interfaces types, such as Ethernet, IB, and FC.
IB QDR/FDR and Infiniband quad data rate/fourteen data rate.
A transparent interconnection of lots of links (Trill) can meet random VM migration, non-blocking, low-delay data forwarding, multi-tenant, and large network scale.

**Mezz Modules on E9000 Compute Nodes**
The mezz module is used for I/O expansion and supports NICs and SAS cards.

##### RH2288H server
