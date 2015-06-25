## Security Consideration

### OpenLDAP 

OpenLDAP container port (389) is published on the host. Make sure you know what you're doing and configure firewall to block it. Then access slapd within internal network through VPN

## Hardening Ubuntu

### Disable root login
	PermitRootLogin no

### Disable password login
	PasswordAuthentication no
