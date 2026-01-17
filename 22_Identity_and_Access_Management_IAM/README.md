# Identity and Access Management (IAM)

IAM is the security foundation of AWS. It controls **who can access AWS
resources and what actions they can perform**.

---

## Why IAM Exists
AWS is API-driven. Every action (launch EC2, read S3, delete resources)
is an API call. Without IAM:
- Anyone could access resources
- No control or accountability
- High security risk

IAM exists to enforce **authentication and authorization**.

---

## Core IAM Concepts

IAM is built on three main components:

### 1. IAM Users
- Represent **humans**
- Used for AWS Console or CLI access
- Have long-term credentials

Best practice:
- Use users only for people
- Enable MFA
- Avoid access keys if possible

---

### 2. IAM Policies
- JSON documents that define permissions
- Specify:
  - Effect (Allow / Deny)
  - Action (what can be done)
  - Resource (on what)

Important rules:
- Default deny
- Explicit deny always wins
- Least privilege is mandatory

---

### 3. IAM Roles
- Used by **AWS services and applications**
- Do not have long-term credentials
- Provide temporary credentials

Roles are safer than users and are
the correct way for EC2, Lambda, and other services to access AWS.

---

## EC2 Accessing AWS Services Securely

Correct flow:


EC2
→ IAM Role
→ Temporary Credentials
→ AWS Service (S3, CloudWatch, etc.)


Why this is secure:
- No credentials stored on EC2
- Automatic rotation
- Least privilege

---

## Best Practices
- Never use root for daily work
- Enable MFA on root and admin users
- Use roles instead of users for services
- Grant only required permissions

---

## Interview Summary
"IAM controls access in AWS using users, roles, and policies. Humans use users,
services use roles, and permissions are defined using least privilege policies."
