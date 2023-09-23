# Deployment

## Cloud Solution Components and Migration


### **1) Subscription Services**


-   The conversation begins by discussing subscription services, which
    are crucial in working with public cloud models and Software as a
    Service (SaaS) offerings.

-   A subscription service is a licensing model where you pay on a
    regular schedule, but you do not own the product; it\'s like a
    long-term or open-ended rental of resources.

-   Payments may also be based on your usage level, meaning the more you
    use, the more you pay.

-   While the subscription is active, you have access to the product,
    but if you stop paying once the regular payments expire, you lose
    access.

-   Public cloud service providers predominantly use subscription
    services for most of their offerings.

Examples of Subscription Services:

1.  **File Subscription Services**:

    -   Examples include Dropbox, AWS S3, Microsoft OneDrive, and Apple
        iCloud.

    -   Amazon Drive is another service in this category.

2.  **Communication Subscription Services**:

    -   These include email, Voice over IP (VoIP), Zoom, SMS, Microsoft
        Teams, Google Meet, and other video conferencing software.

3.  **Collaboration Software**:

    -   Examples encompass Amazon WorkDocs, Atlassian products like Jira
        and Confluence, Microsoft Office 365 (O365), and Google
        WorkSpaces.

4.  **Virtual Desktop Infrastructure (VDI)**:

    -   AWS WorkSpaces allows you to run desktop operating systems in a
        virtual capacity.

    -   Windows Virtual Desktop is another service in this category.

5.  **Directory Services and Identity Providers**:

    -   Examples include Microsoft Azure Active Directory (AD) and AWS
        Directory Services.

### **2) Cloud Resource Deployment**

Introduction to Different Types of Cloud Resources:

-   In this introduction, we\'ll explore various types of resources that
    can be deployed within a cloud ecosystem, with the understanding
    that deeper dives into each resource type will follow.

1.  **Compute Resources**:

    -   Compute resources are familiar to technology professionals and
        include various CPU architectures.

    -   Common CPU vendors like AMD, Intel, and Apple M1 are available.

    -   Vendor-specific CPUs like AWS Gravitron (ARM64 architecture) may
        also be used.

    -   Compute resources are measured by the number of virtual CPUs,
        which equate to thread count on a processor core.

    -   More virtual CPUs mean greater compute power and higher memory
        capacity.

2.  **Storage for Compute Resources**:

    -   AWS provides direct attached storage known as \"instance
        storage.\"

    -   Block storage options like Elastic Block Store (EBS) are
        available, presented over the network but appearing as local
        block devices.

3.  **Networking with Compute Resources**:

    -   Compute resources have network interfaces, including primary and
        secondary ones.

    -   Different interface types offer varying throughput and latency.

4.  **Cloud VM Deployment**:

    - An OS template contains resource allocation, OS image and configuration.
    - A solution template contains the complete infrastructure. 
    - Managed Templates are managed by the CSP after deployment. 

5.  **Cloud Resource Deployment - Storage**:
                        
    1.  Block Storage
        -   Block storage is thick provisioned (you pay based on the amount of provisioned) and requires a compute resource to access.
        -   One compute resource can access multiple block volumes.
        -   VMs are individual compute resources, each with its block
            storage.
        -   Multiple compute resources usually cannot connect to a single
            block volume simultaneously.
    2. File Storage
       -   File storage offers shared file systems, a step up from block
        storage.

       -   It can be thick or thin provisioned, much larger and accessed by multiple
        clients concurrently. 
    
    
    3. Object storage 
        -   Object storage follows a write-once-read-many (WORM) model.

       -   Objects can be deleted or overwritten but not edited in line.

       -   It\'s accessible using URLs and supports multiple client access
        methods.


6.  **Cloud Resource Deployment - Network**:

    -   Segmented networks for workload isolation can be deployed.

    -   Stateful or stateless firewalls, like AWS security groups or
        network ACLs, control traffic flow to applications.

    -   Load balancers and web application firewalls can be used for
        application decoupling and filtering requests.

    -   Content Delivery Networks (CDNs) enable caching and asset
        delivery without frequent origin data requests.

    -   Virtual Private Networks (VPNs) facilitate private network
        connectivity from corporate data centers to cloud-deployed
        networks.



### **3) Cloud Resource Types**

1.  **Compute Services**:

    -   Beyond virtual machines, compute services encompass various
        resource types that enable code execution.

    -   This category includes containerization and other means for
        running code.

2.  **Storage Services**:

    -   Storage is not limited to the basic types discussed earlier; it
        also includes specialized storage services.

3.  **Database Services**:

    -   Database services represent another resource type, offering
        options like relational databases, data warehouses, and various
        types of NoSQL databases.

4.  **Network Services**:

    -   Network services extend beyond the virtual private cloud (VPC)
        concept, encompassing load balancing, DNS management, content
        delivery, and more.

5.  **Serverless Services**:

    -   Serverless computing doesn\'t mean there are no servers; rather,
        it signifies that customers are not responsible for managing the
        underlying compute resources.

    -   Service providers handle all management, allowing users to focus
        solely on resource utilization.

6.  **Container Services**:

    -   Container services are a subset of compute services,
        facilitating the deployment of containers.

    -   Containers can be used for persistent or batch-driven
        applications.

7.  **Auto Scaling**:

    -   Auto scaling is a common implementation pattern across compute,
        storage, and database technologies.

    -   It involves automatically adjusting resources to match workload
        demands, optimizing performance and cost-efficiency.

### **4) Cloud Migration Classifications**

Defining Cloud Migration Terms: The Six Rs and Migration Types

**The Six Rs of Cloud Migration**:

1.  **Rehost** (Lift and Shift):

    -   Migrate on-premises applications directly into virtual machines
        in the cloud with minimal changes.

2.  **Replatform**:

    -   Invest extra effort in migration, looking for platform options
        in the cloud to reduce operational overhead while still
        minimizing changes.

3.  **Repurchase**:

    -   Switch to entirely new software, often Software as a Service
        (SaaS) offerings.

4.  **Refactor**:

    -   Re-architect the application to be cloud-native, often involving
        significant changes.

5.  **Retire**:

    -   Stop using the application entirely rather than migrating it.

6.  **Retain**:

    -   Choose not to migrate the application, leaving it on-premises.

**In Scope for Cloud Migrations**:

-   Rehost (Lift and Shift)

-   Replatform

-   Refactor

**Examples in AWS**:

1.  **Rehost (Lift and Shift)**:

    -   Use migration tools to turn on-premises bare metal or virtual
        machines into Amazon EC2 instances in AWS, essentially running
        the same image in the cloud.

2.  **Replatform**:

    -   For instance, if a database is running on a virtual machine,
        migrate it to a platform-as-a-service offering like Amazon RDS.
        This requires some changes but maintains database engine
        consistency.

3.  **Refactor**:

    -   Split an application\'s data, pushing session data into
        DynamoDB, regular order data into RDS, and historical reporting
        data into Redshift, thus replacing the virtual machine with
        managed cloud service offerings.

**Migration Types**:

1.  **P2V (Physical to Virtual)**:

    -   The most common migration type, where physical resources running
        on bare-metal servers are manually transformed into virtual
        machines with the help of tools.

2.  **V2V (Virtual to Virtual)**:

    -   Migrating resources from one virtualized environment to another,
        whether on-premises or between cloud service providers.

    -   Complexity varies based on factors like legacy configurations,
        software, and operating systems.

3.  **Cloud to Cloud**:

    -   The least common migration path.

    -   Migrating resources from one cloud service provider to another,
        which often involves manual effort or redeployment due to
        limited tools provided by cloud service providers for such
        migrations.


### **5) Storage Migrations**

Migrating Storage to a Cloud Service Provider: Key Considerations and an
AWS Example

**Variables to Consider in Storage Migration**:

1.  **Cost**:

    -   Consider both the cost of storing data in the Cloud Service
        Provider (CSP) and the cost of migrating the data itself.

2.  **Time**:

    -   Evaluate the time required for migration, depending on the
        chosen method.

3.  **Downtime**:

    -   Assess whether the migration will result in an interruption of
        service or if downtime can be minimized or avoided.

4.  **Tools**:

    -   Determine whether third-party tools or tools provided by the CSP
        will be used for the migration.

5.  **Security**:

    -   Address data security concerns during data transfer and while
        stored in the CSP to meet on-premises security requirements.

**Example Using AWS for Storage Migration**:

Scenario: Migrating 900 terabytes of file system storage from an
on-premises data center to AWS S3 (object storage).

Steps:

1.  **Create S3 Bucket**:

    -   Set up an S3 bucket as the destination for the data migration.

2.  **Utilize AWS Snowball**:

    -   Deploy AWS Snowball appliances, which are hardware devices
        roughly the size of a large briefcase.

    -   Each Snowball appliance can store up to 100 terabytes of data.

    -   Plug the Snowball appliances into the on-premises data center
        and connect them to the network.

    -   Copy the data from the on-premises file system or NFS to the
        Snowball appliances.

    -   Deploy multiple Snowball appliances (in this case, nine) to
        accommodate the total data volume.

    -   Use an intermediary server to manage the data transfer to the
        Snowball appliances.

3.  **Ship Appliances to AWS**:

    -   After data is loaded onto the Snowball appliances, ship them
        back to AWS for processing.

4.  **Automatic Data Copy to S3**:

    -   AWS automatically copies the data from the Snowball appliances
        into the S3 bucket on your behalf.

This migration method, using AWS Snowball, minimizes network transfer
and potentially enhances data security. It\'s particularly useful when
transferring large volumes of data, reducing downtime and leveraging
physical appliances for secure and efficient data transfer to the cloud.

### **6) Database Migrations**

#### Database Migration Considerations

Migrating databases from on-premises to the cloud, like AWS, is a
complex undertaking with several considerations:

1.  **Database Engine Compatibility:** Ensure that the source and target
    database engines are compatible. In this case, migrating from
    Microsoft SQL Server to MySQL.

2.  **Schema and Code Conversion:** Utilize tools like the AWS Schema
    Conversion Tool to assess and convert schema and application code.
    Some manual intervention might be required.

3.  **Data Migration:** Use the Database Migration Service (DMS) to
    perform data migration. This includes an initial full copy of data,
    followed by ongoing replication using Change Data Capture (CDC).

4.  **Network Connectivity:** Establish private network connectivity
    between on-premises and AWS for secure data transfer.

5.  **Replication Server:** Set up a replication server (a virtual
    machine) with sufficient resources to cache changes during
    migration.

6.  **Migration Phases:** Divide the migration into three phases:

    -   Full Copy: Initial data transfer while collecting source
        changes.

    -   Apply Changes: Apply cached changes to the target.

    -   Change Data Capture (CDC): Ongoing replication of changes from
        source to target.

7.  **Replica Lag:** Expect a temporary lag during CDC phase as backlog
    information is gradually applied to the target.

8.  **Ongoing Replication:** Phase three (CDC) can be maintained
    indefinitely, and you have the flexibility to turn off ongoing
    replication when desired.

<br><br><br>

#
## Cloud Storage, Compute, and Network Resources

### **1) Cloud-Based Storage Types and Tiers**

#### Primary Cloud Storage Types

-   **Block Storage**

    -   Familiar to on-premises infrastructure users.

    -   Uses SAN or direct-attached disks.

    -   Fast but expensive.

    -   Suitable for OS and data storage for virtual machines.

    -   Efficient for dynamic data.

    -   Not easily scalable, thick provisioned, and expensive.

-   **File Storage**

    -   Utilizes NAS (Network Attached Storage).

    -   Requires storage protocol like NFS, CIFS, or SMB.

    -   Very scalable and tends to be thin provisioned.

-   **Object Storage**

    -   Uses proprietary technology from the cloud provider.

    -   Accessed over the network.

    -   Splits data into data and metadata.

    -   Extremely scalable, favors write once read many workloads.

#### Storage Tiers

-   **SSD (Solid State Disk) Storage**

    -   Utilizes flash memory for high-performance.

    -   Designed for random access workloads.

-   **Hybrid Storage**

    -   Combines SSD and HDD (Hard Disk Drive).

    -   Balances performance and cost.

-   **HDD (Hard Disk Drive) Storage**

    -   Uses spinning platters, inexpensive.

    -   Designed for sequential access workloads.

-   **Archive Storage**

    -   Can be HDD or offline storage like tape.

-   Cost vs. Performance:

    -   Cost per gigabyte decreases from left to right.

    -   Performance decreases as cost decreases.

#### Cloud Storage Tiers

-   **Hot Tier**

    -   Minimizes data access costs.

    -   More expensive for storage.

    -   Offers high performance.

-   **Warm or Cool Tiers**

    -   Balanced between access cost, storage cost, and performance.

-   **Cold Storage**

    -   Increases data access costs.

    -   Low storage costs.

    -   Lower performance, particularly in terms of latency.
<br>
<br>

### **2) Storage Protocols**

#### Storage Area Network (SAN)

-   Combines HDD, SSD, or hybrid disks with a controller interface.

-   Clients interact with the SAN, not individual hard drives.

-   Accessible through different protocols:

    -   Hardware-based fiber connection or ethernet.

    -   Fiber channel carries SCSI protocol over fiber.

    -   Fiber Channel over Ethernet (FCoE) carries SCSI over ethernet.

    -   iSCSI is a common protocol supported by many OS.

    -   NVME over Fabric (NVMe-oF) for hardware to reach hard drives.

#### File Sharing Protocols

-   Linux servers use NFSv4, configured with /etc/exports.

-   Windows servers use CIFS for Windows clients.

-   Both can use fiber channel, FCoE, or iSCSI to access storage.

#### iSCSI vs. Fiber Channel

-   iSCSI:

    -   Cheaper, lower performance, simpler to implement.

    -   Designed for multiple clients accessing the same storage.

-   Fiber Channel:

    -   Expensive due to fiber usage.

    -   Higher performance with lower latency.

    -   Designed for one-to-one server to SAN connectivity.


<br><br>

### **3) Combining Hard Drives - RAID Types**

#### RAID 0 (Striping)

-   Stripes multiple volumes for higher throughput.

-   Cannot tolerate the loss of any hard drive.

#### RAID 1 (Mirroring)

-   Mirrors data from one hard drive to another.

-   No performance benefit compared to RAID 0.

-   Tolerates the loss of one hard drive without data loss.

#### RAID 5 (Striping with Parity)

-   Combines data striping for performance with a parity disk.

-   One hard drive is dedicated to backing up data.

-   Tolerates the loss of one hard drive without data loss.

#### RAID 6 (Double Parity)

-   Provides double parity with two dedicated backup hard drives.

-   Enhanced data redundancy.

#### RAID 10 (Striped Mirrored Volume)

-   Combination of RAID 0 and RAID 1.

-   Offers both striping and mirroring for performance and redundancy.

### Cloud Storage Implementation

-   From a client perspective:

    -   Striped volumes are common for cloud storage.

    -   Mirroring is an option.

    -   Parity is usually handled by the cloud service provider.

<br><br>

### **4) Features of Cloud Storage**

#### Compression

-   CPU-intensive process to reduce data size.

-   Trade-off between CPU usage and storage space.

#### Deduplication

-   Cloud Service Provider\'s responsibility.

-   Identifies duplicate data (objects or blocks).

-   Reduces duplicate data to one copy and uses pointers.

-   Efficient use of storage space.

#### Replication

-   Can be synchronous or asynchronous.

-   Creates multiple copies of data.

-   Applicable to block storage, file system storage, or object storage.

#### Thin Provisioning

-   Pay only for the data present in storage.

-   No need to determine a maximum size.

-   Efficient use of storage resources.

#### Thick Provisioning

-   Provision more storage than needed.

-   Potential for better performance.

-   Pay for provisioned storage, not just used space.

#### Hyperconverged Storage

-   Combines virtual CPU, memory, and storage into a single resource.

-   Common in virtual machine environments.

#### Software Defined Storage (SDS)

-   Separates control plane from data plane.

-   Control plane manages storage provisioning, backup, and deletion.

-   Data plane handles data access, modification, and removal.

-   Abstracts hardware from clients.

-   Used in NAS, SAN, and traditional storage.

-   Allows for policy-based management and different permissions for
    control and data planes.

<br><br>

###  **5) Network Service Deployment**

#### **Cloud DNS with AWS Route 53**

-   AWS Route 53 performs DNS for AWS services.

-   Supports public hosted zones for internet resolution.

-   Offers private hosted zones for specific VPC networks.

-   Allows private hosted zones to be resolved from on-prem networks
    through forwarders and endpoints, requiring private network
    connectivity (e.g., VPN).

#### **Network Time Protocol (NTP)**

-   Provides time synchronization for OS-based servers.

-   Active Directory for Microsoft handles NTP automatically.

-   Linux offers configurability for choosing NTP servers.

-   Time can also be delivered from the host operating system or
    hypervisor for virtual machines.

#### **Dynamic Host Configuration Protocol (DHCP)**

-   Enables dynamic network configuration for virtual machines.

-   Provides host names, DNS domain names, private IP addresses, subnet
    masks, default gateways, DNS servers, and NTP servers.

-   Eliminates the need for manual configuration in the operating
    system.

#### **IP Address Management (IPAM)**

-   Manages IP addresses to prevent conflicts in virtual networks.

-   Ensures no overlapping network address ranges.

-   Prevents issues like creating VPCs with identical network ranges or
    partial overlaps where one network is a subset of another.

#### **Content Delivery as a Network (CDN)**

-   Caches web or multimedia assets closer to end users.

-   Reduces backend load and improves performance with lower latency and
    higher throughput.

-   AWS CloudFront example:

    -   Identifies closest edge locations to the user.

    -   Serves cached assets from edge locations if available.

    -   Checks regional edge caches if not available in edge locations.

    -   Retrieves and caches assets from the content origin if needed.

<br><br>

###   **6) Virtual Private Network (VPN)**

-    VPN stands for Virtual Private Network, used to
    encrypt data between two network nodes.

### VPN Technologies

-   **IPsec**:

    -   Commonly used for data encryption.

    -   Offers various VPN implementation options.

-   **L2TP (Layer 2 Tunneling Protocol)**:

    -   Utilizes IPsec over layer two.

-   **SSTP (Secure Socket Tunneling Protocol)**:

    -   Implemented from Windows servers.

-   **OpenVPN**:

    -   Third-party, open-source option.

    -   Not as high-performing as some alternatives.

-   **IKv2 (Internet Key Exchange v2)**:

    -   Provides fast and current key exchange.

    -   Often used alongside IPsec.

-   **PPTP (Point-to-Point Tunneling Protocol)**:

    -   Deprecated and considered outdated.

    -   Recommended to be upgraded if encountered in real-world
        scenarios.

### VPN Implementation Patterns

#### **Site-to-Site VPN**

-   Connects different data centers or networks.

-   One side initiates the VPN tunnel, and the other side terminates it.

-   May require keep-alive packets to maintain the tunnel persistently.

#### **Point-to-Site VPN**

-   Used for remote employees or temporary connectivity.

-   Individual host connects to a network.

#### **Point-to-Point VPN**

-   Single node connects to another single node.

-   Remote node provides access to the network beyond.


<br><br>

### **7) Routing and Network Appliances**

-   **VRF (Virtual Routing and Forwarding)**:

    -   Virtualization at layer three of the OSI model.

    -   Manages multiple route tables.

    -   Reduces the need for physical or virtual routers.

### Types of Routing

#### **Static Routes**

-   Long-standing routing method.

-   Simple implementation, suitable for network hardware or individual
    nodes.

-   Hard-coded routes in route tables.

-   Limited automation, inflexible, does not scale well.

#### **Dynamic Routing**

-   Routes propagated as needed with appropriate priority.

-   Supports automation, greater flexibility, and scalability.

-   Initial setup complexity; troubleshooting challenges.

#### **MPLS (Multi-Protocol Label Switching)**

-   Routing based on labels rather than remote destination or priority.

-   Labels assigned to networks or hosts.

-   Unique routing approach compared to static and dynamic routes.

### Load Balancer

-   Distributes traffic sent by clients at layers four or seven in the
    OSI model.

-   Load balancer endpoint receives traffic and directs it to backend
    resources.

-   Backend resources can include containers, virtual machines, or IP
    addresses.

### Web Application Firewall (WAF)

-   Operates alongside or in front of an elastic load balancer.

-   Applies layer seven inspection to web-based requests.

-   Filters or drops requests before passing them to a load balancer.

-   Enhances security for web applications.



###  **8) Compute Virtualization**

-   **VM (Virtual Machine)**:

    -   Virtual operating system running on top of underlying hardware.

### Underlying Hardware

-   **Bare Metal Server**:

    -   Physical server in an on-premises data center or cloud service
        provider\'s infrastructure.

### Types of Hypervisors

#### **Type 1 Hypervisor**

-   Runs directly on bare metal.

-   Minimal interface.

-   Provides almost bare-metal performance.

-   Used for high security.

-   Typically managed on-premises.

#### **Type 2 Hypervisor**

-   Installed on an existing operating system (e.g., laptop or desktop).

-   Provides a more comprehensive interface.

-   Lower performance due to abstraction layers.

-   Supports multiple operating systems on top of the base OS.

-   Managed locally.

-   Less security-focused.

### Hypervisor Stacking

-   Type 1 hypervisor on top of bare metal.

-   Type 2 hypervisor on top of the type 1 hypervisor.

-   Offers flexibility in virtualization.

### Hypervisor Comparison

-   Type 1 Hypervisor:

    -   Almost bare-metal performance.

    -   High security.

    -   Minimal interface, requires separate management interface.

-   Type 2 Hypervisor:

    -   Lower performance due to abstraction.

    -   Supports multiple OS on the base OS.

    -   Has its own interface for local management.

    -   Less security-oriented.

### Oversubscription

-   Allocating more resources than physically available for cost
    efficiency.

-   Suitable for workloads with low CPU, memory, or disk requirements.

<br><br>

### **9) Compute Resource Types**

Public cloud providers offer services to launch virtual machines (VMs)
with different resource allocation profiles or families:

#### **General Purpose**

-   Provides roughly equivalent amounts of virtual CPU, memory, and
    storage.

-   No preference for any specific resource.

-   Balanced resource allocation.

#### **CPU Optimized**

-   Emphasizes CPU power.

-   Typically offers more virtual CPU at the expense of memory.

-   Suitable for CPU-intensive workloads.

#### **Memory Optimized**

-   Emphasizes memory capacity.

-   Offers more memory with relatively less virtual CPU.

-   Suitable for memory-intensive workloads.

#### **Storage Optimized**

-   Prefers storage, bandwidth, throughput, and IOPS (Input/Output
    Operations Per Second).

-   Requires more virtual CPU and memory.

-   Suitable for storage-intensive workloads.

### Graphics Processor Units (GPUs)

-   Used for various workloads, including AI and machine learning.

#### **Shared GPU**

-   Multiple VMs utilize the same GPU.

-   Shared tenancy model.

-   Can be oversubscribed for cost-effectiveness.

#### **Pass-Through GPU**

-   One-to-one relationship between a GPU and a single VM.

-   Designed for extreme performance.


