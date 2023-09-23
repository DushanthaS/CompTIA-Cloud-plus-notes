# Cloud Architecture and Design
<br />
<br />

## Cloud Models and Capacity Planing

<br />
<br />

### 1. Cloud Deployment Models



**Public Cloud**

-   Infrastructure hosted in a third party\'s cloud.

-   Subscription-based model; you don\'t own the infrastructure.

-   Utilizes shared tenancy.

-   Examples: Amazon Web Services, Google Cloud, Azure.

**Private Cloud**

-   Infrastructure is on-premises and owned by your company.

-   Includes bare metal and virtual machines.

-   Can be considered a private cloud if managed as a service.

-   No reliance on public cloud infrastructure.

**Community Cloud**

-   Specific consumers with unique needs share the same infrastructure.

-   Managed by community members or a third party.

-   Not available for general subscription.

**Hybrid Cloud**

-   Combination of two or more deployment models (public, private,
    community).

-   Often combines public cloud with on-premises data center.

-   Requires private networking infrastructure between clouds.

**Cloud within a Cloud or Virtual Private Cloud (VPC)**

-   Utilizes a provider\'s infrastructure to create an isolated data
    center network.

-   Unshared by default and not accessible to other customers.

-   Enables customers to have single tenancy within a multi-tenant
    infrastructure.

**Multi-Tenancy**

-   Multiple customers share the same hardware resources simultaneously.

-   Main business model for public cloud providers.

-   Bare metal usage is possible but less common.

**Multi-Cloud**

-   Combines a private cloud deployment with multiple public cloud
    providers.

-   Strategy to reduce vendor lock-in with a single provider.

 >These deployment models offer various options for designing cloud
solutions, each with its unique characteristics and advantages.
Understanding these models is essential for effective cloud architecture
design and decision-making


### 2. Cloud Service Models

In addition to cloud deployment models, it\'s important to understand
cloud service models and the shared responsibility model. These concepts
often overlap and are fundamental in cloud computing. Let\'s delve into
cloud service models:

**Infrastructure as a Service (IaaS)**

-   **Description:** The foundational layer of the technology stack in
    cloud computing.

-   **Components:** Includes data centers, physical infrastructure
    (building, power, cooling, cabling, racks), network infrastructure,
    hardware, and virtualization.

-   **Examples:** Virtual private cloud (VPC), launching a virtual
    machine.

-   **Characteristics:** Offers high flexibility for resource
    customization. Customers have significant responsibilities for
    managing and maintaining resources post-creation.

**Platform as a Service (PaaS)**

-   **Description:** Builds on top of IaaS, adding operating systems and
    software management by the provider.

-   **Components:** Includes IaaS elements (data center, networking,
    servers, virtualization) plus the operating system and software
    stack.

-   **Examples:** AWS Elastic Beanstalk, Heroku, Azure Function Apps.

-   **Characteristics:** Reduces customer responsibilities and tasks
    compared to IaaS, but offers less configuration flexibility.

**Software as a Service (SaaS)**

-   **Description:** The top layer of cloud service models, where the
    provider manages the entire hosted application.

-   **Components:** Fully managed application, including infrastructure,
    software, and services.

-   **Examples:** Google Workspace, Salesforce.

-   **Characteristics:** Offers the least flexibility in terms of
    customer configuration but requires minimal operational overhead.

 >These service models represent different levels of abstraction and
responsibility within the cloud computing ecosystem. Understanding them
is crucial for selecting the right model to meet specific business needs
and requirements.

### 3. Shared Responsibility Model in Cloud Computing

 The shared responsibility model is a crucial concept in cloud computing
that outlines the responsibilities of both the cloud provider and the
customer. It defines the level of ownership and responsibility for
various aspects of the product and its use. Let\'s explore how the
shared responsibility model applies to different cloud service models:

**Infrastructure as a Service (IaaS)**

-   **Provider\'s Responsibilities:**

    -   Data centers and hardware.

    -   Global network infrastructure.

    -   Server hardware, compute, storage, database, and network
        infrastructure.

-   **Customer\'s Responsibilities:**

    -   Operational overhead for the operating system.

    -   Network configuration.

    -   Firewall configuration for resources.

    -   Platform and application management on top of the
        infrastructure.

    -   Server-side encryption.

    -   Protection of network traffic.

    -   Protection of data, including data encryption.

    -   Data integrity checking.

    -   Data management.

**Platform as a Service (PaaS)**

-   **Provider\'s Responsibilities:**

    -   Operating system.

    -   Networking.

    -   Firewalling.

    -   Platform and application management.

    -   Server-side encryption.

    -   Data integrity.

-   **Customer\'s Responsibilities:**

    -   Client-side data encryption.
  
    -   Network traffic protection.
  
    -   Data management

**Software as a Service (SaaS)**

-   **Provider\'s Responsibilities:**

    -   100% of networking, including network traffic protection.

-   **Customer\'s Responsibilities:**

    -   Optional client-side data encryption.

    -   Data management.

 >In the SaaS model, the provider assumes most of the operational
responsibilities, including network management and data integrity, while
the customer\'s focus is primarily on data management. It\'s essential
to understand this shared responsibility model to ensure that security
and compliance requirements are met when using cloud services
effectively.


### 4. Capacity Planning: Understanding Requirements

Capacity planning involves considering various factors that contribute
to determining the resources needed for a project or system. One crucial
aspect of capacity planning is understanding and documenting
requirements, which can encompass technical, business, and other
relevant factors. 

#### __1) Requirements__
 Let\'s explore the elements involved in defining requirements.

**Business Needs Analysis**

-   **Purpose:** The starting point for capacity planning is to conduct
    a business needs analysis to identify what the business will
    require.

-   **Importance:** This analysis forms the foundation for the entire
    capacity planning process.

**Hardware Requirements**

-   **Derived from:** Business needs analysis.

-   **Definition:** Hardware requirements specify the physical
    infrastructure needed to support the project or system. This
    includes servers, storage, networking equipment, and more.

**Virtualization Requirements**

-   **Derived from:** Business needs analysis (if virtualization is the
    chosen approach).

-   **Definition:** Virtualization requirements outline the capacity
    needed for virtualized resources, such as virtual machines,
    containers, or cloud instances.

**Software Requirements**

-   **Derived from:** Business needs analysis.

-   **Scope:** Software requirements encompass various software
    components, which may include off-the-shelf products, custom
    software, security software, auditing tools, and more.

**Budget Considerations**

-   **Influence:** Business needs analysis contributes to budgeting
    decisions.

-   **Budget Types:** Include development budget, operational budget,
    and security budget, taking into account costs for creating,
    maintaining, and securing the product or system.

#### __2) Standard Template for Documentation__

-   **Purpose:** Establish a consistent format for documenting
    requirements.

-   **Components:** Define what the document should contain, including
    sections, required information, optional details, and roles of
    approvers.

 >Creating a well-structured and comprehensive document that addresses
these requirements is essential for effective capacity planning. It
ensures that the necessary resources are allocated to meet the project
or system\'s needs while staying within budget constraints.


#### __3) Licensing Models and Factors__

In capacity planning, it\'s crucial to consider various licensing models
and factors that influence resource allocation and usage. Let\'s explore
different licensing models and the key capacity planning factors:

**Licensing Models**

1.  **Per User Licensing**

    -   **Description:** Each user who uses the software requires a
        separate license, regardless of frequency.

2.  **Socket-Based Licensing**

    -   **Description:** Licensed per overall processor (socket),
        regardless of the number of cores within that socket.

3.  **Core-Based Licensing**

    -   **Description:** Licensed per core, meaning each core on a CPU
        requires a separate license.

4.  **Volume-Based Licensing**

    -   **Description:** Based on the number of installations rather
        than the number of individual users. Even unused installations
        count against the license.

5.  **Perpetual Licensing**

    -   **Description:** Pay once upfront, and the license remains valid
        indefinitely. Limited access to support and upgrades may apply.

6.  **Subscription-Based Licensing**

    -   **Description:** Pay on a periodic basis (e.g., daily, monthly,
        yearly) with potentially easier upgrades and better support.


#### __4) User Density__

 The number of users simultaneously using the product. High concurrent users can lead to capacity challenges.

#### __5) System Load__

Monitoring Key Performance Indicators (KPIs) to assess the infrastructure\'s overall workload and performance.

#### __6) Trend Analysis__

Utilize metrics from user density, system load, and license usage to establish baselines of normal behavior. Monitor for anomalies that may require capacity adjustments.

#### __7) Performance Monitoring__

Ongoing monitoring of application performance, including user experience quality, CPU, memory, and disk usage, to ensure optimal resource allocation.

>Effective capacity planning considers these licensing models and factors
to ensure that resources are allocated efficiently and in line with
business needs, user demands, and budget constraints.

<br />
<br />

## High availability and scaling in cloud environments
<br />
<br />

**Key Definitions for High Availability**

Before delving into the concept of high availability, it\'s essential to
clarify several technical terms and phrases. Here are the definitions of
these terms:

1.  **Business Continuity**

    -   **Definition:** The strategy and processes aimed at ensuring a
        business remains functional in some capacity during or after a
        critical incident. It encompasses more than just compute
        infrastructure or data centers and can apply to various aspects
        of a business, including office space, management resource
        redundancy, and finances.

    - *How to keep the business functional in some capacity during/after a critical incident.*

2.  **Disaster Recovery (DR)**

    -   **Definition:** The process of saving and recovering data and
        other critical business processes during or after a critical
        incident. It involves having a well-defined plan or playbook
        with steps to follow for recovery, which directly contributes to
        business continuity.

    - *How to save and recover data and other business processes during /after a critical incident. Contributes to the Business Continuity Plan.* 

3.  **Recovery Time Objective (RTO)**

    -   **Definition:** A documented time value that represents the
        maximum allowable delay between when services become interrupted
        and when they must be fully restored. RTO outlines the
        acceptable downtime for services during a disaster or incident.

4.  **Recovery Point Objective (RPO)**

    -   **Definition:** A time-based metric that defines the maximum
        acceptable amount of time since the last data recovery point.
        RPO specifies the maximum data loss that is deemed acceptable in
        terms of time.

5.  **High Availability (HA)**

    -   **Definition:** The characteristic of a system where it
        continues to function despite the complete failure of any
        component within the architecture. However, HA acknowledges that
        there may be an interruption of service, but it should not
        exceed the time limits defined by the Recovery Time Objective
        (RTO).

6.  **Redundancy**

    -   **Definition:** Redundancy is closely related to high
        availability but differs in that it ensures a system continues
        to function without degradation in performance even in the event
        of a complete component failure. Redundancy does not imply any
        interruption of service and is typically more challenging to
        achieve than simple high availability.


### High Availability Patterns and Geographic Resource Separation.
<br>

High availability often involves implementing patterns such as failover
and failback to ensure system resilience. Let\'s explore these patterns
and the concept of geographic resource separation:


-   **Failover:** In the event of an outage, like an on-prem data center
    failure, a failover can be implemented to serve the same workload
    from a public cloud. This may require changing DNS settings to point
    to the public cloud endpoint.

-   **Failback:** After the on-prem or private cloud infrastructure
    becomes healthy again, a failback can be performed by making another
    DNS change to move end users or clients from the public cloud back
    to the on-prem infrastructure.

### Geographic Resource Separation

-   **Availability Zone:** An availability zone comprises one or more
    data centers, which appear as a single group of infrastructure to
    end users. While individual resources within an availability zone
    might lack redundancy, combining resources across multiple
    availability zones can create an overall highly available
    infrastructure.

-   **Region:** A region consists of multiple physically separate
    availability zones. Unlike availability zones, which may be close
    together, regions are separated by larger distances, often tens or
    hundreds of miles or kilometers. This separation is designed to
    enhance resilience. Public cloud services are primarily hosted
    across regions, making it a common unit of resource scope,
    especially for Software as a Service (SaaS) offerings.


### Scaling for High Availability

Scaling is a fundamental approach to achieving high availability in
infrastructure. Let\'s explore different types of scaling and how they
can be leveraged:

#### Horizontal Scaling

-   **Description:** Horizontal scaling involves adding or removing
    resources to handle changes in workload demand. It is commonly used
    in public cloud infrastructure and is designed to enhance
    availability.

-   **Example:** In a two-tier architecture with a load balancer and a
    fleet of virtual machines serving as application servers, as metrics
    (such as KPIs) indicating increased activity cross a threshold, you
    can scale out by adding more individual virtual machines to handle
    the application load. 
    When reducing resources due to decreased
    demand, it is called scaling in.

#### Vertical Scaling

-   **Description:** Vertical scaling is typically performed within a
    single server or virtual machine by adding resources like memory,
    CPU, disk space, or network throughput. It is often suitable for
    private clouds or on-premises data centers.

-   **Considerations:** Vertical scaling may involve an interruption of
    service, as you may need to power off the virtual machine or shut
    down the hardware to make resource upgrades.

<br>

### **Advanced Scaling Strategies for High Availability**

In addition to the previously discussed scaling mechanisms (horizontal,
vertical, and geographical scaling), there are other innovative
approaches to achieve high availability:

**Cloud Bursting**

-   **Description:** Cloud bursting is used when an on-prem data center
    reaches saturation or capacity limits, either due to physical
    constraints or a lack of recent server provisioning. In this
    scenario, additional capacity is added in a public cloud
    infrastructure to handle the overflow of work.

**Oversubscription**

-   **Description:** Oversubscription is primarily employed for cost
    efficiency. It involves provisioning virtual resources that
    collectively exceed the available physical resources. This approach
    assumes that saturation will not occur, making it a common pattern
    for public cloud providers. Oversubscription can apply to CPU,
    memory, and network throughput.

**Hypervisor Affinity**

-   **Description:** Hypervisor affinity prioritizes placing resources
    physically and virtually close together to achieve high network
    throughput and low latency. This is suitable for scenarios where
    most traffic occurs between nodes of a workflow, and resilience is
    not a top priority. However, it poses a risk of simultaneous failure
    if resources are clustered too closely (e.g., within the same rack
    during maintenance).

**Hypervisor Anti-Affinity**

-   **Description:** In contrast to hypervisor affinity, hypervisor
    anti-affinity ensures that resources are separated physically, at
    least within separate racks or even different data centers or
    regions. This approach is suitable for critical instances that must
    remain independent of each other to maximize availability and
    resilience, minimizing the risk of simultaneous outages.


### Identifying and Eliminating Single Points of Failure

Improving the reliability and availability of an infrastructure often
involves identifying and removing single points of failure. These
vulnerabilities can manifest in various components of an infrastructure,
including network equipment, servers, hardware, virtual machines,
storage appliances, and database instances. While eliminating all single
points of failure is challenging, especially in private cloud
implementations, it\'s easier in public cloud environments where the
responsibility for resilience is delegated to the provider. Here\'s an
example using Amazon Web Services (AWS) to demonstrate how to avoid
single points of failure:

1.  **Initial State:**

    -   Application server running on a single virtual machine.

    -   DNS configured to point directly to the public IP address or DNS
        of the virtual machine.

    -   Tightly coupled setup, posing a single point of failure.

2.  **Improvements:**

    -   **Load Balancer:** Split out the reverse proxy functionality
        into a load balancer, like AWS\'s Application Load Balancer. It
        allows for multiple availability zones and offers redundancy and
        automatic scaling.

    -   **Application Servers:** Instead of a single virtual machine,
        use multiple virtual machines for the application servers.
        Employ auto-scaling to scale horizontally, ensuring redundancy.

    -   **Database:** Utilize AWS\'s Aurora Serverless, a relational
        database service using MySQL or Postgres. Rather than running on
        discrete virtual machines, it employs Aurora Compute Units
        (ACUs) with CPU and memory. All ACUs are fronted by a single
        proxy endpoint, directing queries to the next available ACU.

By implementing this architecture, most potential single points of
failure from the initial deployment are eliminated, significantly
improving reliability and availability.

However, it\'s essential to recognize that increasing availability and
reliability may come with increased costs and operational overhead.
Decisions about where to prioritize resources and how to balance these
factors depend on specific infrastructure requirements and
organizational priorities.

<br>
<br>

## Solution Design
<br>

 ### **Requirements Analysis**

A business requirements analysis is a crucial step in understanding and
documenting the needs and priorities of both users and the business when
planning for cloud adoption. Here are the key elements of a business
requirements analysis:

1.  **Software:**

    -   **Users:** Desire a familiar interface, easy-to-understand
        billing, and user-friendly administration tools.

    -   **Business:** Requires scalability, cloud-native architecture,
        customizability, and the option for cloud service provider (CSP)
        management.

2.  **Hardware:**

    -   **Users:** May prioritize multiple platform support and Anywhere access.

    -   **Business:** Emphasizes fast, reliable, and scalable
        connections, along with reliability and availability.

3.  **Integration:**

    -   **Users:** Expect software to integrate with existing data
        sources, support legacy on-premises software, and work with
        partner offerings.

    -   **Business:** Values CSP-supported and managed integration
        without increased operational overhead.

4.  **Budget:**

    -   **Users:** Seek reporting flexibility, chargebacks, and
        showbacks, along with opportunities for migrating to managed
        services.

    -   **Business:** Prefers subscription-based models for predictable
        revenue, scalable costs without increased operational overhead,
        and clear support cost predictions.

5.  **Compliance:**

    -   **Users:** Require CSP certification and compliance
        attestations, compatibility with common frameworks (NIST, ISO,
        SOC 1, SOC 2), and the ability to meet customer controls.

    -   **Business:** Shares the same compliance requirements, aiming
        for alignment with user expectations.

6.  **SLA (Service Level Agreement):**

    -   **Users:** Look for adherence to uptime metrics and timely
        responses to outages or maintenance.

    -   **Business:** Requires legally enforceable SLA documentation,
        compatibility with business application SLAs, and proactive
        monitoring for frequent outages.

7.  **User and Business Needs:**

    -   **Users:** Expect usability, familiarity, and security that
        doesn\'t hinder productivity.

    -   **Business:** Prioritizes security, cost, and reliability,
        considering the overall impact on operations.

8.  **Security:**

    -   **Users:** Want security that doesn\'t impede work and an
        easy-to-use interface despite security measures.

    -   **Business:** Seeks flexible security features, comprehensive
        data and network protection options, and a balance between
        security and usability.

9.  **Network:**

    -   **Users:** Require high-performance and reliable networks.

    -   **Business:** Adds an emphasis on encryption options, the
        ability to set up hybrid cloud environments, reliability, and
        redundancy to mitigate localized outages.

By analyzing and documenting these elements comprehensively,
organizations can align their cloud adoption strategies with the needs
and expectations of both users and the business, ensuring a successful
transition to the cloud while optimizing resources and outcomes.
<br>
<br>
### **Environment Types in Solution Designs**

Solution design and operations involve more than just architectural
considerations; they also encompass the management and promotion of
applications through various environments. Here, we\'ll explore
different types of environments that play a crucial role in the software
development lifecycle:

1.  **Development Environment:**

    -   **Purpose:** Initial environment for coding and experimentation.

    -   **Size:** Usually downsized to reduce costs.

    -   **Deployment:** Developers can deploy code directly.

    -   **Testing:** Sandbox for testing and experiments.

    -   **Reproducibility:** Can be redeployed from scratch if needed.

2.  **Quality Assurance (QA) Environment:**

    -   **Purpose:** Testing environment for functional, regression, and
        security testing.

    -   **Size:** Typically smaller than production.

    -   **Automation:** Supports continuous integration and deployment.

    -   **Security:** May include security testing and audits.

3.  **Staging Environment:**

    -   **Purpose:** Pre-production environment identical to production.

    -   **Size:** Should be the same size as production.

    -   **Dependencies:** Mimics production\'s upstream and downstream
        dependencies.

    -   **Testing:** Used for further QA testing if separate from QA
        environment.

4.  **Production Environment:**

    -   **Purpose:** Full-sized infrastructure for end-user access.

    -   **Size:** Must handle production-level loads.

    -   **Change Management:** Follows a formal change management
        process.

    -   **Automation:** Managed using automation tools, no manual
        changes.

5.  **Blue-Green Deployment:**

    -   **Purpose:** Deployment model for minimizing downtime.

    -   **Environments:** Two identical environments (blue and green).

    -   **Deployment:** New code is deployed to one environment while
        the other serves production.

    -   **Scaling:** The environment not in use can be downsized to
        reduce costs.

6.  **Canary Deployments:**

    -   **Purpose:** Gradual deployment to a small subset of production.

    -   **Deployment:** Updates deployed to a small percentage of
        resources.

    -   **Monitoring:** Changes are monitored for issues or anomalies.

    -   **Rollback:** Easy rollback if problems are detected.

    -   **Full Deployment:** Proceeds to deploy to the rest of the
        environment upon verification.

7.  **Disaster Recovery Environment:**

    -   **Purpose:** Backup production environment for disaster recovery
        and testing.

    -   **Size:** Scaled according to disaster recovery requirements.

    -   **Usage:** Activated during emergencies, catastrophic events, or
        for DR testing.

These various environments play distinct roles in the software
development lifecycle, from initial development and testing to staging,
production, and disaster recovery. Properly managing and transitioning
applications through these environments helps ensure quality,
reliability, and efficiency in the software deployment process.
<br>
<br>
### **Security Testing and Other Types of Testing in Solution Design**

In solution design and development, it\'s crucial to perform various
types of testing to ensure that new code can be safely promoted to
production. Two essential types of security testing are vulnerability
testing and penetration testing, which help identify and address
security issues:

1.  **Vulnerability Testing:**

    -   **Purpose:** Identifying known vulnerabilities in different
        contexts.

    -   **Contexts:**

        -   Network-level vulnerabilities (network security).

        -   Operating system vulnerabilities (OS security).

        -   Service-level vulnerabilities (including third-party
            dependencies).

        -   Application-level vulnerabilities (code developed
            internally).

    -   **Scope:** Tests are performed against a predefined list of
        vulnerabilities.

2.  **Penetration Testing:**

    -   **Purpose:** Discovering potential security issues, especially
        those unknown.

    -   **Usage:** Often used to meet compliance objectives and during
        security audits.

    -   **Scope:** Casts a wider net to identify weaknesses, including
        those not covered by vulnerability testing.

    -   **Result Integration:** Vulnerabilities discovered during
        penetration testing can be included in subsequent vulnerability
        testing.

These security testing practices help organizations identify and
mitigate security risks in their software applications.

Additionally, various other types of testing are essential during the
development process:

**Use Tests:**

1.  **Performance Testing:**

    -   **Purpose:** Validates that the application remains functional
        as the load increases.

    -   **Focus:** Ensures the application scales efficiently and meets
        performance requirements.

2.  **Regression Testing:**

    -   **Purpose:** Ensures that new changes or updates do not break
        existing functionality.

    -   **Focus:** Verifies that changes don\'t negatively impact the
        application\'s stability or features.

3.  **Functional Testing:**

    -   **Purpose:** Validates that the application\'s functionality
        works according to specifications.

    -   **Focus:** Tests both new and existing functionality to ensure
        they meet requirements.

4.  **Usability Testing:**

    -   **Purpose:** Evaluates the user experience to ensure it aligns
        with usability requirements.

    -   **Focus:** Examines user interactions, user interface design,
        and overall user satisfaction.

These testing types play crucial roles in ensuring the reliability,
performance, security, and user experience of software applications.
Incorporating these tests into a continuous integration and continuous
deployment (CI/CD) workflow helps maintain and improve the quality of
the application throughout its development lifecycle.
