# Firewall Configuration - UFW on Arch Linux

## Task: Setup and Use a Firewall

### System Information
- **OS**: Arch Linux
- **Username**: somu
- **Hostname**: huskey
- **Firewall**: UFW (Uncomplicated Firewall)

### Steps Completed

#### 1. Enable UFW Firewall
\`\`\`bash
sudo ufw enable
\`\`\`

#### 2. List Current Rules
\`\`\`bash
sudo ufw status verbose
\`\`\`

#### 3. Block Telnet (Port 23)
\`\`\`bash
sudo ufw deny 23
\`\`\`

#### 4. Test Block Rule
\`\`\`bash
nmap -p 23 localhost
\`\`\`

#### 5. Allow SSH (Port 22)
\`\`\`bash
sudo ufw allow 22
\`\`\`

#### 6. Remove Test Rule
\`\`\`bash
sudo ufw delete deny 23
\`\`\`

#### 7. Final Configuration
\`\`\`bash
sudo ufw status numbered
\`\`\`

### Final Firewall Rules
- Port 22: ALLOW (SSH Access)
- Default: deny incoming, allow outgoing

### How Firewall Filters Traffic
- **Packet Inspection**: Examines source/destination IP, ports, protocols
- **Rule-based Filtering**: Allows/denies based on configured rules
- **Stateful Inspection**: Tracks connection states
- **Default Security**: Deny all incoming, allow all outgoing traffic
