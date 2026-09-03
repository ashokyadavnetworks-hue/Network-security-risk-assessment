# Network Hardening Plan

## Objective

Reduce the organization's attack surface and prevent unauthorized access through layered network and identity security controls.

## Control 1 — Firewall Traffic Filtering

### Implementation

The firewall should use a least-privilege approach.

Unnecessary inbound and outbound connections should be denied, while only business-required traffic should be permitted.

### Controls

* Default-deny inbound traffic.
* Permit only required public services.
* Restrict administrative services.
* Restrict direct user access to databases.
* Monitor outbound connections.
* Log denied traffic.
* Review firewall rules periodically.

### Frequency

Monitoring should occur continuously, with formal firewall-rule reviews at least monthly and after significant infrastructure changes.

---

## Control 2 — Identity & MFA Hardening

### Implementation

Every employee should have an individual account.

Password sharing should be prohibited, and MFA should be enabled for employee and privileged accounts.

### Controls

* Unique accounts
* Strong passwords
* MFA
* RBAC
* Account lifecycle management
* Privileged-access restrictions
* Authentication monitoring

### Frequency

Authentication controls should operate continuously.

Access reviews should be performed periodically and whenever employees change roles or leave the organization.

---

## Control 3 — Database Credential Hardening

### Implementation

The default database administrator credential should be replaced immediately.

Database administration should be restricted to authorized administrators and systems.

### Controls

* Unique administrator credentials
* Secure credential storage
* Credential rotation
* Restricted database connectivity
* Disabled unnecessary accounts
* Privileged activity logging

### Frequency

Credential rotation should follow organizational security policy, while privileged activity should be continuously monitored.

---

## Expected Result

These controls provide multiple layers of protection.

If an attacker obtains a user's password, MFA can prevent account takeover.

If an attacker attempts to reach internal services, firewall restrictions can block unauthorized traffic.

If an attacker reaches the database environment, restricted privileges and secure administrator credentials can limit further access.

