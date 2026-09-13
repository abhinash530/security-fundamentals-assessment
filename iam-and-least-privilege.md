# Identity and Access Management (IAM) and Least Privilege

## 1. Introduction

Identity and Access Management (IAM) is a fundamental component of cloud security. IAM determines who can access cloud resources, how they authenticate, and what actions they are authorized to perform.

Effective IAM reduces the risk of unauthorized access and limits the potential impact of compromised accounts.

---

## 2. Authentication vs Authorization

### Authentication

Authentication verifies the identity of a user, application, or service.

Examples include:

- Passwords
- Multi-factor authentication (MFA)
- Security keys
- Certificates
- Biometric authentication

### Authorization

Authorization determines what an authenticated identity is allowed to access or perform.

For example, a user may be authenticated successfully but only be authorized to read a specific storage resource rather than modify it.

---

## 3. Principle of Least Privilege

The principle of least privilege means that every user, application, or service should receive only the minimum permissions required to perform its legitimate function.

For example, if an employee only needs to view reports, the employee should receive read access rather than administrative permissions.

### Benefits

Least privilege helps to:

- Reduce the attack surface.
- Limit unauthorized actions.
- Reduce the impact of compromised accounts.
- Prevent accidental changes.
- Improve compliance and accountability.

---

## 4. Role-Based Access Control

Role-Based Access Control (RBAC) assigns permissions according to defined roles.

Example:

| Role | Example Permissions |
|---|---|
| Viewer | Read resources |
| Developer | Manage application resources |
| Database Administrator | Manage databases |
| Security Administrator | Manage security controls |
| Cloud Administrator | Broad infrastructure management |

Users should be assigned only the roles required for their responsibilities.

---

## 5. Multi-Factor Authentication

Multi-factor authentication requires users to provide more than one form of verification.

Common factors include:

1. Something the user knows — password or PIN.
2. Something the user has — security key or authentication device.
3. Something the user is — biometric characteristic.

MFA significantly strengthens account security, particularly for privileged accounts.

---

## 6. Privileged Accounts

Privileged accounts have elevated permissions and can perform sensitive administrative operations.

Examples include:

- Cloud administrators
- Security administrators
- Database administrators
- Infrastructure administrators

These accounts should receive additional protection.

### Recommended controls

- Require MFA.
- Use separate administrative accounts.
- Avoid using privileged accounts for routine activities.
- Monitor administrative actions.
- Review permissions regularly.
- Remove unnecessary privileges.

---

## 7. Service Accounts and Workload Identities

Applications and cloud workloads may require identities to access resources.

These identities should also follow least-privilege principles.

Organizations should:

- Grant only required permissions.
- Avoid embedding long-term credentials in source code.
- Use managed identities where supported.
- Rotate credentials when necessary.
- Monitor workload activity.

---

## 8. Access Review Process

Cloud permissions should not remain unchanged indefinitely.

A regular access review should include:

1. Identify active users and service identities.
2. Review assigned roles.
3. Identify unused permissions.
4. Remove unnecessary access.
5. Review privileged accounts.
6. Document significant changes.
7. Repeat the review periodically.

---

## 9. Example Least-Privilege Scenario

Consider a cloud application where a developer needs to read application logs.

An insecure approach would be to give the developer full administrator access.

A better approach is:

```text
Developer
   |
   +-- Read application logs
   |
   +-- No database administration
   |
   +-- No user management
   |
   +-- No billing administration
   |
   +-- No infrastructure deletion
