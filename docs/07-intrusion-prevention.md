## Project Summary

This project demonstrated the implementation and validation of multiple production-oriented Linux security controls, including:

- Authentication hardening
- Least privilege access control
- Security logging and auditing
- File integrity protection
- System maintenance
- Network security
- Automated intrusion prevention

Each control was independently configured, validated, and documented using real implementation evidence collected during the hardening process.

Together, these layered controls establish a practical defense-in-depth security baseline suitable for production Ubuntu server environments.
# Intrusion Prevention

## Overview

Preventive security controls such as authentication hardening, access control, and firewalls significantly reduce the likelihood of unauthorized access. However, Internet-facing servers are continuously subjected to automated attacks, including brute-force login attempts and credential guessing.

Intrusion prevention complements these controls by continuously monitoring authentication activity and automatically responding to suspicious behavior before it develops into a successful compromise.

This chapter demonstrates how Fail2Ban was configured to detect repeated SSH authentication failures and automatically block offending IP addresses, providing an additional layer of protection against automated attacks.

## Intrusion Prevention Controls Implemented

The following intrusion prevention controls were implemented to automatically detect and respond to malicious authentication activity.

- Monitoring SSH authentication logs.
- Detecting repeated failed login attempts.
- Automatically banning offending IP addresses.
- Validating automatic recovery after removing the ban.

# 1. Fail2Ban

### Why?

Internet-facing SSH services are frequently targeted by automated bots performing brute-force and password-guessing attacks. Even when strong authentication controls are in place, continuously allowing repeated authentication attempts unnecessarily consumes system resources and increases operational risk.

Fail2Ban strengthens server security by monitoring authentication logs, identifying repeated failed login attempts, and temporarily blocking offending IP addresses before additional attacks can continue.

##  Implementation

Fail2Ban was configured to monitor SSH authentication logs and automatically ban IP addresses that exceeded the configured authentication failure threshold.

The SSH jail was customized to define the maximum number of failed login attempts, ban duration, and monitoring window, providing automated protection against repeated authentication attacks.

## Configuration

### Configuring Fail2Ban for SSH Protection

Fail2Ban was configured to monitor the SSH service (`sshd`) and automatically ban IP addresses that exceeded the configured authentication failure threshold.

The SSH jail configuration was reviewed to confirm that the intrusion prevention policy had been successfully applied.

![Fail2Ban SSH configuration](../screenshots/intrusion-prevention/01-01-fail2ban-configured.png)

## Verification

The intrusion prevention policy was validated by intentionally generating multiple failed SSH authentication attempts and confirming that Fail2Ban automatically blocked the offending IP address.

---

### Test 1 - Triggering Automatic Protection

### Test Setup

Multiple failed SSH authentication attempts were intentionally generated from the same client to exceed the configured Fail2Ban threshold.

![Repeated failed SSH authentication attempts](../screenshots/intrusion-prevention/01-02-failed-login-attempts.png)

---

### Verification Result

After the configured failure threshold was exceeded, Fail2Ban automatically banned the client's IP address and prevented additional SSH connection attempts.

![IP address automatically banned](../screenshots/intrusion-prevention/01-03-ip-banned.png)

