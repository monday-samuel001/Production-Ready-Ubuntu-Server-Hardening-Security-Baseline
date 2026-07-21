# Network Security

## Overview

Securing a Linux server requires controlling the network traffic that is permitted to enter and leave the system. A properly configured firewall acts as the first line of defense by restricting unnecessary network exposure and ensuring that only authorized services are accessible.

Implementing a default-deny firewall policy significantly reduces the server's attack surface by blocking unsolicited network traffic unless it has been explicitly permitted. Carefully defining inbound and outbound firewall rules also improves operational security while supporting the Principle of Least Privilege at the network layer.

This chapter demonstrates how a host-based firewall was configured to restrict network access, permit only required services, and validate that the implemented firewall rules functioned as intended.

## Network Security Controls Implemented

The following network security controls were implemented to reduce the server's attack surface and restrict network communication to only authorized services.

- Implementing a default-deny firewall policy.
- Allowing only required inbound and outbound network traffic.
- Restricting unnecessary network exposure through explicit firewall rules.
- Validating firewall behavior through controlled connectivity testing.

# 1. Uncomplicated Firewall (UFW)

### Why?

A firewall is one of the most effective security controls for reducing a server's attack surface. By filtering network traffic, it ensures that only explicitly authorized connections are permitted while blocking unnecessary or potentially malicious communication.

Adopting a default-deny firewall policy follows the Principle of Least Privilege at the network layer by allowing only services that are required for normal server operation.

## Implementation

Ubuntu's Uncomplicated Firewall (UFW) was configured to enforce a default-deny firewall policy for both inbound and outbound network traffic.

Only essential services required for server administration and operation were explicitly permitted, including Secure Shell (SSH) on the custom administrative port and HTTP traffic for the hosted NGINX web server.

This configuration minimizes unnecessary network exposure while ensuring legitimate administrative and application traffic remains functional.

## Configuration

### Configuring the UFW Firewall Policy

The firewall was configured with a default-deny policy, after which only the required services were explicitly allowed, including:

- SSH on TCP port `972`
- HTTP on TCP port `80`

This approach ensures that all network traffic is denied by default unless specifically authorized.

![UFW firewall configuration](../screenshots/network-security/01-01-ufw-firewall-configured.png)

## Verification

The firewall configuration was validated by testing connectivity to services that were explicitly permitted and confirming that unauthorized traffic remained blocked by the firewall.

---

### Test 1 - Verifying Allowed Services

### Verification Result

Connections to the SSH service on port `972` and the hosted NGINX web server on TCP port `80` were successfully established, confirming that authorized traffic was correctly permitted.

![Successful firewall validation](../screenshots/network-security/01-02-authorized-traffic.png)

![Successful firewall validation](../screenshots/network-security/01-04-authorized-traffic.png)

![Successful firewall validation](../screenshots/network-security/01-05-authorized-traffic.png)

### Test 2 - Validating the Default-Deny Firewall Policy

### Test Setup

A connection attempt was made to the MySQL service (TCP port `3306`) on the hardened Ubuntu server. Because no firewall rule permitted inbound access to this port, the connection was expected to fail.

For comparison, the same connection test was performed against a publicly accessible server where TCP port `3306` was accepting incoming connections.

![Firewall blocking MySQL port](../screenshots/network-security/01-03-blocked-traffic.png)

![Firewall blocking MySQL port](../screenshots/network-security/01-07-blocked-traffic.png)

---

### Verification Result

The connection attempt to the hardened Ubuntu server was unsuccessful because the firewall blocked inbound traffic to TCP port `3306`.

In contrast, the comparison test confirmed that another publicly accessible server accepted inbound connections on the same port, demonstrating how exposed network services can increase a system's attack surface.

---

### Security Validation

This validation confirms that the default-deny firewall policy successfully prevents unauthorized access to services that have not been explicitly permitted.

Restricting unnecessary network exposure reduces the number of potential entry points available for attackers and strengthens the server's overall security posture.
