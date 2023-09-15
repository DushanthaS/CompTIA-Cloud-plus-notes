# Operations and Support  - Part 1

## Cloud Monitoring Operations

### **1) Cloud Monitoring and Logging**

 There are six sub-points to cover in this domain:

**Subpoints**

1.  **Configure Monitoring, Logging, and Alerting:** To maintain
    operational status.

2.  **Efficient Operation:** Optimize cloud environments.

3.  **Automation and Orchestration:** Apply proper techniques.

4.  **Backup and Restore Operations:** Perform adequately.

5.  **Disaster Recovery Tasks:** Implement as needed.

The discussion begins with an emphasis on logging and its increasing
significance compared to metrics in monitoring. The location of logs
varies between Linux and Windows operating systems:

-   On Linux, authentication logs are stored in **/var/log/secure**,
    while system logs are in **/var/log**.

-   Windows stores authentication logs in the \'Event Viewer\' under the
    \'Security\' log.

-   File access logs aren\'t readily available on Linux by default but
    can be found in the \'Security\' log on Windows.

For specific application logs:

-   On Linux running Apache, you\'d find them in **/var/log/apache2**.

-   On Windows, these logs are in the \'Event Viewer\' under the
    \'Application\' log.

**Aggregating Logs**

In large data centers with numerous servers, it\'s crucial to collect
and aggregate logs centrally. On Linux, the aggregator tool used is
\'syslog,\' configured through **rsyslog.conf** to forward logs to an
external server. On Windows, \'Event Viewer\' can be configured for
similar log forwarding.

**Log Severity Levels**

Logs come with severity levels associated primarily with syslog:

-   **Emergency (0):** Indicates the system is unusable and requires
    immediate action.

-   **Alert (1):** Immediate action is necessary.

-   **Critical (2):** The system may or may not be usable, but issues
    lean towards \"not.\"

-   **Error (3):** Denotes various error conditions, such as CPU,
    kernel, application, or memory issues.

-   **Warning (4):** Less severe, suggesting the system is likely still
    usable.

-   **Notice (5):** Requires investigation but no immediate action.

-   **Information (6):** Represents information-only events that may or
    may not signify a problem.

-   **Debug (7):** Debug notices typically enabled for specific
    troubleshooting purposes.

Severity levels four and higher indicate that the system is still
usable, while levels zero to three demand immediate attention.

**Audit Logs**

Audit logs differ from regular logs, primarily serving compliance
purposes. Each log entry comprises four sections: event owner,
timestamp, details, and effects or ramifications. Enabling audit logs
alongside regular system logs aids in compliance achievement, root cause
analysis, risk management, and troubleshooting.
<br>


### **2) Traditional Monitoring for Availability**

Traditional monitoring strategies primarily aim to assess system
availability, helping to determine uptime and downtime metrics. When
establishing Service Level Agreements (SLAs), it\'s essential to grasp
the expected uptime and what\'s realistically achievable based on the
deployed architecture.

#### Uptime Percentages and Downtime

-   An SLA with 90% uptime corresponds to 1/9.

-   This translates to a permissible downtime of up to three days and
    one hour per month within the SLA.

-   As uptime percentages increase (adding nines), downtime decreases:

    -   Two nines (99% uptime) allow for 7 hours and 15 minutes of
        downtime.

    -   Three nines (99.9%) permit 43 minutes of downtime.

    -   Four nines (99.99%) allow only 4 minutes of downtime.

    -   Five nines of uptime (99.999%) allow a mere 26 seconds of
        monthly downtime.

#### Architectural Considerations

-   For architectural design, it\'s crucial to align uptime goals with
    practical infrastructure capabilities.

-   Marketing-driven uptime targets might exceed what the infrastructure
    can support.

-   Note that increasing uptime beyond two or three nines significantly
    escalates infrastructure costs.

#### Factors Impacting Availability

Several factors can cause unavailability:

1.  **Hardware Failures:** Overlying hardware failures can disrupt
    services.

2.  **Application-Level Failures:** Failures in upstream or downstream
    dependencies.

3.  **Performance Thresholds:** Exceeding performance thresholds with
    diminishing returns.

4.  **Maintenance Windows:** Scheduled maintenance activities like patch
    installations or updates.

5.  **Non-Specific Dependency Failures:** Unpredictable dependency
    failures.

#### Configuring Monitoring for Availability

To determine availability and maintain a performance baseline:

-   Sufficient monitoring should be configured to establish a normal
    behavior baseline.

-   This baseline serves as the foundation for all monitoring
    activities.

-   Thresholds for deviations from the normal baseline are set for
    alerting purposes.

-   Utilization thresholds can inform capacity planning efforts based on
    performance data.



#### Configuration of Thresholds and Alerting

Configuring thresholds and alerts varies based on the monitoring
software or cloud provider ecosystem in use. However, the strategies for
alerting are generally consistent.

#### Types of Alerts

1.  **Performance Alerts:** These focus on key performance indicators
    (KPIs) such as CPU percentage, request per second, or latency.

2.  **Utilization Alerts:** These are based on resource utilization and
    typically don\'t cause immediate emergencies or outages unless
    utilization reaches 100%. KPIs are based on a percentage of total
    capacity.

3.  **Availability Alerts:** These are centered around uptime and the
    user experience. Metrics might include the number of transactions
    over a period or the revenue generated by the application.

#### Notification Methods

Alerts need to be routed to appropriate channels for action:

-   **Email:** A popular but less responsive method for alerting. It\'s
    not as effective in achieving quick issue mitigation.

-   **Webhooks and API Destinations:** These can automate trouble ticket
    creation, enhancing incident management.

-   **Scaling Infrastructure:** For an active response, infrastructure
    can be scaled automatically when a threshold is exceeded. This helps
    mitigate issues by adding or removing resources dynamically.

-   **Hardware or Virtual Machine Recovery:** In cases of
    unavailability, hardware or virtual machines can be recovered or
    replaced automatically.

-   **Execution of Code:** Complex mitigation strategies may involve
    executing code for specific business logic.

#### Alert Handling Based on Threshold Types

-   **Performance Thresholds:** These usually trigger notifications or
    automated scaling actions.

-   **Utilization Thresholds:** Similar to performance thresholds, they
    may also involve custom code execution to adjust limits as needed.

-   **Availability Thresholds:** The handling of these alerts can be a
    combination of the methods mentioned, depending on the nature of the
    outage or user experience issue being encountered.

<br>

### **3) Lifecycle Management of Applications**

Effectively managing and monitoring the lifecycle of an application is
of paramount importance. To achieve this, it\'s crucial to have a
roadmap that outlines the future direction of the application. This
roadmap tracks the various lifecycle phases of the underlying hardware,
software, and associated services. While these components can have
separate roadmaps, they often use Gantt charts to visualize dependencies
and compare various systems.

### Four Phases of Lifecycle Management

1.  **Development Phase:**

    -   This phase encompasses applications in the development
        environment, including beta applications actively undergoing
        code development.

    -   It also includes the development of the underlying architecture.

2.  **Deployment Phase:**

    -   In this phase, resources are being provisioned, and the
        application is prepared for deployment.

    -   There may be multiple environments in the deployment process,
        with one closely resembling the production environment.

    -   OS images and software versions used in this phase typically
        include stable or Long-Term Support (LTS) releases.

    -   Automation plays a critical role in ensuring the quality of
        deployments and enabling reproducibility.

3.  **Maintenance Phase:**

    -   After reaching the production environment, the focus shifts to
        maintaining the application\'s availability.

    -   Maintenance activities may include migration to a different
        cloud provider or data center, as well as scalability
        adjustments (vertical or horizontal).

    -   Unfortunately, many organizations stop the roadmap at this
        phase, missing a crucial final step.

4.  **Deprecation Phase:**

    -   The deprecation phase occurs when the application reaches its
        End of Life (EOL).

    -   During this phase, changes or deployments to the application are
        discouraged.

    -   The decision to deprecate an application can be made by either
        the vendor or the customer, depending on ownership.

### Importance of Deprecation

The deprecation phase is of utmost importance but often overlooked. It
signifies the end of an application\'s lifecycle and signals the need to
transition to newer solutions or technologies. Properly managing this
phase is essential for maintaining a secure and efficient IT ecosystem.

<br>

### **4) Change Management and Asset Management in Application Lifecycle**

Application lifecycle management primarily involves planned changes with
detailed understanding. However, unforeseen events require a different
approach, and that\'s where change management plays a crucial role.
Change management has its own lifecycle:

### Change Management Lifecycle

1.  **Proposing and Planning the Change:**

    -   Driven by business needs and the proposed solution to address
        those needs.

2.  **Approvals:**

    -   Gaining necessary approvals, including budgeting if the change
        scope requires it.

    -   Planning schedules and resource allocation, including hardware,
        software, and personnel.

3.  **Development Phase:**

    -   Developing and testing the change in a non-production
        environment.

4.  **Deployment:**

    -   Implementing the change in the production environment as per the
        approved schedule.

    -   Thoroughly testing to ensure effectiveness and non-disruption of
        existing functionality.

5.  **Close Phase:**

    -   Completing documentation for the change.

    -   Transitioning the change into the maintenance phase alongside
        the application.

<br>

### **5) Benefits of Effective Change Management**

A well-designed change management structure offers several benefits:

-   Reduced infrastructure costs due to planned and approved changes.

-   Enhanced overall process efficiency.

-   Improved organizational agility with efficient change
    implementation.

-   Increased operational flexibility.

### Asset Management

Asset management involves auditing, documenting, and managing assets
effectively, offering several advantages:

-   More effective budget allocation by avoiding redundant resource
    purchases.

-   Identification of systems in need of updates, monitoring, or
    replacement.

-   Significant contributions to security and compliance.

### Cloud Service Provider Asset Management

Managing assets in a cloud service provider context requires different
methods:

-   Managing subscriptions for infrastructure, platform, or
    software-as-a-service offerings.

-   Addressing complexities related to self-service environments.

-   Ensuring proper tracking, monitoring, and cost attribution in
    decentralized deployments.

### Configuration Management Database (CMDB)

-   Bare metal resource inventory is relatively simple as additions and
    removals align with hardware purchases or retirements.

-   Virtual machines, especially in self-service environments, pose
    greater challenges.

-   A cloud CMDB shifts focus from individual resources to fleets, as
    fleets can expand and contract with scalability demands.

### Patch Management in Infrastructure

Patch management is a time-consuming but critical task for operations
teams. Regular patching of various components, including bare metal,
firmware, and virtual machines, serves several purposes:

### Reasons for Regular Patching

1.  **Fixing Security Flaws:** Regular patches are deployed to address
    security vulnerabilities, reducing the risk of exploitation.

2.  **Resolving Service/Application Bugs:** Patches fix bugs and issues,
    especially at the operating system level, improving stability and
    performance.

3.  **Feature Releases:** Patches can include feature releases that
    enhance performance or add new functionality.

4.  **Feature Enhancements:** Some patches may provide feature
    enhancements beyond bug fixes.

### Deployment Targets for Patches

Patches are deployed to various parts of the infrastructure:

1.  **Hypervisor Software:** The hypervisor itself requires periodic
    patching to maintain security and stability.

2.  **Virtual Machines:** Virtual machines need patching, but the scope
    depends on the operating system type, version, and existing patch
    level.

3.  **Virtual Appliances:** Patches can be deployed to virtual
    appliances, which often run as virtual machines without a full
    operating system.

4.  **Network Components:** Patches are essential for network components
    like firewalls, routers, and switches.

5.  **Applications:** Patches may be required for applications running
    on top of other resources.

6.  **Storage Resources:** Storage resources, including Network-Attached
    Storage (NAS) systems with embedded operating systems, require
    patching.

7.  **Firmware:** Patches are necessary for storage and networking
    firmware.

8.  **Internal Software:** Internal software applications may need
    patching to address vulnerabilities or enhance functionality.

9.  **Operating Systems:** The operating systems themselves may require
    specific patches.

### Patching Policies and Strategies

1.  **N Minus One Policy:** Deploying the second most recent patch
    instead of the latest one to ensure stability. This minimizes the
    risk of deploying inadequately tested patches.

2.  **Rollback Plans:** Preparing for the possibility that a patch
    deployment goes awry. Rollback plans are crucial, especially if a
    patch breaks critical functionality. Rollback from an application
    perspective is often feasible, but for OS updates, it\'s challenging
    and may require restoring from backups or redeploying virtual
    machines from images.

<br>

### **6) Application Upgrade Methods**

Deploying updates to an application while maintaining availability for
end-users can be complex but essential. Three different methods for
upgrading an application are commonly used: in-place (rolling) upgrades,
blue-green upgrades, and canary upgrades.

### In-Place (Rolling) Upgrades

-   Deregister one resource at a time from the load balancer.

-   Perform the application update on the deregistered instance,
    resulting in the updated version.

-   Register the updated instance with the load balancer.

-   Wait until it\'s in service and move on to the next resource.

-   Repeat the process until all instances are upgraded.

-   This method ensures minimal impact on the end-user experience since
    the application remains available throughout the upgrade.

### Blue-Green Upgrades

-   Utilize two separate copies of the application fleet: the old
    version (blue) and the updated version (green).

-   Employ weighted routing records in DNS, e.g., using Route 53 in AWS,
    to control traffic distribution.

-   Initially, assign a 100 weight to the blue version to direct 100% of
    the traffic there.

-   Deploy an entirely new infrastructure for the green version.

-   To test the new infrastructure, set a weighted routing record with a
    zero weight.

-   Gradually adjust the weights to redirect more traffic to the green
    version as it is validated.

-   Eventually, make the blue version weight zero and the green version
    weight 100% to complete the upgrade.

-   Afterward, the old version\'s infrastructure can be de-provisioned,
    leaving only the updated version.

-   Blue-green deployments minimize user disruption during the upgrade
    process.

### Canary Upgrades

-   Isolate a single resource from the load balancer, referred to as the
    \"canary instance.\"

-   Update the application on the canary instance and return it to
    service.

-   Observe the behavior of the canary instance, ensuring it handles
    traffic appropriately.

-   Perform comprehensive validation without making changes to the rest
    of the infrastructure.

-   If the new application version is deemed satisfactory, proceed with
    one of the other deployment methods.

-   If issues arise, quickly revert the canary instance to the previous
    version without affecting other resources.

-   Canary updates allow for a controlled validation process without
    impacting the overall user experience.

<br>

### **7) Dashboard and Reporting**

In the cloud environment, dashboards and reporting take on additional
flexibility and importance. Beyond the traditional performance and
availability metrics, cloud-based dashboards offer insights into cost
management and resource allocation. Here\'s an overview:

### Resource Tagging and Labeling

-   Assigning tags or labels to cloud resources.

-   Tags can be contributed to by different parts of the organization.

-   Finance focuses on tags like cost centers, project IDs, and
    executive sponsors.

-   Technology teams contribute tags like environments, application
    tiers, audit timestamps, and application versions.

-   AWS provides tag policies to enforce the presence of tags on
    resources.

### Chargeback vs Showback

-   Understanding cloud spending and allocating costs to business value.

-   Tagging and labeling enable cost tracking based on organizational
    criteria.

-   Dashboards help visualize spending patterns and resource allocation.

-   Reaction to cost overruns includes chargeback (billing other
    departments for their resource usage) or showback (providing cost
    insights without actual charges).

### Operational Dashboards

1.  **Elasticity and Scaling Dashboards:**

    -   Visualize how resources dynamically change over time.

    -   Track auto-scaling events and resource adjustments.

2.  **Connectivity Dashboards:**

    -   Monitor the ability to connect to resources and applications
        based on location.

3.  **Network Performance Dashboards:**

    -   Monitor latency and throughput to ensure optimal network
        performance.

4.  **Availability and Health Dashboards:**

    -   Crucial for maintaining Service Level Agreements (SLAs) and
        ensuring a positive user experience.

    -   Provides insights into resource availability and overall health.

5.  **Incident Dashboards:**

    -   Track and respond to incidents, including outages and security
        events.

6.  **Resource Utilization Dashboards:**

    -   Essential for infrastructure teams.

    -   Helps determine whether scaling or capacity planning is
        required.

<br><br>

## Cloud Optimization

Optimizing infrastructure, including the cloud, involves right sizing
resources and implementing effective scaling mechanisms. Cloud
infrastructure offers distinct advantages for both right sizing and
scaling:

### **1) Right Sizing Strategies**

-   Right sizing means adjusting resource allocation to meet actual
    needs.

-   In the cloud, right sizing is advantageous due to the absence of
    hardware purchase requirements.

-   Cloud resources can be easily modified to meet performance demands
    without over-provisioning.

-   Reducing resource usage can lead to cost savings, a benefit not
    feasible in on-premises infrastructure.

#### Scaling Mechanisms

1.  **Vertical Scaling:**

    -   Within a single server or virtual machine, it involves adding or
        removing memory, CPU, disk, or network throughput.

    -   May require an interruption of service, impacting availability.

    -   Appropriate for fine-tuning resource allocation when right
        sizing within a VM.

2.  **Horizontal Scaling:**

    -   Scaling by adding or removing entire virtual machines (or
        duplicating resources if not using VMs).

    -   Ideal for cloud infrastructure and suits automation.

    -   Does not usually cause application outages, enhancing
        infrastructure resilience.

    -   Commonly leads to auto scaling.

3.  **Auto Scaling:**

    -   A form of horizontal scaling where resources are adjusted
        automatically based on metrics (e.g., performance, usability,
        availability).

    -   Requires automation and operates in both directions:

        -   Scaling out to meet increased demand for performance or
            availability.

        -   Scaling in to reduce costs when resources are underutilized.

    -   Does not require service interruptions.

4.  **Cloud Bursting:**

    -   Horizontal scaling into a public cloud when on-premises
        resources are exhausted.

    -   Activated when on-premises capacity is unavailable.

    -   May involve service interruptions, although not guaranteed.


### **2) Optimization in the Cloud: Compute, GPUs, Memory, and More**

Optimizing resources in the cloud is an ongoing task, involving various
aspects such as cost modeling, performance testing, and fine-tuning.
Here are some strategies and considerations for optimizing cloud
resources:

### Compute Resource Optimization

-   **Cost Modeling:** Choose an initial virtual machine size, conduct
    performance tests, and determine the threshold for optimal
    utilization. If the initial choice falls short, explore other sizing
    options iteratively until the correct resource size is found.

-   **Regular Reevaluation:** Resource optimization is not a one-time
    task. Periodically revisit and adjust resource sizes to accommodate
    changing requirements and workloads.

### Performance Evaluation in AWS

-   **OS Images:** Ensure you have the correct OS images or templates
    for different CPU architectures (e.g., x86 and arm64) ready.

-   **Infrastructure as Code (IaC):** Create CloudFormation templates
    with mappings between OS images and instance types/sizes.

-   **Shell Scripts:** Use scripts (e.g., bash or PowerShell) to loop
    through desired instance types, launch them using IaC, and execute
    performance tests. Collect performance metrics in centralized
    storage (e.g., CloudWatch for numeric metrics and S3 for text-based
    output).

### GPU Optimization

-   **Disabling Autoboost:** Force GPUs into their highest performance
    mode continuously for improved performance.

-   **Maximizing Clock Speed:** Configure GPUs to run at maximum clock
    speed to enhance performance.

-   **Shared vs. Pass-through:** Consider switching from shared GPU to
    pass-through mode if shared GPU resources do not meet performance
    expectations.

### Memory Optimization

-   **Resizing VMs:** In public clouds, resize VMs or change their
    family to optimize for memory over virtual CPU. Ideal for
    memory-intensive workloads, databases, ETL jobs, and in-memory
    caching systems.

### Driver and Firmware Updates

-   **Stay Up to Date:** Ensure drivers and firmware are updated within
    a certain tolerance. Consider an N-1 strategy for stability and
    performance.

-   **Vendor-Supplied Drivers:** Prefer vendor-supplied drivers over
    generic ones, as they often offer higher performance.

### Container Workloads

-   **Standardized Virtualization:** Running containers on virtual
    machines is a valid approach, especially in public clouds.

-   **Container Engines:** Install a container engine on top of the OS
    to run containers.

-   **Multiple Runtimes:** You can have multiple container runtimes on
    the same OS without conflicts.

-   **Resource Configuration:** Configure each application container
    with unique resource allocations based on specific requirements.
<br>
<br>


### **3) Storage Optimization Considerations**

-   Optimizing storage involves various factors:

    -   Understanding the workload\'s storage requirements is crucial.

    -   Considerations include:

        -   Type of storage needed (block, file, or object).

        -   Storage tiers (hot, cold, archival).

        -   Automatic performance optimization as data grows.

        -   Throughput and IOPS provisioning (manual or static).

        -   Thick or thin provisioning (scalability vs. manual changes).

        -   Upper capacity limits for the chosen storage service.

### Evaluating Block Storage Performance in AWS

-   Example: Evaluating block storage options for performance in AWS.

-   Approach:

    -   Create a shell script using AWS CLI to launch identical
        instances.

    -   Install an agent for pushing performance metrics to CloudWatch.

    -   Provision different volumes (types, sizes) and attach them to
        instances.

-   Automation:

    -   Volume attachment generates log entries in CloudTrail.

    -   Utilize EventBridge to capture events and trigger Lambda
        functions.

-   Performance Testing:

    -   Lambda invokes performance tests using Systems Manager Run
        Command.

    -   Tests can run in parallel for efficient resource optimization.

-   Monitoring:

    -   Output sent to CloudWatch Logs for instant analysis.

    -   Performance metrics available in CloudWatch dashboard during
        testing.

### **4) Network Optimization Considerations**

-   Optimizing the network involves delving into various details,
    considering factors such as node-to-node and network-to-network
    traffic.

-   Key Considerations:

    -   Configuration of individual resources.

    -   Physical placement of resources.

-   Diverse Optimization Possibilities:

    -   Corporate office to office traffic.

    -   Corporate office to public cloud.

    -   Corporate office to private cloud.

    -   Home office to corporate office or public cloud.

    -   Customer network to corporate office or cloud.

    -   Server to server traffic.

-   Customized Strategies:

    -   Each scenario requires specific parameters and optimization
        strategies.

### Basic Network Configuration Tips

-   Configuring network interfaces:

    -   Ensure proper configuration at the operating system level.

    -   Adjust parameters to optimize for the specific traffic type.

-   Example: Implementing jumbo frames:

    -   Increase data passed per TCP packet for efficient throughput
        with larger data sizes.

-   Placement Strategies:

    -   Consider placing servers in the same data segment.

    -   Note that the same network segment can span significant
        distances in different data centers.

-   Network Interface Teaming/Bonding:

    -   Combine multiple network interfaces to achieve aggregate
        throughput.

<br>

### **5) Cloud Resource Placement Strategies**

-   Resource placement in the cloud is a critical architectural decision
    impacting network performance.

-   Consideration of Choices:

    -   Multiple virtual machines on the same physical server:

        -   Affinity-based choice.

    -   Multiple servers in the same rack or data center:

        -   Affinity strategy.

    -   Multiple virtual machines in the same zone (public cloud):

        -   Not necessarily affinity, but can maximize performance.

    -   Prioritizing anti-affinity or resilience:

        -   Place servers in different data centers.

        -   In a public cloud, use different zones or regions.

-   Trade-offs:

    -   Choices come with trade-offs.

    -   Greater physical distance between resources typically results in
        lower performance.

    -   Optimization can focus on availability or resilience, not just
        performance.
