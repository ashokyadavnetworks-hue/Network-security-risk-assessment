# Network Security Risk Assessment & Hardening Plan

## Overview

This project presents a security risk assessment and network hardening strategy for a hypothetical social media organization that experienced a major data breach resulting in the exposure of customer personal information.

The assessment identifies four major security weaknesses within the organization's environment and proposes practical network and access-control hardening measures to reduce the likelihood and impact of future security incidents.

The project is designed from the perspective of a **Security Analyst** responsible for assessing vulnerabilities, prioritizing risks, recommending security controls, and developing a sustainable hardening strategy.

---

## Scenario

A social media organization experienced a significant data breach that compromised customer information, including names and addresses.

A subsequent security assessment identified four major vulnerabilities:

1. Employees share account passwords.
2. The database administrator account uses a default password.
3. Firewalls lack effective inbound and outbound traffic-filtering rules.
4. Multifactor authentication (MFA) is not implemented.

These weaknesses create opportunities for unauthorized access, credential compromise, lateral movement, database compromise, and data exfiltration.

---

## Project Objectives

The primary objectives of this assessment are to:

* Identify and prioritize security vulnerabilities.
* Assess the potential impact of each vulnerability.
* Recommend appropriate network-hardening controls.
* Apply least-privilege principles.
* Strengthen authentication and access management.
* Improve firewall traffic control.
* Secure privileged database access.
* Reduce the organization's attack surface.
* Establish repeatable security-hardening practices.
* Provide recommendations for continuous monitoring and review.

---

## Security Assessment

### Vulnerability 1: Password Sharing

**Risk:** High

Employees sharing passwords creates a lack of individual accountability and increases the likelihood of unauthorized account access.

If one employee's password is exposed, attackers may be able to access systems under another user's identity.

### Recommended Controls

* Require unique credentials for every employee.
* Prohibit credential sharing.
* Enforce strong password policies.
* Implement centralized identity and access management.
* Apply role-based access control (RBAC).
* Monitor authentication logs.
* Disable inactive accounts promptly.

### Expected Security Benefit

Unique identities improve accountability and make suspicious authentication activity easier to investigate.

---

## Vulnerability 2: Default Database Administrator Password

**Risk:** Critical

Using a default administrator password significantly increases the risk of unauthorized database access.

If attackers discover or obtain the default credentials, they could potentially gain privileged access to sensitive customer information.

### Recommended Controls

* Immediately replace the default administrator password.
* Use a strong, unique administrative credential.
* Store privileged credentials securely.
* Restrict database administrative access.
* Disable unnecessary database accounts.
* Implement credential rotation.
* Monitor privileged database activity.

### Expected Security Benefit

These controls reduce the probability of unauthorized privileged access and limit exposure of sensitive customer information.

---

## Vulnerability 3: Missing Firewall Traffic Rules

**Risk:** Critical

Firewalls without appropriate filtering rules provide insufficient control over network traffic.

Unrestricted inbound traffic can expose internal services to external attackers, while unrestricted outbound traffic can make command-and-control communication and data exfiltration more difficult to detect.

### Recommended Controls

Implement a restrictive firewall policy based on least privilege.

#### Inbound Traffic

* Deny unnecessary inbound connections.
* Allow only required services.
* Restrict administrative services to authorized networks.
* Block unused ports.
* Log denied connection attempts.

#### Outbound Traffic

* Restrict unnecessary outbound connections.
* Control access to known services.
* Monitor unusual outbound traffic.
* Log suspicious connection attempts.

### Security Principle

**Default Deny**

Traffic should be denied unless it is explicitly required and authorized.

### Expected Security Benefit

Firewall filtering reduces the organization's exposed attack surface and helps prevent unauthorized network communication.

---

## Vulnerability 4: No Multifactor Authentication

**Risk:** High

Without MFA, compromised usernames and passwords may be sufficient for attackers to access organizational systems.

### Recommended Controls

Implement MFA for:

* Employee accounts
* Administrative accounts
* Remote access
* Cloud services
* Privileged systems

Where possible, phishing-resistant authentication should be preferred.

### Expected Security Benefit

MFA introduces an additional authentication factor, reducing the likelihood that stolen passwords alone can be used to compromise accounts.

---

# Risk Prioritization

| Vulnerability             | Likelihood | Impact   | Risk     |
| ------------------------- | ---------- | -------- | -------- |
| Password sharing          | High       | High     | High     |
| Default database password | High       | Critical | Critical |
| Missing firewall rules    | High       | Critical | Critical |
| No MFA                    | High       | High     | High     |

The database administrator password and firewall configuration should receive the highest immediate remediation priority because compromise of either could provide attackers with significant access to sensitive systems or data.

---

# Network Hardening Strategy

The proposed hardening strategy follows a defense-in-depth approach.

## Layer 1 — Identity Security

* Unique user accounts
* Strong password policy
* MFA
* RBAC
* Privileged account management

## Layer 2 — Network Security

* Firewall filtering
* Network segmentation
* Restricted administrative access
* Inbound and outbound traffic monitoring

## Layer 3 — Database Security

* Remove default credentials
* Restrict database access
* Secure privileged accounts
* Credential rotation
* Database activity monitoring

## Layer 4 — Monitoring

* Authentication logging
* Firewall logging
* Privileged activity monitoring
* Alerting for suspicious behavior
* Periodic security reviews

---

# Proposed Firewall Policy

A simplified example policy is shown below.

| Direction                    | Traffic                        | Action | Reason                         |
| ---------------------------- | ------------------------------ | ------ | ------------------------------ |
| Internet → Internal          | Unsolicited traffic            | DENY   | Reduce attack surface          |
| Internet → Public Web Server | HTTPS                          | ALLOW  | Required public service        |
| Internal → Database          | Authorized application traffic | ALLOW  | Required application function  |
| User Network → Database      | Direct access                  | DENY   | Prevent unnecessary access     |
| Admin Network → Database     | Authorized management traffic  | ALLOW  | Administrative requirement     |
| Internal → Internet          | Required services              | ALLOW  | Business operations            |
| Internal → Internet          | Unnecessary traffic            | DENY   | Reduce abuse/exfiltration risk |

This policy should be adapted to the organization's actual network architecture and business requirements.

---

# Hardening Schedule

Security hardening should not be treated as a one-time activity.

### Daily

* Review critical security alerts.
* Monitor authentication events.
* Monitor firewall alerts.
* Investigate suspicious privileged activity.

### Weekly

* Review firewall logs.
* Review failed authentication attempts.
* Check for newly identified security issues.
* Review privileged account activity.

### Monthly

* Review firewall rules.
* Review user privileges.
* Remove unnecessary accounts.
* Review database access.
* Verify security configurations.

### Periodically

* Rotate privileged credentials according to organizational policy.
* Perform vulnerability assessments.
* Review access-control policies.
* Test incident-response procedures.
* Conduct security awareness training.

---

# Incident Prevention Strategy

The proposed controls reduce the probability of future breaches through multiple defensive layers.

### Example Attack Chain

```text
Compromised Employee Credential
             ↓
        MFA Challenge
             ↓
     Unauthorized Access Blocked
             ↓
     Firewall Restrictions
             ↓
     Lateral Movement Limited
             ↓
    Database Access Restricted
             ↓
     Sensitive Data Protected
```

Defense-in-depth ensures that failure of one control does not automatically result in complete network compromise.

---

# Monitoring & Detection

The organization should monitor:

* Failed login attempts
* Successful logins from unusual locations
* Privileged account activity
* Database authentication events
* Unexpected firewall connections
* Unusual outbound traffic
* Repeated access-denied events
* Changes to firewall rules
* Changes to privileged accounts

Alerts should be investigated by security personnel and escalated according to the organization's incident-response procedures.

---

# Security Framework Alignment

The recommendations support the principles of the **NIST Cybersecurity Framework**.

| Security Activity                | Relevant Function |
| -------------------------------- | ----------------- |
| Asset and account identification | Identify          |
| Risk assessment                  | Identify          |
| Firewall hardening               | Protect           |
| MFA implementation               | Protect           |
| Access control                   | Protect           |
| Security monitoring              | Detect            |
| Incident investigation           | Respond           |
| Security improvements            | Recover           |

---

# Implementation Roadmap

## Phase 1 — Immediate

* Change the default database administrator password.
* Disable unnecessary accounts.
* Stop password sharing.
* Identify critical exposed services.
* Implement essential firewall rules.

## Phase 2 — Short Term

* Deploy MFA.
* Implement RBAC.
* Restrict database access.
* Establish firewall logging.
* Implement centralized authentication monitoring.

## Phase 3 — Long Term

* Introduce network segmentation.
* Implement privileged access management.
* Establish continuous vulnerability management.
* Conduct periodic security assessments.
* Improve security awareness training.
* Integrate security monitoring with a SIEM platform.

---

# Expected Security Improvements

After implementing the proposed controls, the organization should achieve:

* Reduced unauthorized access risk.
* Reduced attack surface.
* Improved account accountability.
* Stronger privileged-access security.
* Better network visibility.
* Improved detection capabilities.
* Reduced probability of credential-based attacks.
* Improved protection of customer information.

---

# Limitations

This project is a **security assessment and proposed hardening plan based on a hypothetical organizational scenario**.

No production environment was accessed or modified.

Firewall rules, MFA controls, database security controls, and monitoring recommendations are presented as proposed security measures rather than claims of deployment in a real organization.

---

# Skills Demonstrated

* Security risk assessment
* Vulnerability identification
* Network hardening
* Firewall security
* Authentication security
* Access control
* Database security
* Least privilege
* Defense in depth
* Security monitoring
* Risk prioritization
* Security documentation
* NIST CSF concepts

---

# Conclusion

The assessment identified several weaknesses that could contribute to unauthorized access and future data breaches.

The highest-priority recommendations are to eliminate default credentials, implement restrictive firewall rules, enforce unique user credentials, and deploy MFA.

Together, these controls provide multiple layers of protection across identity, network, database, and monitoring environments.

Effective cybersecurity requires continuous assessment rather than one-time remediation. Regular monitoring, access reviews, firewall reviews, vulnerability assessments, and security-policy updates should therefore become part of the organization's ongoing security program.

---

## Disclaimer

This repository is an educational cybersecurity case study based on a hypothetical scenario. It is intended for learning, portfolio development, and defensive security analysis.
