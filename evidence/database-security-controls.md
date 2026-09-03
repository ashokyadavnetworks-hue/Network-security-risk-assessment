# Database Security Controls

## Objective

Protect sensitive customer information by securing privileged database access and reducing unnecessary database exposure.

## Identified Issue

The organization's database administrator account is configured with a default password.

Default administrative credentials create a significant security risk because unauthorized users may be able to discover or obtain the credentials.

## Recommended Controls

### 1. Replace Default Credentials

The default database administrator password should be changed immediately.

The new credential should be:

- Strong
- Unique
- Not reused elsewhere
- Stored securely
- Accessible only to authorized personnel

### 2. Restrict Database Access

Database access should be limited to authorized users, applications, and systems.

Ordinary employees should not have direct administrative access to the database.

### 3. Apply Least Privilege

Users and applications should receive only the permissions required for their legitimate responsibilities.

Administrative privileges should be restricted to authorized database administrators.

### 4. Secure Privileged Credentials

Privileged database credentials should be securely managed and should not be stored in plain text or shared between employees.

Credential rotation should follow the organization's security policy.

### 5. Monitor Database Activity

Security teams should monitor:

- Database authentication attempts
- Failed administrator logins
- Successful privileged logins
- Permission changes
- Account changes
- Unusual database activity
- Unauthorized access attempts

## Review Frequency

Database permissions should be reviewed periodically.

Privileged credentials should be managed and rotated according to organizational security policy.

Database activity should be monitored continuously where logging capabilities are available.

## Expected Security Benefit

These controls reduce the risk of unauthorized database access and help protect sensitive customer information from compromise.
