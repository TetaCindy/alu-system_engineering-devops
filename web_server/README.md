# File Transfer Script

## Description
A Bash script that securely transfers files from a local client to a remote server using `scp` (Secure Copy Protocol).

## Repository Information
- **GitHub repository**: `alu-system_engineering-devops`
- **Directory**: `web_server`
- **File**: `0-transfer_file`

## Requirements

### Script Parameters
The script accepts exactly 4 parameters:
1. **PATH_TO_FILE** - The path to the file to be transferred
2. **IP** - The IP address of the destination server
3. **USERNAME** - The username for SSH connection
4. **PATH_TO_SSH_KEY** - The path to the SSH private key for authentication

### Functionality
- Displays usage message if less than 4 parameters are provided:
  ```
  Usage: 0-transfer_file PATH_TO_FILE IP USERNAME PATH_TO_SSH_KEY
  ```
- Transfers the file to the user's home directory (`~/`) on the remote server
- Disables strict host key checking for the `scp` connection

## Usage Example

```bash
# Check if file exists on remote server
$ ssh ubuntu@8.8.8.8 -i /vagrant/sylvain 'ls ~/'
afile

# Create a local file
$ touch some_page.html

# Transfer the file
$ ./0-transfer_file some_page.html 8.8.8.8 sylvain /vagrant/private_key
some_page.html                                     100%   12     0.1KB/s   00:00

# Verify file transfer
$ ssh ubuntu@8.8.8.8 -i /vagrant/private_key 'ls ~/'
afile
some_page.html
```

## Purpose
This script provides a simple way to publish website pages or transfer files to a remote server, useful for deployment workflows and file synchronization tasks.
