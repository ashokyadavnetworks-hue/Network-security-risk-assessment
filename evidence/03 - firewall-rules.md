# Firewall Rules

## Objective

Reduce the organization's network attack surface by controlling inbound and outbound traffic using least-privilege principles.

## Identified Issue

The organization's firewalls do not currently have appropriate rules to filter traffic entering and leaving the network.

This can expose unnecessary services and increase the risk of unauthorized network access.

## Recommended Firewall Strategy

The firewall should follow a **default-deny** approach wherever practical.

Traffic should only be permitted when there is a legitimate business or operational requirement.

## Inbound Traffic Rules

| Source | Destination | Traffic | Action | Reason |
|---|---|---|---|---|
| Internet | Public Web Server | HTTPS | ALLOW | Required public service |
| Internet | Internal Network | Unsolicited Traffic | DENY | Protect internal systems |
| Internet | Database | Direct Access | DENY | Prevent external database access |
| Admin Network | Database | Authorized Management | ALLOW | Required administration |
| User Network | Database | Direct Access | DENY | Enforce restricted access |

## Outbound Traffic Rules

| Source | Destination | Traffic | Action | Reason |
|---|---|---|---|---|
| Internal Network | Approved Services | Required Traffic | ALLOW | Business operations |
| Internal Network | Unknown Destinations | Suspicious Traffic | DENY/INVESTIGATE | Reduce potential threats |
| Database | Internet | Unnecessary Traffic | DENY | Reduce data-exfiltration risk |
| Admin Network | Approved Management Services | Required Traffic | ALLOW | Administrative operations |

## Firewall Logging

The firewall should log:

- Denied inbound connections
- Denied outbound connections
- Repeated connection attempts
- Connections to unusual destinations
- Attempts to access restricted services
- Changes to firewall rules

Security teams should review these logs for suspicious activity.

## Rule Maintenance

Firewall rules should be reviewed regularly and whenever:

- A security incident occurs
- New services are introduced
- Network architecture changes
- Applications are added or removed
- New threats are identified

Unused or outdated firewall rules should be removed.

## Expected Security Benefit

Proper firewall filtering reduces unnecessary network exposure and helps prevent unauthorized communication.

Combined with authentication and database security controls, firewall hardening provides an additional layer of defense against unauthorized access and potential data breaches.

## Security Principle

**Least Privilege + Default Deny**

Only required and authorized network traffic should be permitted.
