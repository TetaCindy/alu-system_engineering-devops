# Firewall

This project focuses on configuring UFW (Uncomplicated Firewall) to secure web servers by controlling incoming and outgoing network traffic.

## Project Description

Configure UFW firewall on web-01 server to block all incoming traffic except for essential services: SSH, HTTP, and HTTPS. This ensures the server is protected while remaining accessible for web traffic and remote administration.

## Requirements

- Ubuntu 16.04 LTS or later
- UFW (Uncomplicated Firewall)
- Root or sudo privileges
- All Bash scripts must be executable
- All files must end with a new line

## Files

| File | Description |
|------|-------------|
| `0-block_all_incoming_traffic_but` | UFW commands to configure firewall rules on web-01 |

## Installation and Configuration

### Install UFW
```bash
sudo apt-get update
sudo apt-get install -y ufw
```

### Configure Firewall Rules

The firewall is configured to:
- **Deny** all incoming traffic by default
- **Allow** all outgoing traffic by default
- **Allow** incoming traffic on specific ports:
  - Port 22 (SSH) - For remote server access
  - Port 80 (HTTP) - For web traffic
  - Port 443 (HTTPS) - For secure web traffic

### Apply Configuration

```bash
# Make the script executable
chmod +x 0-block_all_incoming_traffic_but

# Run the configuration script
sudo ./0-block_all_incoming_traffic_but
```

### Verify Configuration

Check UFW status and active rules:
```bash
sudo ufw status verbose
```

Expected output:
```
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere
80/tcp                     ALLOW IN    Anywhere
443/tcp                     ALLOW IN    Anywhere
```

## Important Notes

⚠️ **WARNING**: Always configure SSH (port 22) access **before** enabling UFW to prevent being locked out of your server.

⚠️ **Container Limitation**: UFW cannot be properly configured inside Docker containers due to iptables restrictions. Run these commands on actual servers.

## Security Best Practices

- Only open ports that are absolutely necessary
- Regularly review firewall rules: `sudo ufw status numbered`
- Monitor logs for suspicious activity: `sudo tail -f /var/log/ufw.log`
- Keep UFW and system packages updated

## Additional UFW Commands

```bash
# Disable firewall temporarily
sudo ufw disable

# Reset all rules to default
sudo ufw reset

# Delete a specific rule
sudo ufw delete allow 80/tcp

# Check firewall status
sudo ufw status
```

## Server Information

- **web-01**: 3.87.225.168
- **web-02**: 54.91.147.29
- **lb-01**: 34.230.38.85


