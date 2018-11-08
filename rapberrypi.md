# Raspberry Pi

## Edit DNS Servers

```bash
sudo nano /etc/dhcpcd.conf
static domain_name_servers=8.8.8.8 8.8.4.4 # Add this line to the file
```