Module 3: Networking in GCP
• CIDR Notation 
• Virtual Private Network & Subnets 
• [Lab] Explore Default VPC 
• [Lab] Create Auto Mode VPC 
• [Lab] Create Custom Mode VPC 
• [Lab] Create Virtual Machine with All Subnets Firewall Rules 
• [Lab] Create Firewall Rule - SSH Internal vs External IP Address 
• [Lab] Internal vs External IP Address 
• [Lab] Static vs Ephemeral IP Address Shared VPC Concepts 
• [Lab] Deploy Shared VPC Introduction to VPC Peering 
• [Lab] VPC Peering GCP Hybrid Connectivity Options 
• Dedicated Interconnect vs Partner Interconnect

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

  


# Explore Auto Mode VPC

# Custom Mode VPC

# Explore Custom Mode VPC

#
