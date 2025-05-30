# Task-4-Elevate-Labs
# Setup and Use a Firewall (Linux - UFW)

## Objective

Configure and test basic firewall rules on a Linux system using UFW (Uncomplicated Firewall). The goal is to understand how to filter network traffic by allowing or blocking specific ports.

## Environment

- OS: Kali Linux
- Tool: UFW (Uncomplicated Firewall)

## Steps Performed

1. **Checked UFW status**
   - Command: `sudo ufw status verbose`
   - Result: UFW was active; default policy set to deny all incoming connections.

2. **Listed current firewall rules**
   - Command: `sudo ufw status`
   - SSH (port 22) was already allowed.

3. **Blocked inbound traffic on port 23 (Telnet)**
   - Command: `sudo ufw deny 23`
   - Verified using `ufw status` to see deny rule applied.

4. **Tested Telnet port**
   - Command: `telnet localhost 23`
   - Result: Connection refused (as expected, since the port was blocked).

5. **Allowed SSH (port 22)**
   - Command: `sudo ufw allow 22`
   - Result: UFW confirmed the rule already existed; no change made.

6. **Removed test block rule for port 23**
   - Command: `sudo ufw delete deny 23`
   - Verified using `ufw status` to confirm removal.

## How Firewalls Filter Traffic

Firewalls work as gatekeepers that monitor and control network traffic based on a set of predefined rules. They inspect each data packet and decide whether to allow or block it, based on parameters such as:

- **IP addresses** (source and destination)
- **Port numbers** (e.g., block port 23, allow port 22)
- **Protocol types** (TCP, UDP, ICMP)
- **Direction of traffic** (inbound or outbound)
- **Connection state** (in stateful firewalls)

In Linux, tools like **UFW** simplify the management of these rules by providing an easy-to-use command-line interface over `iptables`, enabling users to create complex filtering rules using straightforward syntax like `allow`, `deny`, and `delete`.

---
## Commands Used

```bash
sudo ufw status verbose
sudo ufw status
sudo ufw deny 23
telnet localhost 23
sudo ufw allow 22
sudo ufw delete deny 23


