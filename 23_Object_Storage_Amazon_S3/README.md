# Object Storage – Amazon S3

Amazon S3 is AWS’s object storage service used to store data independently
of compute resources.

---

## Why S3 Exists
Storing data on servers creates problems:
- Data loss if server fails
- Poor scalability
- Difficult sharing

S3 solves this by providing:
- Independent storage
- High durability
- Unlimited scale

---

## What S3 Is
- Object storage (not a filesystem)
- Stores data as objects inside buckets
- Accessible via HTTP / API

Key components:
- Bucket: container for objects
- Object: actual file
- Key: object name/path

---

## Object Storage vs Block Storage

- EBS:
  - Attached to one EC2
  - Used for OS and app data
- S3:
  - Independent of EC2
  - Used for files, logs, backups

Golden rule:
> EC2 is disposable, data must survive.

---

## S3 in Real Architecture

User
→ ALB
→ EC2 (Private Subnet)
→ IAM Role
→ S3


Use cases:
- User uploads
- Logs
- Backups
- Static website hosting
- Shared data across instances

---

## S3 Security

Access is controlled by:
- IAM policies (identity-based)
- Bucket policies (resource-based)

Best practices:
- S3 is private by default
- Use IAM roles
- Block public access unless required

---

## Versioning, Lifecycle & Backups

- Versioning protects against accidental deletion
- Lifecycle rules control cost
- S3 is the primary backup destination in AWS

---

## Interview Summary
"S3 is an object storage service used to store application data, logs, and backups
independently of EC2, ensuring durability and scalability."
