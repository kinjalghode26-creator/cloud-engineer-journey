# Azure Learning Journey

## Day 1 — Azure Networking Fundamentals

### Topics Learned

- Azure Virtual Network (VNet)
- Address Space
- Subnets
- Private IP vs Public IP
- Network Security Group (NSG)
- Route Tables / User Defined Routes (UDR)
- Azure connectivity troubleshooting

### Key Concepts

#### Azure VNet
An Azure VNet is a logically isolated network in Azure that provides private IP-based communication between Azure resources.

#### Subnet
A subnet is a smaller network within a VNet. A VNet can contain multiple subnets.

Example:

- VNet: 10.0.0.0/16
- Web Subnet: 10.0.1.0/24
- App Subnet: 10.0.2.0/24
- DB Subnet: 10.0.3.0/24

#### NSG
A Network Security Group controls network traffic using security rules such as source, destination, port, protocol, priority and action (Allow/Deny).

Lower priority number = higher priority.

#### Route Table / UDR
A route determines where traffic should go next based on its destination. User Defined Routes (UDRs) allow custom routing.

### Troubleshooting Mindset

When a VM cannot communicate with another VM, check:

1. VM status
2. Source and destination IP
3. Protocol and port
4. Routing
5. NSG
6. OS firewall
7. Port/listener
8. Application/service

### Day 1 Takeaway
Being in the same VNet does not automatically mean all communication will work. Connectivity depends on routing, security rules, firewalls, ports and the application/service.

Being in the same VNet does not automatically mean all communication will work. Connectivity depends on routing, security rules, firewalls, ports and the application/service.
