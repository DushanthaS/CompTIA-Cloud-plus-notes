
<br>

# Operations and Support  - Part 2
<br>


## Cloud Automation
<br>

### **1) Infrastructure as Code (IaC)**

One of the most powerful technology advancements with the rise of public
clouds is **Infrastructure as Code (IaC)**. This concept allows for the
automation of deploying and managing virtual infrastructure, applying
DevOps principles to infrastructure and operations. IaC brings
much-needed quality and repeatability to infrastructure lifecycles.

**Key Concepts**

1.  **IAC Types:**

    -   **Imperative:** Uses command line or script-based operations but
        lacks idempotency (Repeted task will always end up with same results).

    -   **Declarative:** Utilizes state definitions and templates, often
        in YAML or JSON, exhibiting idempotency.

2.  **Example: Imperative IaC with AWS CLI:**

    -   Creating a Kinesis DataFire host delivery stream.

    -   Offers flexibility but may not guarantee idempotency.

3.  **Example: Declarative IaC with Terraform:**

    -   Creating an EC2 instance in AWS.

    -   Utilizes templates and variables, ensuring idempotency.

**Benefits of IaC**

-   **Faster Deployments and Changes:** Accelerated infrastructure
    provisioning and modification.

-   **Faster Recovery and Rollback:** Swift response to issues with the
    ability to revert.

-   **Reduced Configuration Drift:** Minimized manual changes, reducing
    discrepancies.

-   **Code Reusability:** Templates can be reused with parameter
    adjustments.

-   **Version Control:** Templates treated as code and stored in source
    code repositories.

-   **Self-Documenting Infrastructure:** Vital for incident response and
    disaster recovery.

<br>

**AWS Example with CloudFormation**

**Scenario:** Automating the deployment of an AWS Neptune cluster and
SageMaker notebook with underlying network creation.

**Task 1: Deploy the Network**

-   Create VPC network.

-   Define subnets.

-   Set up internet gateway, NAT gateways, route tables, and Neptune
    subnet group.

**Task 2: Deploy Neptune Cluster**

-   Ensure high availability with multiple availability zones.

-   Implement replicas.

-   Enhance security measures for the database resource.

**Task 3: Deploy SageMaker Notebook**

-   Configure security group, permissions, and connection settings.

IaC streamlines the creation, management, and documentation of complex
infrastructure, making it a critical tool for modern cloud-based
environments.

### **2) CI/CD and version control**

**Continuous Integration and Continuous Deployment (CI/CD)** have become
integral in tandem with DevOps principles, aiming to enhance the
frequency and quality of code deployments to applications. This
automated approach reduces human intervention in the deployment process,
minimizing the inherent risks associated with manual actions.

**Key Concepts**

-   **Automation:** Eliminates the need for human intervention in the
    deployment process.

-   **Risk Reduction:** Human involvement is reserved for
    troubleshooting when automation encounters issues.

-   **CI/CD Pipeline:** Divided into discrete tasks.

**Continuous Integration (CI)**

1.  **Building the Application:** Compiling and preparing the
    application for deployment.

2.  **Testing the Application:** Conducting various tests (e.g.,
    functional, regression, performance) as per organizational
    requirements.

3.  **Merging Code:** Integration of code changes into a separate
    branch, enabling further rebuilding and deployment to the target
    environment.

**Continuous Delivery (CD)**

-   **Code Artifact Repository:** The code artifact for deployment is
    placed in the appropriate repository but not yet deployed to any
    environment.

-   Sometimes considered as the endpoint of CI/CD, marking the
    successful preparation of the code artifact for deployment.

**Continuous Deployment**

-   **Deployment to Environment:** The code artifact is moved from the
    repository to the designated environment.

-   May involve additional automated testing (e.g., regression testing)
    to ensure the code functions as expected.

**Version Control**

-   **Definition:** The practice of persisting multiple versions of
    application or infrastructure code.

-   **Use Cases:**

    -   Storing versions of templates.

    -   Holding versions of maintenance scripts.

-   **Relevance in CI/CD:** Application code is pushed and merged
    between branches as it progresses from one environment to the next.

-   **Example:** Git, a popular version control system, with various
    offerings built on its technology.

CI/CD, coupled with version control, streamlines software development
and deployment, fostering a more efficient and reliable approach to
delivering code and infrastructure changes.

<br>

### 3) **Automation**

**Automation** and **orchestration** are often used interchangeably, but
they have distinct meanings and purposes within the context of managing
tasks and processes.

**Automation**

-   **Definition:** Automation involves the elimination of manual tasks
    and configuration changes by employing scripting mechanisms or
    infrastructure as code for individual tasks.

-   **Scope:** Focuses on automating individual, discrete tasks.

-   **Examples:**

    1.  Installing a patch on a single virtual machine.

    2.  Identifying and deleting expired data for compliance using
        lifecycle policies.

    3.  Deploying a new container version to an application (treated as
        a single task, even if it involves multiple resources).

Automation simplifies repetitive and manual processes, ensuring tasks
are performed consistently and efficiently. However, it operates at a
granular level, handling tasks one by one.

<br>

### 4) **Orchestration**

-   **Definition:** Orchestration is the coordination and management of
    multiple automated tasks or processes to achieve a larger, more
    complex goal or workflow.

-   **Scope:** Focuses on integrating and managing the flow of multiple
    tasks as a single, cohesive process.

-   **Examples:**

    -   Automating the provisioning and configuration of a multi-tier
        application stack.

    -   Managing the full lifecycle of a service, including scaling,
        load balancing, and failover.

    -   Automating the onboarding of a new employee, involving multiple
        IT and HR tasks.

Orchestration involves the coordination and sequencing of various
automated tasks to achieve a higher-level objective. It enables the
automation of end-to-end processes, ensuring tasks are executed in the
correct order and dependencies are met.


<br>


### 5) **Configuration Management**

-   **Definition:** Configuration management combines infrastructure as
    code, automation, and orchestration to manage and maintain
    resources, including tasks inside the operating system.

-   **Scope:** Encompasses resource provisioning, operational tasks,
    software updates, and configuration.

-   **Example:** Managing patches, kernel optimization, user account
    management, disk space management.

Configuration management software addresses operational tasks and
ensures resource configurations are maintained correctly.

**Relationship Summary**

-   **Infrastructure as Code** is a foundation for provisioning and
    managing resources but may not address operational tasks inside
    resources.

-   **Automation** simplifies specific tasks but may not orchestrate
    complex workflows or handle all operational tasks.

-   **Orchestration** coordinates multiple automated tasks into
    structured processes.

-   **Configuration Management** combines infrastructure as code,
    automation, and orchestration to manage resources comprehensively,
    including operational tasks.

Configuration management bridges the gap by encompassing all aspects of
resource management, making it a crucial component of DevOps strategies
for both on-premises and cloud environments.

<br>

## Business Continuity

<br>

### **1) Backup Types**

In the context of business continuity, different backup types are
essential for ensuring data availability and recovery during incidents
or outages. Let\'s explore these backup types:

**1. Full Backup**

-   **Definition:** A complete backup of an individual system captured
    at a specific point in time.

-   **Purpose:** Provides a comprehensive snapshot of data and system
    configuration.

-   **Characteristics:** Stands alone and can be used for a complete
    system restoration.

-   **Usage:** Typically performed periodically as a baseline backup.

**2. Incremental Backup**

-   **Definition:** Contains data that has changed since the last full
    backup or incremental backup.

-   **Purpose:** Efficiently captures changes made since the last backup
    by using the archive bit.

-   **Characteristics:** Requires a reference to the last full backup or
    incremental backup.

-   **Usage:** Performed frequently between full backups to minimize
    data loss during restoration.

**3. Snapshot**

-   **Definition:** An overarching term that encompasses either a full
    backup or a combination of full and incremental backups.

-   **Purpose:** Captures a point-in-time view of data and system state.

-   **Characteristics:** Can consist of a full backup taken at one point
    and multiple incremental backups.

-   **Usage:** Provides a comprehensive data set for restoration while
    allowing for smaller, more frequent backups.

**4. Synthetic Full Backup**

-   **Definition:** A consolidation of a full backup and all incremental
    backups taken since that full backup.

-   **Purpose:** Mimics the characteristics of a full backup while
    efficiently using incremental backups.

-   **Characteristics:** Appears as a single full backup, simplifying
    the restoration process.

-   **Usage:** Reduces the need to restore multiple incremental backups
    when a full restore is required.

**5. Differential Backup**

-   **Definition:** A combination of multiple backups, usually a full
    backup and a single incremental backup.

-   **Purpose:** Provides an efficient compromise between full and
    incremental backups for restoration.

-   **Characteristics:** Differential backups grow in size over time as
    changes accumulate.

-   **Usage:** Simplifies restoration compared to incremental backups
    but requires less storage compared to full backups.

<br>


### 2) **Backup Objects and Backup Targets in Business Continuity**

When implementing backup strategies for business continuity, it\'s
crucial to consider the various backup objects and backup targets
available. Each serves a specific purpose and offers distinct
advantages. Let\'s explore these elements:

#### **Backup Objects**

**1. System State Backup**

-   **Content:** Contains essential operating system configurations.

-   **Use Case:** Provides a fast and lightweight backup of the
    operating system, suitable for frequent backups throughout the day.

-   **Purpose:** Facilitates rapid system recovery by capturing critical
    OS settings.

**2. Application Level Backup**

-   **Content:** Includes a single program, its executables, and its
    configuration.

-   **Use Case:** Enables the quick restoration of specific
    applications, ideal for frequent backups.

-   **Purpose:** Ensures fast recovery of crucial applications and their
    settings.

**3. File System Backup**

-   **Content:** Encompasses user home directories, data sets, and file
    systems.

-   **Use Case:** Suitable for backing up large volumes of data, such as
    user files and data sets.

-   **Purpose:** Protects user data and file systems, distinct from the
    operating system.

**4. Database Dump**

-   **Content:** Typically a single file or a set of files containing
    SQL statements.

-   **Use Case:** Used for database backup, including entire databases,
    single tables, or specific data subsets.

-   **Purpose:** Facilitates database recovery and data integrity.

**5. Configuration File Backup**

-   **Content:** Backs up configuration files, playbooks, or templates.

-   **Use Case:** Typically involves backing up configuration settings
    for applications or infrastructure components.

-   **Purpose:** Ensures that critical configuration settings are
    preserved and can be quickly restored.


#### **Backup Targets**

**1. Tape**

-   **Advantages:** Cost-effective, high-capacity storage, durable over
    time.

-   **Disadvantages:** Slow for restores, offline storage may lead to
    long latency.

**2. Disk**

-   **Advantages:** Fast, easy for restores, movable and storable.

-   **Disadvantages:** May require more significant upfront investment
    for storage infrastructure.

**3. Cloud**

-   **Advantages:** Scalable, cost-effective, no significant upfront
    payment, easy expansion and maintenance.

-   **Disadvantages:** Data transfer costs may apply when copying data
    to the cloud.

**4. Object Store**

-   **Advantages:** Scalable, cost-effective, suitable for write-once,
    read-many (WORM) data, no upfront investment.

-   **Disadvantages:** None specified.


<br>
 
### 3) **Backup and Restore Policies, Workflow, and the 3-2-1 Backup Rule**

To effectively manage backups and restores across an organization or
enterprise, you\'ll need orchestration and well-defined backup and
restore policies. These policies require documentation, including
schedules, targets, retention periods, and destinations. Here\'s a
breakdown of key considerations:

**Backup and Restore Policies**

-   **Schedules:** Determine how often resources need to be backed up
    (e.g., daily, monthly).

-   **Targets:** Specify where backups will be stored (e.g., local data
    center, different data center, or a cloud region).

-   **Retention:** Define how long backups should be retained,
    considering compliance requirements.

-   **Destination:** Determine the location or storage medium for
    backups, ensuring data integrity and accessibility.

**Backup Workflow (Example using AWS Backup)**

1.  **Resource Tagging:** Tag various resources with metadata key-value
    pairs to associate them and apply the same backup plan.

2.  **Backup Vault Creation:** Create a backup vault to serve as the
    destination for all backups. Backup vaults hold restore points and
    allow resource-level access control.

3.  **Permissions Policy:** Establish permissions policies on the vault
    to control access and ensure security.

4.  **Backup Plan:** Create a backup plan that integrates resources,
    backup jobs, and vaults. Configure the plan to execute on a
    specified schedule.

5.  **Backup Initiation:** When a backup job is initiated based on the
    schedule, it discovers all resources with a particular tag and
    starts the backup process.

6.  **Restore Points:** Each backup generates restore points, which are
    placed into the vault. Restore points support point-in-time
    recovery, allowing restoration from any point within the retention
    period.

#### **The 3-2-1 Backup Rule**

The ***3-2-1 backup rule*** is a widely recognized guideline for data
backup and business continuity:

-   **3 Copies:** Maintain at least three copies of your data. This
    includes the original data and two backup copies.

-   **2 Different Media Types:** Store the backup copies on at least two
    different types of media or storage devices (e.g., disk, tape,
    cloud).

-   **1 Offsite Copy:** Keep one copy of the data offsite, away from the
    primary location, to protect against site-specific disasters.

Following the 3-2-1 backup rule ensures redundancy, data availability,
and recovery options during unexpected incidents or outages. It is a
fundamental principle of data protection and business continuity
planning.


<br>

### 4) **Data Restore Methods and Key Terms in Disaster Recovery**

When it comes to restoring data, it\'s essential to understand key terms
related to disaster recovery and service level agreements (SLAs). These
terms help define recovery objectives and guide the restoration process:

**Key Terms:**

**1. SLA (Service Level Agreement)**

-   **Definition:** A formal agreement that outlines the expected level
    of service, including uptime and acceptable downtime.

-   **Purpose:** Provides a clear understanding of performance
    expectations and commitments.

**2. RTO (Recovery Time Objective)**

-   **Definition:** The ***maximum allowable downtime*** during a system
    outage or disaster. It specifies how quickly systems must be
    restored to normal operation.

-   **Purpose:** Helps organizations determine the time frame within
    which critical services need to be recovered.

**3. RPO (Recovery Point Objective)**

-   **Definition:** The ***maximum amount of data loss*** an organization can
    tolerate during an incident. It represents the point in time to
    which data must be recovered.

-   **Purpose:** Establishes the acceptable data loss threshold, guiding
    backup and recovery strategies.

**4. MTTR (Mean Time to Recovery)**

-   **Definition:** The ***average time it takes to recover*** from an
    incident or failure. It calculates the expected recovery duration
    based on historical data.

-   **Purpose:** Offers insight into the efficiency of recovery
    processes and aids in cost-benefit analysis.

**Restore Methods and Benefits:**

**1. In-Place Overwrite or Restore**

-   **Method:** Recover 100% of the data to the original location,
    overwriting existing data.

-   **Benefits:** Useful for addressing data corruption or compromised
    data quickly by restoring the entire dataset.

**2. Side-by-Side Restore**

-   **Method:** Restore the original data to the same server but in a
    slightly different location for side-to-side comparisons.

-   **Benefits:** Facilitates data verification and comparison while
    retaining the original data.

**3. Alternate Location Restore**

-   **Method:** Place the entire dataset on a separate server for
    comparisons, data copies, or redundancy.

-   **Benefits:** Enables data redundancy, testing, or maintaining a
    copy of the data without affecting the original.

**4. File Restore**

-   **Method:** Restore specific files or data segments rather than the
    entire dataset.

-   **Benefits:** Useful for situations where only specific files need
    recovery, offering flexibility and speed.

**5. Snapshot Restore**

-   **Method:** Replace an entire server or data volume with a snapshot
    of a previous state.

-   **Benefits:** Provides rapid restoration of an entire system or data
    volume, often faster than other methods.


<br>

### 5) **Disaster Recovery Requirements**

Business continuity encompasses several crucial factors, including
resiliency, availability, and disaster recovery. In this discussion,
we\'ll focus on disaster recovery, which involves specific terms and
concepts aimed at minimizing downtime and data loss during incidents or
disasters.

**Key Disaster Recovery Terms:**

**1. RPO (Recovery Point Objective)**

-   **Definition:** The maximum acceptable amount of data loss, measured
    in time, that an organization can tolerate during a disaster.

-   Separate from backup RPO.

**2. RTO (Recovery Time Objective)**

-   **Definition:** The maximum acceptable length of time an
    organization can endure system downtime during a disaster.

-   Separate from backup RTO.

**3. SLA (Service Level Agreement)**

-   Specific to DR (not just minor outages)
-   Applies to control plane and data plane separately. 
-   SLA Sources
    - CSP
    - Software vendor
    - Hardware vendor
    - Physical facility owner
    - Internet provider 

**Disaster Recovery Planning Considerations:**

1.  **Geographical Stability:** Separating infrastructure across
    multiple geographical locations to minimize the impact of local
    disasters on overall operations.

2.  **Environmental Stability:** Addressing potential environmental
    hazards within a single data center, such as power loss or cooling
    failures, to ensure continuous operations.

3.  **Power Availability:** Ensuring that individual servers and racks
    can maintain power even when others are affected, reducing the risk
    of widespread outages.

4.  **Internet Access:** Maintaining internet connectivity, as it plays
    a crucial role in communication and disaster recovery processes.

**Disaster Recovery Site Types:**

Disaster recovery sites are essential for ensuring business continuity
during and after disasters. There are three common types:

**1. Hot Disaster Recovery Site**

-   **Description:** An exact replica of the production data center,
    with full capacity to handle all business processes and data loads.

-   **Benefits:** Offers immediate failover capabilities with minimal
    downtime and data loss.

-   **Trade-offs:** Higher costs due to maintaining duplicate
    infrastructure and services.

**2. Warm Disaster Recovery Site**

-   **Description:** A site with allocated office and infrastructure
    space, but limited capacity to handle all business processes.

-   **Benefits:** Faster failover compared to cold sites, with reduced
    infrastructure costs.

-   **Trade-offs:** Longer recovery times and potential data loss due to
    limited capacity.

**3. Cold Disaster Recovery Site**

-   **Description:** A site with office space and data center facilities
    but no infrastructure.

-   **Benefits:** Lower infrastructure costs compared to hot and warm
    sites.

-   **Trade-offs:** Significantly longer failover times as
    infrastructure needs to be procured and set up during a disaster.

<br>

### 6) **Disaster Recovery Strategies**

In the context of AWS, there are four primary disaster recovery (DR)
implementation strategies: Backup and Restore, Pilot Light, Warm
Standby, and Active-Active. Each strategy has its unique purpose,
trade-offs, and objectives. Let\'s explore these strategies and their
associated metrics:

**1. Backup and Restore:**

-   **Preparation Steps:**

    -   Point-in-time backups of data from the corporate data center to
        AWS.

    -   Creation of infrastructure images.

    -   Setup of the Virtual Private Cloud (VPC) within AWS.

-   **Execution Steps (During Disaster):**

    -   Provisioning load balancers, DNS, compute resources, and
        database resources.

    -   Restoring data.

    -   DNS cutover and configuration of CI/CD and monitoring.

-   **Metrics:**

    -   **RTO (Recovery Time Objective):** Less than 24 hours.

    -   **RPO (Recovery Point Objective):** Depends on backup frequency, usually Hours.

**2. Pilot Light:**

-   **Additional Preparation Steps:**

    -   Provisioning of database resources in AWS.

    -   Implementation of one-way replication from on-premises data
        center to AWS.

-   **Execution Steps (During Disaster):**

    -   Launch compute resources.

    -   Scale database resources.

    -   Promote database replica.

    -   DNS cutover, CI/CD configuration, and monitoring.

-   **Metrics:**

    -   **RTO:** Hours.

    -   **RPO:** Minutes.

**3. Warm Standby:**

-   **Additional Preparation Steps:**

    -   Configure two-way replication or use one-way replication with
        application adaptation.

    -   Configure DNS for partial traffic routing to AWS for
        infrastructure validation.

-   **Execution Steps (During Disaster):**

    -   Fully scale application and database.

    -   Complete DNS failover.

-   **Metrics:**

    -   **RTO:** Minutes.

    -   **RPO:** Seconds.

**4. Active-Active:**

-   **Additional Preparation Steps:**

    -   Similar to Warm Standby but fully scaled on both sides.

    -   Configure DNS with health checks for equal traffic distribution.

-   **Execution Steps (During Disaster):**

    -   DNS failover (can be automated).

-   **Metrics:**

    -   **RTO:** Near-zero.

    -   **RPO:** Near-zero.

**Key Trade-offs:**

-   **Cost of Implementation:** Increases from left to right (Backup and
    Restore being the least costly).

-   **Operational Overhead:** Increases from left to right
    (Active-Active requires significant operational maintenance).

<br>


### 7) **Disaster Recovery Documentation Essentials**

-   Disaster Recovery Kit Comprises crucial documents for effective disaster recovery
        execution.

**Contents of a DR Kit:**

1.  **Playbooks:**

    -   Specific procedures based on scenario possibilities.

    -   Different sets of tasks for various types of disaster recovery.

2.  **Notification Chart:**

    -   Informed principles and notification avenues.

    -   Reference from incident management and high availability
        concepts.

3.  **Decision Tree:**

    -   List of responsible individuals for disaster recovery
        decision-making.

    -   Identifies scenarios and playbooks to execute.

4.  **Emergency Contacts:**

    -   Vendors and providers to contact during a disaster.

    -   Critical for potential involvement and assistance.

5.  **Network Diagrams:**

    -   Up-to-date diagrams outlining the network structure.

    -   Crucial for disaster recovery planning and execution.

**Playbooks Specifics:**

-   Tailored based on the type of emergency:

    -   Environmental disaster.

    -   Cybersecurity compromise.

    -   Social engineering attack.

    -   Other relevant scenarios based on organizational needs.

