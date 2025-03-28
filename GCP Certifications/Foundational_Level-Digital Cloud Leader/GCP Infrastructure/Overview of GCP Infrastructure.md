# Basics of Cloud Computing

# What is Cloud Computing
- Cloud computing is a transformative technology that enables the delivery of computing services—including servers, storage, databases, networking, software, analytics, and intelligence—over the internet, or "the cloud."
- This model allows businesses and individuals to access and use IT resources on-demand, without the need for owning and maintaining physical infrastructure.
- Cloud computing offers unparalleled scalability, flexibility, and cost-efficiency, as users can scale resources up or down based on their needs and only pay for what they use.
- It encompasses various service models such as Infrastructure as a Service (IaaS), Platform as a Service (PaaS), and Software as a Service (SaaS), each catering to different aspects of IT needs.
- IaaS provides virtualized computing resources, PaaS offers a platform for developing and deploying applications, and SaaS delivers software applications over the internet.
- Additionally, cloud computing can be deployed in different environments, including public, private, and hybrid clouds, each offering unique benefits and use cases.
- Public clouds are managed by third-party providers and offer shared resources, private clouds are dedicated to a single organization for enhanced security and control, and hybrid clouds combine both to provide greater flexibility and optimization.
- By leveraging cloud computing, organizations can innovate faster, improve operational efficiency, and gain a competitive edge in the digital landscape.

# Public Cloud Providers
- Public cloud, private cloud, and hybrid cloud computing represent three distinct models of cloud deployment, each offering unique benefits and use cases for businesses.
- Public cloud services are provided by third-party vendors over the internet, offering scalable and cost-effective solutions where resources are shared among multiple organizations.
- This model is ideal for businesses looking to reduce IT costs and leverage the latest technologies without the need for significant upfront investments. 
- Public cloud service providers offer scalable and cost-effective cloud solutions where resources are shared among multiple organizations. Here are a few examples:
  - Amazon Web Services (AWS): One of the largest and most comprehensive cloud platforms, offering a wide range of services including computing power, storage, 
    and databases1.
  - Microsoft Azure: Provides a variety of cloud services, including those for computing, analytics, storage, and networking1.
  - Google Cloud Platform (GCP): Offers services for computing, data storage, data analytics, and machine learning1.
  - IBM Cloud: Provides IaaS, PaaS, and SaaS solutions, with a strong focus on AI and machine learning1.
  - Oracle Cloud: Known for its database services, Oracle Cloud also offers a range of cloud solutions for enterprise applications1.

# Private Cloud Providers
- Private cloud, on the other hand, is dedicated to a single organization, providing enhanced security, control, and customization.
- It is often hosted on-premises or in a dedicated data center, making it suitable for businesses with stringent regulatory requirements or those needing high 
  levels of data privacy.
- Private cloud service providers offer dedicated cloud environments for a single organization, providing enhanced security and control.
- Here are a few examples:
  - VMware: Offers private cloud solutions that can be deployed on-premises or in a hosted environment2.
  - Amazon Web Services (AWS): Provides private cloud solutions through AWS Outposts, which bring AWS infrastructure and services to on-premises locations2.
  - Microsoft Azure: Offers Azure Stack, a private cloud solution that extends Azure services to on-premises environments2.
  - Google Cloud Platform (GCP): Provides Anthos, a platform for managing applications across hybrid and multi-cloud environments2.
  - IBM Cloud: Offers private cloud solutions with a focus on security and compliance2. 

# Hybrid Cloud
Hybrid cloud combines the best of both worlds, integrating public and private cloud environments to allow data and applications to move seamlessly between them. This model offers greater flexibility and optimization of existing infrastructure, enabling businesses to scale workloads across different environments based on their specific needs. By leveraging hybrid cloud, organizations can achieve a balance between cost efficiency, security, and performance, making it a versatile solution for a wide range of applications and industries.

# IaaS in GCP
- Virtualization is the mother of Cloud Computing, be it any offerings either IaaS, PaaS, or SaaS.
- Important layers in setting up the Infrastructure:
   - Hardware   (Bare Metal)
   - Hypervisor (VMware, ESXi, virtualization techniques).
- Infrastructure as a Service (IaaS) is a cloud computing model that provides **virtualized** computing resources over the internet.
- It offers businesses the flexibility to rent virtual machines, storage, and networking components on a pay-as-you-go basis.
- This eliminates the need for **investing in and maintaining physical hardware**, allowing organizations to scale their infrastructure up or down based on demand.
- IaaS is ideal for businesses that require robust and scalable computing power without the overhead of managing physical servers.

**IaaS (Infrastructure as a Service)**

- Compute Engine: Virtual machines running in Google’s data centers.
- Cloud Storage: Object storage service for storing and accessing data.
- Virtual Private Cloud (VPC): Networking service for managing network resources.
- Cloud Load Balancing: Distributes traffic across multiple instances.
- Persistent Disk: Durable and high-performance block storage for VMs.
- Cloud Interconnect: Extends on-premises networks to Google’s network.
- Cloud DNS: Scalable, reliable, and managed DNS service.

# PaaS in GCP

- If you want to launch a web application, you need bare minimum following components:
  - Web Server with Windows/linux OS.
  - Code of the application
  - install the application server
  - platform
  - dependencies
  - libraries
-
- - Platform as a Service (PaaS) is a cloud computing service that supplies a complete development and deployment environment in the cloud. 
- It includes everything developers need to build, test, deploy, and manage applications, such as development tools, middleware, database management systems, and infrastructure.
- PaaS abstracts the underlying infrastructure, enabling developers to focus on writing code and delivering applications quickly and efficiently.
- This model is particularly beneficial for collaborative development projects and rapid application development.

**PaaS (Platform as a Service)**

- App Engine: Fully managed platform for building and deploying web applications.
- Google Kubernetes Engine (GKE): Managed environment for deploying, managing, and scaling containerized applications using Kubernetes.
- Cloud Functions: Event-driven serverless compute service.
- Cloud Run: Fully managed compute platform for running containerized applications.
- Firebase: Platform for building mobile and web applications.
- BigQuery: Fully managed data warehouse for large-scale data analytics.
- Cloud Dataflow: Stream and batch data processing service.

# marketplace


# SaaS in GCP

- Software as a Service (SaaS) is a cloud-based software delivery model where applications are hosted by a service provider and made available to customers over 
  the internet.
- Users can access these applications through a web browser, eliminating the need for installing and maintaining software on individual devices.
- SaaS offers a subscription-based pricing model, making it cost-effective for businesses to use sophisticated software solutions without the complexities of 
  software management.
  This model is ideal for applications that require web or mobile access, such as email, customer relationship management (CRM), and collaboration tools.

**SaaS (Software as a Service)**

- Google Workspace: Suite of productivity and collaboration tools (e.g., Gmail, Docs, Drive, Calendar).
- Google Analytics: Web analytics service for tracking and reporting website traffic.
- Google Ads: Online advertising platform for creating and managing ads.
- Google Cloud Identity: Identity and access management service.
- Google Maps Platform: APIs and SDKs for integrating maps and location-based services into applications.



# GCP Infrastructure

# Regions 🌍
- A region is a specific geographical location where you can host your resources.
- Each region is an independent geographic area that consists of multiple zones.
- Regions help you place your resources closer to your users to reduce latency and meet regulatory and compliance requirements.
- Regions are categorized into following geographies:
  - Americas
  - Europe
  - Middle East
  - Asis Pacific
  - Others
- At present, there 42 working regions.
- CLI to see the list of all regions: gcloud compute regions list
- You can also opt to host your resources in more than one region.
- Using multiple regions can enhance disaster recovery strategies by provoding geographic redundancy.
- Some regions are designed to be more environmentally friendly, with low CO2 emissions.
- Each region contains multiple zones. A zone is an isolated location within a region, designed to be independent of other zones in the same region.
- This setup provides redundancy and isolation, ensuring high availability, and fault tolerance for your applications.
- Each region in Google Cloud Platform contains a minimum of three zones. This setup ensures redundancy and high availability, allowing you to distribute your
  resources across multiple zones within a regino to protect against failures. 



# Zones 🗺️
- A zone is an isolated location within a region. Each region has multiple zones, and each zone is designed to be independent of the others in the same region.
- Zones provide redundancy and isolation. By distributing your resources across multiple zones, you can protect your applications from failures that might occur 
  in a single zone.
- In the us-central1 region, the zones are us-central1-a, us-central1-b, us-central1-c, and us-central1-f.

# Key Points to Highlight 📌
- High Availability: Deploying resources across multiple zones within a region ensures high availability and fault tolerance.
- Low Latency: Regions and zones help minimize latency by allowing you to place resources closer to your users.
- Disaster Recovery: Using multiple regions can enhance disaster recovery strategies by providing geographic redundancy.

# How Google Secures GCP Infrastructure
Google employs a multi-layered approach to secure its GCP infrastructure. Here are the key components of their security strategy:

**1. Physical Security:**

- Data Centers: Google designs and builds its own data centers with multiple layers of physical security, including biometric identification, metal detection, 
  cameras, vehicle barriers, and laser-based intrusion detection systems.
- Access Control: Access to data centers is tightly controlled and monitored to ensure only authorized personnel can enter.

**2. Infrastructure Security:**

- Custom Hardware: Google uses custom-designed hardware and software to enhance security and performance1.
- Secure Boot: Ensures that servers boot with a known, verified firmware and software stack.

**3. Network Security:**

- Encryption: Data is encrypted in transit and at rest to protect it from unauthorized access2.
- DDoS Protection: Google’s infrastructure includes robust protection against Distributed Denial of Service (DDoS) attacks2.

**4. Identity and Access Management (IAM):**

- Strong IAM Processes: Implementing least privilege access, multi-factor authentication (MFA), and regular audits to manage and control access to resources3.
- BeyondCorp: A zero-trust security model that shifts access controls from the network perimeter to individual users and devices1.

**5. Data Security:**

- Encryption: Data is encrypted both in transit and at rest using strong encryption standards2.
- Data Loss Prevention (DLP): Tools and policies to prevent data leaks and ensure sensitive data is handled securely3.

**6. Monitoring and Logging:**

- Detailed Logging: Comprehensive logging and monitoring of activities to detect and respond to security incidents3.
- Security Command Center: A centralized platform for managing security and compliance across GCP2.

**7. Compliance and Certifications:**

- Certifications: Google Cloud complies with various industry standards and certifications, such as ISO/IEC 27001, SOC 1/2/3, and GDPR2.
- Continuous Compliance: Regular audits and assessments to ensure ongoing compliance with security standards2.

**8. Operational Security:**

- Regular Patching: Systems are regularly patched and updated to protect against vulnerabilities3.
- Incident Response: A dedicated team and processes for responding to security incidents2.

These measures collectively ensure that GCP infrastructure is secure, reliable, and compliant with industry standards.

# Shared Responsibility Model

-The shared responsibility model outlines the division of security responsibilities between Google Cloud and its customers.
- Ensures both parties understand their roles in securing cloud environments.
- Google Cloud's Responsibilities
  - Infrastructure Security: Physical security of data centers, network security, and hardware maintenance.
  - Platform Security: Ensuring the security of the cloud platform, including services like Compute Engine, Cloud Storage, and networking services.
  - Compliance: Meeting industry standards and certifications (e.g., ISO/IEC 27001, SOC 1/2/3, GDPR).
  - Physical Security: Secure data centers with multiple layers of protection.
  - Network Security: Encryption of data in transit and at rest, DDoS protection.
  - Operational Security: Regular patching and updates, incident response.
- Customer's Responsibilities
  - Data Security: Protecting data stored in the cloud, including encryption and access controls.
  - Identity and Access Management (IAM): Managing user access and permissions.
  - Configuration Management: Properly configuring cloud services to meet security and compliance requirements.
  - Data Protection: Encrypting sensitive data, implementing DLP (Data Loss Prevention) policies.
  - Access Management: Using IAM to control access, enabling multi-factor authentication (MFA).
  - Compliance and Auditing: Regularly auditing configurations and access logs, ensuring compliance with regulatory requirements.

- Shared Fate Model: Google Cloud's approach to partnering with customers to achieve better security outcomes through shared fate1.
- Continuous Monitoring: Implementing continuous monitoring and logging to detect and respond to security incidents.

# Cloud Identity
- In the context of Google Cloud Platform (GCP), Cloud Identity is an Identity as a Service (IDaaS) solution that centrally manages users and groups. 
- Here are some key points about Cloud Identity:
- Cloud Identity allows you to manage user identities and access across your organization.
- It helps you control who has access to your GCP resources.
- You can configure Cloud Identity to federate identities between Google and other identity providers, such as Active Directory and Microsoft Entra ID (formerly 
  Azure AD).
- By using Cloud Identity, you can manage access and compliance across all users in your domain.
- This includes setting up Identity and Access Management (IAM) policies to control access to GCP resources1.

**- Key Features of Cloud Identity:**
**1. User and Group Management: ** Create and manage user accounts and groups within your organization.

**2. Security: ** Implement strong security measures, such as multi-factor authentication (MFA) and single sign-on (SSO).

**3. Compliance:** Ensure compliance with regulatory requirements by managing and auditing user access.

**4. Centralized Management:** Simplifies the management of user identities and access across multiple services and applications.

**5. Enhanced Security:** Provides robust security features to protect your organization's data and resources.

**6. Scalability:** Easily scales to accommodate the needs of growing organizations.

**Cloud Identity is an essential tool for managing and securing access to your GCP resources, ensuring that only authorized users can access sensitive data and services.
**

# [Lab] Adding Users Password Policy and Enforce 2-Step Verification

# Google Cloud Directory Sync (GCDS)
- Google Cloud Directory Sync (GCDS) is a tool that enables administrators to synchronize users, groups, and other data from an Active Directory (AD) or LDAP 
  service to their Google Cloud domain directory.
- GCDS is a powerful tool for organizations that use both on-premises directories and Google Cloud services, providing seamless integration and management of 
  user identities.
  
 - Use Cases
  - User Provisioning: Automatically create, update, or delete user accounts in Google Cloud based on changes in your AD or LDAP directory.
  - Group Management: Synchronize group memberships to manage access to Google Cloud resources and applications.
  - Organizational Units: Reflect the structure of your organization in Google Cloud by synchronizing organizational units from your AD or LDAP directory. 

- Benefits
  - Consistency: Ensures that user information is consistent across both your on-premises directory and Google Cloud, reducing administrative overhead.
  - Efficiency: Automates the process of updating user accounts and groups, saving time and effort for IT administrators.
  - Security: Helps maintain secure access by ensuring that user accounts and permissions are accurately reflected in Google Cloud.
 
- Key Features
  - User and Group Synchronization: GCDS synchronizes user accounts, groups, and organizational units from your AD or LDAP directory to Google Cloud Identity or 
    Google Workspace.
  - Automated Sync: The synchronization process can be scheduled to run automatically at regular intervals, ensuring that your Google Cloud directory is always 
    up-to-date with changes made in your AD or LDAP directory.
  - Customizable Sync Options: Administrators can customize which attributes and objects to synchronize, providing flexibility to meet specific organizational   
    needs.
- Download and Install GCDS
  - access the GCDS Download page by visiting:
    - https://tools.google.com/dlpage/dirsync
  - Click on the download link to get the GCDS installer for your operating system.
  - Follow the instructions provided on the page to install and configure GCDS for synchronizing your Active Directory or LDAP directory with Google Cloud.
  - you can also visit this page for step by step instructions --
    - https://support.google.com/a/answer/6120989?hl=en&sjid=6330265346186834591-NC&visit_id=638785249898484818-1076318879&ref_topic=7106512&rd=1

# Resource Hierarchy in GCP (Org, Folder, and Projects) 
- The Google Cloud Platform (GCP) resource hierarchy is designed to organize and manage resources in a structured manner, similar to a file system.
- Here's a breakdown of the hierarchy:
- 
**1. Organization:**
- This is the top level of the hierarchy.
- It represents a company or an organization and provides central visibility and control over all resources.
- 
**2. Folders:**
- Under the organization, you can create folders to group projects and other folders.
- This helps in organizing resources based on departments, teams, or other logical groupings.

**3. Projects:**
- Projects are the next level in the hierarchy. 
- They are the primary grouping mechanism for resources and services. 
- Each project has its own set of permissions, billing information, and settings.
- Projects have their own set of permissions and roles.
- You can assign roles to users to control access to resources within the project.
- Common roles include Viewer, Editor, and Owner, each with different levels of access.
- Each project is linked to a billing account.
- You can set up budgets and alerts to monitor and control spending.
- Billing information is managed at the project level, allowing for detailed cost tracking.
- Projects act as containers for resources like Compute Engine instances, Cloud Storage buckets, and BigQuery datasets.
- Resources within a project can be organized and managed using labels and tags.
- Projects can be created, updated, and deleted.
- When a project is deleted, all resources within it are also deleted.
- It's important to manage the lifecycle of your projects to avoid unnecessary costs and resource usage.

**4. Resources:**
- These are the actual services and components you use, such as Compute Engine VMs, Cloud Storage buckets, and Pub/Sub topics.
- Resources are contained within projects.

The hierarchy allows for inheritance of policies and permissions. For example, access control policies set at the organization level are inherited by all folders, projects, and resources within that organizatio

• [Lab] Create Folders & Projects in GCP 
• [Lab] Organization Policy - I Identity & Access Management (Identity, Roles & Permissions) 
• Primitive Roles • Pre-Defined Roles 
• [Lab] Assign Pre-Defined Roles to Users 
• [Lab] Define Custom Role & Assignment Part - I 
• [Lab] Assign Role at Organization & Folder Levels IAM - Privileged Access Manager (PAM) Introduction 
• [Lab] Privileged Access Manager Part - 1
 
