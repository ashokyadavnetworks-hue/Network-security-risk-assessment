# Security Risk Assessment

## 1. Executive Summary

A hypothetical social media organization experienced a major data breach involving customer personal information. A post-incident assessment identified weaknesses in credential management, database security, firewall configuration, and authentication controls.

The assessment determined that these weaknesses significantly increase the organization's exposure to unauthorized access and data compromise.

The recommended security strategy focuses on three primary areas:

1. Network traffic filtering
2. Identity and authentication hardening
3. Privileged database access protection

These controls are designed around least privilege, defense in depth, and continuous monitoring.

---

## 2. Risk Register

| ID   | Vulnerability             | Likelihood | Impact   | Overall Risk | Priority |
| ---- | ------------------------- | ---------- | -------- | ------------ | -------- |
| R-01 | Password sharing          | High       | High     | High         | P1       |
| R-02 | Default database password | High       | Critical | Critical     | P0       |
| R-03 | Missing firewall rules    | High       | Critical | Critical     | P0       |
| R-04 | No MFA                    | High       | High     | High         | P1       |

---

## 3. Risk R-01 — Password Sharing

### Threat

Shared credentials prevent reliable identification of the individual performing an action.

### Potential Attack

An attacker obtaining a shared employee password could access organizational resources while appearing to be a legitimate user.

### Mitigation

* Unique accounts
* Strong password policy
* MFA
* RBAC
* Authentication logging

### Residual Risk

Medium, assuming authentication monitoring and periodic access reviews are maintained.

---

## 4. Risk R-02 — Default Database Password

### Threat

Default privileged credentials may be publicly known, predictable, or reused across environments.

### Potential Attack

An attacker could attempt default credentials against exposed or internally accessible database services.

### Mitigation

* Replace default password immediately.
* Restrict database access.
* Disable unnecessary administrative accounts.
* Implement credential rotation.
* Monitor privileged database activity.

### Residual Risk

Low to Medium after effective implementation.

---

## 5. Risk R-03 — Missing Firewall Rules

### Threat

Insufficient traffic filtering exposes unnecessary services and communication paths.

### Potential Attack

An external attacker could discover exposed services, exploit vulnerable applications, or establish unauthorized communication.

### Mitigation

* Default-deny inbound policy
* Restrictive outbound policy
* Allow only required services
* Restrict administrative access
* Enable firewall logging
* Periodically review rules

### Residual Risk

Medium, because firewall controls must be continuously reviewed and updated.

---

## 6. Risk R-04 — No MFA

### Threat

Password compromise can directly lead to account compromise.

### Potential Attack

An attacker using stolen credentials could authenticate as a legitimate employee or administrator.

### Mitigation

Deploy MFA across:

* Employee accounts
* Administrative accounts
* Remote access
* Cloud services
* Privileged systems

### Residual Risk

Low to Medium depending on authentication strength and coverage.

---

## 7. Overall Assessment

The organization currently has a high-risk security posture due to weaknesses in authentication, privileged access, and network traffic control.

Immediate remediation should prioritize the default database credentials and firewall configuration, followed by MFA and identity-management improvements.

The organization should establish continuous monitoring and recurring security reviews to prevent security controls from degrading over time.

