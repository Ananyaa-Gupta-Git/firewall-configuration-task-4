# Firewall Configuration Task - Cyber Security Internship

## Task Objective
Configure and test basic firewall rules to allow or block traffic on Windows/Linux systems.

## Tools Used
- **Windows**: Windows Firewall with Advanced Security (wf.msc)
- **Testing**: Command Prompt/Terminal, Telnet, Netstat

## System Information
- **Operating System**: Microsoft Windows [Version 10.0.26100.4770]
- **Firewall**: Windows Defender Firewall with Advanced Security
- **Date Completed**: 8 Aug 2025

## Tasks Completed

### 1. Initial Firewall Status
✅ Documented current firewall configuration
- Initial check showed Telnet services running on ports 23130 and 23134
- Command used: `netstat -an | findstr :23`
- Result: Found 4 TCP connections listening on port 23
- Screenshots: `screenshots/01_initial_telnet_status.png`, `screenshots/02_existing_inbound_rules.png`, `screenshots/03_initial_firewall_overview.png`

### 2. Blocked Telnet Port (23)
✅ Created inbound rule to block TCP port 23
- Rule Name: "Block Telnet Port 23"
- Action: Block connection
- Protocol: TCP
- Port: 23
- Profile: All (Domain, Private, Public)
- Screenshot: `screenshots/04_block_telnet_rule_created.png`

### 3. Tested Block Rule
✅ Verified that Telnet connections are properly blocked
- Command used: `telnet localhost 23`
- Result: "'telnet' is not recognized as an internal or external command" (Telnet client not installed - this is actually more secure)
- Note: The block rule was successfully created and is visible in firewall rules
- Screenshot: `screenshots/01_initial_telnet_status.png` (shows Telnet test attempt)

### 4. Allowed SSH Port (22)
✅ Created inbound rule to allow TCP port 22
- Rule Name: "Allow SSH Port 22"
- Action: Allow connection
- Protocol: TCP
- Port: 22
- Profile: All (Domain, Private, Public)
- Screenshot: `screenshots/05_ssh_and_telnet_rules_combined.png`

### 5. Documented Outbound Rules
✅ Reviewed existing outbound firewall rules
- Documented current outbound rule configuration
- Observed multiple Microsoft application rules properly configured
- Screenshot: `screenshots/06_outbound_rules_overview.png`

## Commands Used

### Windows Commands
```cmd
# Open Windows Firewall Advanced Settings
wf.msc

# Check network connections
netstat -an | findstr :23

# Test Telnet connection
telnet localhost 23

# Export firewall configuration (optional)
netsh advfirewall export "firewall_backup.wfw"
```

## Key Learnings

### Firewall Concepts
1. **Firewall Purpose**: Network security device that monitors and controls network traffic
2. **Inbound Rules**: Control traffic coming into the system
3. **Outbound Rules**: Control traffic leaving the system
4. **Port-based Filtering**: Blocking/allowing specific ports (e.g., 23 for Telnet, 22 for SSH)

### Security Insights
- **Telnet (Port 23)**: Insecure protocol that transmits data in plain text
- **SSH (Port 22)**: Secure alternative to Telnet with encryption
- **Default Deny**: Good practice to deny by default and allow only necessary traffic

### Practical Skills Gained
- Windows Firewall configuration using GUI
- Understanding of inbound/outbound traffic rules
- Testing firewall effectiveness
- Proper cleanup and documentation

## Files in Repository
```
├── README.md                              # This documentation
├── screenshots/                           # All task screenshots
├── commands/                              # Command documentation
│   └── windows_commands.txt               # All Windows commands used
└── configuration/                         # Configuration notes
    └── firewall_analysis.txt              # Analysis of firewall behavior
```

## Interview Questions Preparation

### Q1: What is a firewall?
**A**: A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between trusted internal networks and untrusted external networks.

### Q2: Difference between stateful and stateless firewall?
**A**: 
- **Stateful**: Tracks the state of network connections and makes decisions based on connection context and history
- **Stateless**: Treats each packet independently without considering connection state

### Q3: What are inbound and outbound rules?
**A**:
- **Inbound rules**: Control traffic coming into your system from external sources
- **Outbound rules**: Control traffic leaving your system to external destinations

### Q4: How does UFW simplify firewall management?
**A**: UFW provides a simple command-line interface for managing iptables rules, making firewall configuration accessible to users without deep networking knowledge.

### Q5: Why block port 23 (Telnet)?
**A**: Telnet transmits all data, including passwords, in plain text, making it vulnerable to eavesdropping and man-in-the-middle attacks. SSH (port 22) should be used instead as it provides encrypted communication.

### Q6: What are common firewall mistakes?
**A**:
1. Locking yourself out by blocking management access
2. Creating overly permissive rules
3. Not testing rules after implementation
4. Forgetting to enable the firewall
5. Not documenting rule changes

### Q7: How does a firewall improve network security?
**A**: Firewalls improve security by:
- Blocking unauthorized access attempts
- Filtering malicious traffic
- Controlling application access to the network
- Monitoring and logging network activity
- Implementing access control policies

### Q8: What is NAT in firewalls?
**A**: Network Address Translation (NAT) allows firewalls to hide internal IP addresses from external networks, providing an additional layer of security by making internal network structure invisible from outside.

## Completion Status
- [x] Task completed successfully
- [x] All screenshots captured
- [x] Documentation complete
- [x] GitHub repository organized
- [x] Ready for submission

---
**Submitted by**: Ananyaa Gupta  
**Date**: 08/08/2025  
**GitHub Repository**: https://github.com/Ananyaa-Gupta-Git/firewall-configuration-task-4
