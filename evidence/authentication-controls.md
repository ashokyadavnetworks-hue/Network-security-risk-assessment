# Authentication Controls

## Objective

Strengthen user authentication and reduce the risk of unauthorized access caused by shared or compromised credentials.

## Identified Issue

The organization currently allows employees to share passwords, and Multifactor Authentication (MFA) is not implemented.

These weaknesses increase the risk of unauthorized account access and reduce individual accountability.

## Recommended Controls

### 1. Unique User Accounts

Every employee should have an individual account.

Shared accounts and shared passwords should be prohibited.

Individual accounts provide accountability by allowing security teams to associate activity with a specific user.

### 2. Multifactor Authentication

MFA should be implemented for:

- Employee accounts
- Administrative accounts
- Remote access
- Systems containing sensitive information
- Privileged accounts

MFA provides an additional layer of protection if a password is compromised.

### 3. Strong Password Policy

The organization should establish a password policy that includes:

- Strong and unique passwords
- No password sharing
- Prevention of inappropriate password reuse
- Account protection after repeated failed login attempts
- Secure management of privileged credentials

### 4. Role-Based Access Control

Users should only receive the permissions required for their job responsibilities.

Administrative privileges should be limited to authorized personnel.

## Monitoring

Authentication activity should be monitored for:

- Repeated failed login attempts
- Unusual login locations
- Unusual login times
- Multiple authentication failures
- Suspicious privileged access

## Review Frequency

Authentication controls should operate continuously.

User accounts and privileges should be reviewed periodically and whenever an employee changes roles or leaves the organization.

## Expected Security Benefit

These controls reduce the risk associated with stolen or shared credentials, improve user accountability, and make unauthorized access more difficult.
