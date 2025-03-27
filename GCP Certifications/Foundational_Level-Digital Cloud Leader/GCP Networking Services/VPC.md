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

VPC network is a global resource with regional subnets.
By regional subnets, that means the subnet should belong to any of the desired region (geographical location).
Each VPC is logically isolated from each other.
You can create multiple VPCs as per the business requirements.
you cannot connect from a VM in one VPC to the other VM in the second VPC by default.
connectivity can be established between multiple VPCs using different services and techniques which we will explore in next topics.
2 or more VPCs can be connected together using VPC peering.
Subnets can acts as either private or public subnets depending on the routing defined.
Firewall rules can be configured to allow or restrcit traffic within subnets.
Resources wtihin a VPC communicate via the standard IPv4 addresses, and there is a dedicated DNS service within the VPC to provide name resolution.


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
# Auto Mode VPC

# Explore Auto Mode VPC

# Custom Mode VPC

# Explore Custom Mode VPC

#
