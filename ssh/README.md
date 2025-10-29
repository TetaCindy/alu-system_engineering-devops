# SSH

This project contains Bash scripts for connecting to remote servers using SSH.

## Description

This project focuses on learning SSH (Secure Shell) and how to use it for secure remote server connections using private keys.

## Requirements

- Ubuntu 20.04 LTS
- All scripts must be executable
- Scripts must start with `#!/usr/bin/env bash`
- Second line must be a comment explaining what the script does

## Files

| File | Description |
|------|-------------|
| `0-use_a_private_key` | Bash script that uses SSH to connect to a server using the private key `~/.ssh/school` with the user `ubuntu` |

## Usage

Make the script executable:
```bash
chmod +x 0-use_a_private_key
```

Run the script:
```bash
./0-use_a_private_key
```
