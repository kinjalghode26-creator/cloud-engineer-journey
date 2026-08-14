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

## Day 2 — Azure Connectivity Troubleshooting

### Troubleshooting Flow

When a VM cannot communicate with another VM:

1. Check whether both VMs are running.
2. Identify the source IP and destination IP.
3. Identify the protocol and destination port.
4. Check NSGs associated with the relevant subnet and NIC.
5. Check routing and effective routes.
6. Check whether the destination port is listening.
7. Check whether the required application/service is running.

### Important Concepts

#### ICMP vs TCP

Ping uses ICMP.

ICMP does not use TCP/UDP ports.

For example:

- Ping → ICMP
- SQL Server → TCP 1433
- HTTPS → TCP 443

A failed ping does not necessarily mean TCP connectivity is blocked because they use different protocols.

### Network Watcher

Azure Network Watcher can be used for network troubleshooting.

The Connection Troubleshoot feature can be used to test connectivity between a source and destination, including a specific TCP port.

Example:

Source:
vm-app01

Destination:
vm-db01

Protocol:
TCP

Port:
1433

### Port vs Application

A network port being reachable does not necessarily mean the application is working.

Example:

TCP 1433 → Reachable ✅
SQL Server → Not running ❌

The application/service should therefore also be checked.

### Day 2 Troubleshooting Mindset

When troubleshooting connectivity, identify where the communication is failing:

Source → Routing → NSG → Network Path → Destination → OS Firewall → Port → Application

### Day 2 Takeaway

Being in the same VNet does not automatically mean that all communication will work.

A successful network connection also does not guarantee that the application/service is working.
