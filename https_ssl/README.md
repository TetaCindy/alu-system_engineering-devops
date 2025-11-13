# HTTPS SSL

This project focuses on configuring DNS subdomains and understanding SSL/HTTPS concepts for web infrastructure.

## Project Description

Configure domain subdomains to point to different servers (load balancer and web servers) and create a script to audit DNS records.

## Requirements

- Ubuntu 16.04 LTS
- Shellcheck 0.3.7
- All Bash scripts must be executable
- All files must end with a new line

## Files

| File | Description |
|------|-------------|
| `0-world_wide_web` | Bash script that displays information about subdomains using dig and awk |

## Usage

### DNS Subdomain Information Script

Display information for all default subdomains:
```bash
./0-world_wide_web <domain>
```

Display information for a specific subdomain:
```bash
./0-world_wide_web <domain> <subdomain>
```

**Example:**
```bash
./0-world_wide_web yourdomain.com
./0-world_wide_web yourdomain.com web-01
```

## DNS Configuration

Configure the following A records for your domain:
- `www` → Load balancer IP
- `lb-01` → Load balancer IP
- `web-01` → Web server 1 IP
- `web-02` → Web server 2 IP


