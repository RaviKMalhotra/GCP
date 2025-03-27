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
CIDR Notation (Classless Inter-Domain Routing) is a method used to allocate IP addresses and route IP packets more efficiently. It represents IP addresses and their associated routing prefix in a compact format. A CIDR notation consists of an IP address followed by a slash (/) and a number, which indicates the number of bits in the subnet mask.

For example, in the CIDR notation 192.168.1.0/24:

192.168.1.0 is the network address.
/24 means that the first 24 bits of the IP address are the network part, and the remaining bits are used for host addresses.
This notation allows for flexible and efficient allocation of IP addresses, reducing the wastage of IP address space compared to traditional class-based addressing. CIDR is widely used in modern networking to manage IP address allocation and routing.
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
