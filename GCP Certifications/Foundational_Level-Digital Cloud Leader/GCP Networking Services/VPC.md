Ravi Malhotra
+919650207359

# Understanding of CIDR Notation
- CIDR Notation (Classless Inter-Domain Routing) is a method used to allocate IP addresses and route IP packets more efficiently.
- It represents IP addresses and their associated routing prefix in a compact format.
- A CIDR notation consists of an IP address followed by a slash (/) and a number, which indicates the number of bits in the subnet mask.
- For example, in the CIDR notation 192.168.1.0/24:
  - 192.168.1.0 is the network address.
  - /24 means that the first 24 bits of the IP address are the network part, and the remaining bits are used for host addresses.
  - This notation allows for flexible and efficient allocation of IP addresses, reducing the wastage of IP address space compared to traditional class-based 
    addressing.
- CIDR is widely used in modern networking to manage IP address allocation and routing.
    
# Understanding of VPC
- VPC network is a global resource with regional subnets.
- By regional subnets, that means the subnet should belong to any of the desired region (geographical location).
- Each VPC is logically isolated from each other.
- You can create multiple VPCs as per the business requirements.
- you cannot connect from a VM in one VPC to the other VM in the second VPC by default.
- connectivity can be established between multiple VPCs using different services and techniques which we will explore in next topics.
- 2 or more VPCs can be connected together using VPC peering.
- Subnets can acts as either private or public subnets depending on the routing defined.
- Firewall rules can be configured to allow or restrcit traffic within subnets.
- Resources wtihin a VPC communicate via the standard IPv4 addresses, and there is a dedicated DNS service within the VPC to provide name resolution.

# Auto Mode VPC
- An auto mode VPC in Google Cloud Platform (GCP) is a type of Virtual Private Cloud that automatically creates subnets in each region with predefined IP ranges. This setup simplifies network management by providing a global network infrastructure out of the box. Auto mode VPCs come with default firewall rules and routes, allowing for easy and quick deployment of resources without the need for extensive network configuration.

# Default VPC
- The default VPC is an auto mode VPC, which automatically creates subnets in each region.
- Each subnet in the default VPC is created with a predefined IP range. These subnets span all regions, providing a global network infrastructure.
- This makes it easier to start using GCP services without needing to manually configure the network.
- Default VPC can also be deleted as per the business requirements. 

**Firewall Rules**

- The default VPC comes with pre-configured firewall rules that allow internal communication between instances and block incoming traffic from outside the network, except for SSH, RDP, and ICMP1.

**Routes**

- Default routes are created to enable communication between subnets and to direct traffic to the internet.
- These routes include a default internet gateway route.

**Ease of Use**

The default VPC is designed to simplify the initial setup and usage of GCP services. 
It allows you to quickly deploy resources without needing to configure networking details.

**Customizability**

- While the default VPC (auto mode) is convenient, you can create custom VPCs to have more control over your network configuration. 
- Custom VPCs allow you to define your own subnets, IP ranges, and firewall rules.

**Security**

The default VPC includes basic security configurations, but for production environments, it's recommended to review and customize firewall rules and other security settings to meet your specific requirements.

# Custom Mode VPC
- A custom mode VPC in Google Cloud Platform (GCP) allows you to have full control over your network configuration.
- Unlike auto mode VPCs, custom mode VPCs do not automatically create subnets in each region.
- Instead, you manually create subnets with specific IP ranges as needed.
- This flexibility enables you to design your network to fit your unique requirements, including setting up dual-stack subnets with both IPv4 and IPv6 address 
  ranges.
- Custom mode VPCs are ideal for production environments where precise network management is crucial.
- They allow for better integration with existing IP address management schemes and avoid conflicts that can arise with auto mode VPCs.
- Additionally, custom mode VPCs support advanced features like VPC Network Peering and Shared VPC, providing robust options for connecting and managing multiple networks3.

# Shared VPC
- Shared VPC in Google Cloud Platform (GCP) allows an organization to **connect resources from multiple projects** to a common Virtual Private Cloud (VPC)
  network.
- This setup enables **secure and efficient communication between resources using internal IP addresses**.
- In a Shared VPC, you designate a project as a host project and attach one or more service projects to it.
- The VPC networks in the host project are called Shared VPC networks.
- Key benefits of Shared VPC include:
1. Centralized Network Management: Network resources like subnets, routes, and firewalls are managed centrally in the host project, while service project admins can manage their own resources without impacting the network configuration.
2. Security and Access Control: Shared VPC allows for consistent application of security policies across multiple projects, ensuring that access control is maintained at the network level.
3. Cost Management: Service projects can be used to separate budgeting or internal cost centers, making it easier to track and manage expenses.
Shared VPC is ideal for organizations that need to maintain a centralized network infrastructure while allowing different teams or departments to manage their own resources independently.

# VPC Peering
- VPC Peering is a networking feature that allows you to connect **two Virtual Private Clouds (VPCs)** directly, enabling secure and private communication between them.
- With VPC peering, resources in the peered VPCs can interact as if they were part of the same network, using private IP addresses.
- This eliminates the need for traffic to traverse the public internet, enhancing security and reducing latency.
- VPC peering is useful for scenarios such as:
1. **Inter-Project Communication:**
- Connecting VPCs in different projects within the same organization.

 2. **Cross-Region Connectivity:**
- Establishing connections between VPCs in different regions for global applications.

3. **Resource Sharing:**
Allowing different teams or departments to share resources securely without exposing them to the public internet.

- Setting up VPC peering involves creating a peering connection request from one VPC and accepting it from the other.
- Once established, you need to update route tables and security groups to allow traffic between the peered VPCs.


# IP Addressing
overview of the different types of IP addresses used in Google Cloud Platform (GCP):

1. **Internal IP Addresses:**
- Internal IPv4 Addresses: These are private IP addresses used for communication within a VPC network.
- They are not accessible from the internet and are used for internal communication between resources in the same VPC or connected networks.
- Internal IPv6 Addresses: Similar to internal IPv4 addresses, these are private IPv6 addresses used for internal communication within a VPC network.
  
2. **External IP Addresses:**
- External IPv4 Addresses: These are public IP addresses that allow resources to communicate with the internet.
- They can be either ephemeral or static.
- External IPv6 Addresses: Public IPv6 addresses that enable internet communication for resources.
- These are provided by Google.
  
3. **Ephemeral IP Addresses:**
- Ephemeral External IP Addresses: These are temporary IP addresses assigned to resources when they are created.
- They are released when the resource is stopped or deleted.
- Ephemeral Internal IP Addresses: These are temporary internal IP addresses assigned to resources within a VPC network.
  
4. **Static IP Addresses:**
- Static External IP Addresses: These are permanent IP addresses that you reserve and assign to resources.
- They remain the same even if the resource is stopped or restarted.
- Static Internal IP Addresses: These are permanent internal IP addresses that you reserve and assign to resources within a VPC network.
  
5. **Alias IP Ranges:**
- These allow you to assign multiple internal IP addresses to a single network interface.
- This is useful for running multiple services on a single VM instance.
  
6. **Public IP Addresses:**
- These are IP addresses that are routable on the internet.
- External IPv4 and IPv6 addresses are always public IP addresses.

7. **Private IP Addresses:**
- These are IP addresses that are **not routable on the internet**.
- They are used for internal communication within a VPC network or connected on-premises networks.

### Understanding these different types of IP addresses helps in effectively managing network configurations and ensuring secure and efficient communication between resources in GCP.

# Interconnect
- Interconnect in Google Cloud Platform (GCP) refers to a suite of services that provide high-bandwidth, low-latency connections between your on-premises network and Google Cloud.
- These connections are **established through physical links,** either directly or via a service provider, to ensure secure and efficient data transfer.
- There are two main types of Interconnect services:

1. **Dedicated Interconnect:**
- Provides a direct physical connection between your on-premises network and Google's network, offering high bandwidth and low latency.
- This option is ideal for large-scale data transfers and requires your data center to be located in a colocation facility with a Dedicated Interconnect 
  connection.

2. **Partner Interconnect:**
- Uses a supported service provider to connect your on-premises network to Google Cloud.
- This option offers flexible bandwidth options and is suitable for locations that cannot reach a Dedicated Interconnect colocation facility.
- The service provider handles much of the setup and management, making it a simpler and often more cost-effective solution.

### These Interconnect options enable you to extend your on-premises infrastructure to Google Cloud, providing a seamless hybrid cloud experience.

# [ Labs Section ]
Now, we will do couple of labs.

# Explore Default VPC
- Type 'VPC Networks' in the main search bar
- Under 'VPC Networks', you will see one VPC created for you by default.
- Name of this VPC is 'default', and the Mode of this VPC is 'Auto'
- And you can see that it has 6 Firewall rules created for you by default.
- Refer to the screenshot below:
- ![image](https://github.com/user-attachments/assets/6ecdf057-9d1e-4f33-a944-202e0d19fdc7)

- click on the default VPC, and then you will see many different tabs such as Overview, Subnets, Static Internal IP Addresses, Firewall, Firewall Endpoints, Routes, VPC Network Peering, Private Services Access, and DNS Configuration.

- Click on Subnets, and you will see a list of 42 subnets created for you, one subnet in each active region.
- you can create additional subnet here by click on the button 'Add Subnet'
- You cannot delete the defaul subnet.
- Each subnet is named as default.
- Each subnet has a specific Primary IPv4 ranges.
- Each subnet has a dedicated, which is always the first ip address of that specific range.
- example: for the subnet with the IPv4 range 10.140.0.0/20, the default gateway IP address will be '10.140.0.1'.

Firewall Rules

- Default VPC (Custom Mode VPC) is also preconfigured with 6 Firewall Rules. These are the firewall rules:
1. default-allow-https: with a Rule priority of 1000, allowing access over port HTTP/80.
2. default-allow-https: with a Rule priority of 1000, allowing access over port HTTPS/443.
3. defualt-allow-icmp: with a Rule priority of 65534, allowing access over port ICMP.
4. default-allow-ssh: with a Rule priority of 65534, allowing access over port TCP/22.
5. default-allow-internal: with a Rule priority of 65534, allowing access over TCP:0-65535 & UDP:0-65535, and ICMP.
6. default-allow-rdp: with a Rule priority of 65534, allowing access over port TCP/3389.

- Refer to the screenshot below:
- ![image](https://github.com/user-attachments/assets/34c5f7d4-7cb9-4732-b06c-755449b4d94b)

------------------
# Day 3
------------------


# Lab # 1 - Create a Load Balancing Setup

1. **Create an instnace in the default vpc in the useast1b location with the windows server 2025 OS.**
  - Install IIS role on this windows server to make it as a web server.
     
2. **Create an instnace in the default vpc in the useast1b location with the Debian OS.**
  - Perform these commands on the debian machine to make a web server:
    - sudo apt update
    - sudo apt install apache2 -y
    - sudo systemctl start apache2
    - sudo systemctl enable apache2
      
3. **Crete an Instance Group in the Instance page**
4. **Create a public facing application LB**

# Module 4: Identity-Aware Proxy (IAP)
- Identity-Aware Proxy (IAP) is a Google Cloud service that provides a **centralized authorization layer for applications accessed over HTTPS.**
- It allows you to **enforce access control policies at the application level**, rather than relying solely on network-level firewalls.
- By leveraging IAP, organizations can enforce granular access control policies at the application level, **ensuring that only authenticated and authorized 
  users can access sensitive resources.**
- This service integrates seamlessly with Google Cloud's suite of products, offering a robust security solution that aligns with modern zero-trust security 
  models.
- IAP not only simplifies the management of user access but also **enhances security by eliminating the need for traditional network-level firewalls and VPNs.**
- With features like **context-aware access** and **integration with existing identity providers**, IAP provides a comprehensive and flexible approach to 
  securing cloud- based and on-premises applications.

- Here are some key features and benefits of IAP:

1. **Centralized Access Control:**
- IAP provides a single point of control for managing user access to web applications and cloud resources.
- This helps ensure consistent security policies across your organization.

2. **Authentication and Authorization:**
- IAP performs both authentication and authorization checks.
- It verifies user identity and ensures that only authorized users can access protected resources.

3. **Zero-Trust Security Model:**
- IAP supports a zero-trust security model, allowing users to access applications from untrusted networks without the need for a VPN.
- This enhances security and simplifies remote access.

4. **Context-Aware Access:**
- IAP can enforce access policies based on user identity, device security status, IP address, and other contextual attributes.
- This allows for fine-grained access control.

5. **Integration with Google Cloud Services:**
- IAP integrates seamlessly with various Google Cloud services, including App Engine, Compute Engine, and Google Kubernetes Engine (GKE).
- It can also protect SSH and RDP access to VMs.

6. **Ease of Use:**
- End users can access IAP-secured applications by simply pointing their web browser to an internet-accessible URL.
- No VPN client is required, making it easier for remote workers.
- IAP is ideal for organizations looking to enhance security and simplify access management for their cloud-based and on-premises applications.

# [Lab] Identity Aware Proxy Part - Step-by-Step Instructions

1. Set Up Your Environment
Create a Project: Go to the Google Cloud Console, create a new project, or select an existing one.
Enable Billing: Ensure billing is enabled for your project.

2. Enable Necessary APIs
Navigate to APIs & Services > Library.
Enable the **Identity-Aware Proxy API** and Compute Engine API.

3. Set Up a Compute Engine Instance
Create an Instance: Go to Compute Engine > VM instances and click on Create Instance.
Configure the Instance: Choose the necessary configurations (e.g., machine type, region) and deploy a simple web application on this instance.

4. Set Up an HTTPS Load Balancer
- Navigate to Load Balancing: Go to Network Services > Load Balancing.
- Create a Load Balancer: Click on Create Load Balancer and select HTTP(S) Load Balancer.
- Configure Backend Services: Add the Compute Engine instance as a backend service.
- Configure Frontend: Set up the frontend configuration with an IP address and port.

5. Enable Identity-Aware Proxy (IAP)
- Navigate to IAP: Go to **Security > Identity-Aware Proxy.**
- Enable IAP: Select the **load balancer** you created **and click on Enable IAP**.
- Configure Access: Set up access controls by assigning IAM roles to users who should have access to the application.
  
6. Test Your Configuration
- Access the Application: Try accessing the application through the load balancer's IP address.
- Authentication: You should be prompted to sign in with a Google account. Only users with the appropriate IAM roles will be able to access the application.

# Module 5: Cloud Armor
- Google Cloud Armor as a suite of security features and services.
- Google Cloud Armor provides a comprehensive set of tools to protect your applications and infrastructure from various threats, including DDoS attacks and web 
  application vulnerabilities.
- It includes features like **DDoS protection**, a **web application firewall (WAF)**, **adaptive protection**, and **security policies**
- Google Cloud Armor is a security service designed to protect your Google Cloud deployments from various types of threats, including distributed denial-of-service (DDoS) attacks and application attacks like cross-site scripting (XSS) and SQL injection (SQLi).
- Here are some key features and benefits:

1. **DDoS Protection:**
- Provides **always-on protection** against volumetric and protocol-based DDoS attacks, ensuring your applications remain available even under attack.

2. **Web Application Firewall (WAF):**
- Includes **preconfigured WAF rules** to protect against common web application vulnerabilities, such as those **listed in the OWASP Top 10**.
- Allows you to define custom rules with configurable match conditions and actions to tailor security policies to your specific needs.

3. **Security Policies:**
- You can create and manage security policies to **protect applications running behind a load balancer.**
- These policies can be configured manually or use preconfigured templates.
- Policies can be applied to both **global and regional external Application Load Balancers**.
- 
4. **Adaptive Protection:**
- Offers **adaptive protection for Layer 7 endpoints**, which uses **machine learning** to detect and mitigate sophisticated attacks in real-time.

5. **Integration with Other Services:**
- Integrates with Cloud CDN and Media CDN to provide enhanced security for content delivery networks.

6. **Enterprise Features:**
- Cloud Armor Enterprise includes advanced features such as third-party named IP address lists, Google Threat Intelligence, and DDoS bill protection.
- Google Cloud Armor helps ensure the security and availability of your applications, whether they are deployed on Google Cloud, in a hybrid environment, or 
  across multiple clouds.

# Cloud Armor Lab

To get started with a lab on GCP Cloud Armor, you can follow these steps:

Set Up Your Environment:

Ensure you have a Google Cloud account and have enabled billing.
Create a new project or use an existing one.
Enable Necessary APIs:

Enable the Cloud Armor API and other related APIs like Compute Engine API.
Create a Load Balancer:

Set up an external HTTP(S) load balancer to serve as the entry point for your application.
Configure Cloud Armor Security Policies:

Create security policies to filter incoming traffic. You can use preconfigured WAF rules or define custom rules based on your needs1.
Attach Security Policies to Backend Services:

Apply the security policies to your backend services to protect them from attacks2.
Test Your Configuration:

Simulate different types of attacks to ensure your security policies are working as expected.
For detailed instructions, you can refer to the Google Cloud Armor documentation12.

If you have any specific questions or need further assistance, feel free to ask!



1
Favicon type
Product overview | Google Cloud Armor

2
Favicon type
Configure Google Cloud Armor security policies

Favicon type
Google Cloud Armor documentation
Show more




AI-generated content may be incorrect
You said:

no no, give me low level instructions, i want to perform this lab, i have access to the GCP 
Copilot said:
Copilot
Got it! Let's dive into the detailed steps to set up a lab with Google Cloud Armor:

Step-by-Step Instructions
1. Set Up Your Environment
Create a Project: Go to the Google Cloud Console, create a new project, or select an existing one.
Enable Billing: Ensure billing is enabled for your project.
2. Enable Necessary APIs
Navigate to APIs & Services > Library.
Enable the Cloud Armor API and Compute Engine API.
3. Create a Load Balancer
Navigate to Load Balancing: Go to Network Services > Load Balancing.
Create a Load Balancer: Click on Create Load Balancer and select HTTP(S) Load Balancer.
Configure Backend Services: Add backend services (e.g., instance groups) that will serve your application.
Configure Frontend: Set up the frontend configuration with an IP address and port.
4. Configure Cloud Armor Security Policies
Create a Security Policy:
Go to Security > Cloud Armor.
Click on Create Policy.
Define the policy name and description.
Add rules to the policy (e.g., allow or deny specific IP ranges, apply preconfigured WAF rules).
Add Rules: Specify the conditions for each rule (e.g., IP ranges, request headers).
5. Attach Security Policies to Backend Services
Navigate to Backend Services: Go to Network Services > Load Balancing > Backend Services.
Select Backend Service: Choose the backend service you want to protect.
Attach Security Policy: Click on Edit and attach the security policy you created.
6. Test Your Configuration
Simulate Attacks: Use tools like curl or third-party services to simulate different types of attacks (e.g., SQL injection, XSS).
Verify Logs: Check the logs in Cloud Logging to ensure that the security policies are being enforced.


# Module 6: Data Loss Prevention (DLP) API
The Google Cloud Data Loss Prevention (DLP) API is a fully managed service designed to help you discover, classify, and protect sensitive data across your organization. Here’s a brief overview:

What is Cloud DLP?
Cloud DLP helps you identify and manage sensitive information in your data. It can inspect and classify data in various formats, including text, images, and storage repositories like BigQuery, Cloud Storage, and Datastore12.

Key Features
Data Discovery and Classification:

Detects sensitive data such as credit card numbers, social security numbers, and other personally identifiable information (PII).
Supports over 150 built-in information types2.
Data Transformation:

Provides methods for de-identifying data, such as masking, tokenization, and redaction, to protect sensitive information while preserving its utility2.
Risk Analysis:

Analyzes data to identify potential re-identification risks, helping you understand and mitigate privacy risks2.
Integration and Automation:

Offers APIs for integrating with existing systems and automating data protection workflows.
Supports real-time data protection for live traffic and batch processing for data at rest2.
How It Works
Inspection: Cloud DLP inspects data to find sensitive information using predefined or custom detection rules.
Transformation: It can then transform the data to obscure sensitive information while maintaining its usability.
Analysis: Provides insights into data privacy risks and helps you manage compliance requirements2.
For more detailed information, you can refer to the Google Cloud DLP documentation

• [Lab] DLP API Demo

Templates, INFO_TYPES & Match
• [Lab] Create Stored INFO_TYPE
• [Lab] Create Template
• [Lab] Create Job for Inspection
• [Lab] Template for De-Identification

# Module: Backup and Disaster Recovery
- Google Cloud Platform (GCP) offers a robust suite of services and tools for backup to safeguard your critical data.
- Key offerings include the Google Cloud Backup and DR Service, which provides centralized management, policy-based backups, and incremental backups for 
  efficient data protection1.
- Additionally, Persistent Disk Snapshots and Cloud Storage are essential tools for creating and storing backups, ensuring your data is secure and easily 
  recoverable.
- GCP also supports Backup Vaults, which offer immutable and indelible storage for enhanced security.
- Whether using managed services or self-managed storage, GCP provides comprehensive solutions to meet diverse backup needs.

  # Module: Disaster Recovery
- Disaster recovery (DR) is a critical component of business continuity planning, designed to restore systems and data after a catastrophic event.
- Google Cloud Platform (GCP) provides a comprehensive set of tools and technologies to support DR strategies.
- Key offerings include the **Google Cloud Backup and DR Service**, which facilitates seamless backup and recovery operations.
- Cloud Storage offers durable and scalable storage solutions for backup data.
- Compute Engine provides flexible and reliable compute resources to quickly restore applications.
- Additionally, Cloud DNS and Traffic Director help manage and route traffic efficiently during a disaster2. By leveraging these services, organizations can ensure minimal downtime and data loss, maintaining operational resilience in the face of unexpected disruptions.
- 
# Module 8: GCP Security Tools
• [Lab] Web Security Scanner
• [Lab] Security Command Center
# Cloud Logging
• [Lab] Explore Cloud Logging
• [Lab] Cloud Log Sinks
• [Lab] Container Scanning API

# By Ravi K Malhotra

