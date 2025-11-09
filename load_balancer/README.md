# Load Balancer

This project configures web servers with custom Nginx response headers to track which server handles HTTP requests when placed behind a load balancer.

## Task 0: Custom HTTP Response Header

Configure Nginx on both `web-01` and `web-02` to include a custom HTTP header that identifies which server is responding to requests.

### Requirements

- Custom header name: `X-Served-By`
- Custom header value: hostname of the server
- Automated configuration script for Ubuntu 16.04 LTS

### Usage

```bash
# Make the script executable
chmod +x 0-custom_http_response_header

# Run the script with sudo
sudo ./0-custom_http_response_header
```

### Testing

```bash
# Test locally
curl -sI localhost | grep X-Served-By

# Test remotely
curl -sI <server-ip> | grep X-Served-By
```

### Example Output

```
X-Served-By: 6814-web-01
X-Served-By: 6814-web-02
```

## Files

- `0-custom_http_response_header` - Bash script that configures Nginx with custom HTTP response header
