# AWS EC2 – Overview

This chapter provides a clear overview of **Amazon EC2** as a cloud compute
service. It focuses on **what EC2 is, how it behaves, and why it is used**,
without going into deep configuration details.

---

## What Is Amazon EC2?

> **Amazon EC2 (Elastic Compute Cloud) is an AWS service that provides
resizable virtual machines in the cloud.**

In simple terms:
- EC2 lets you **run virtual servers on AWS**
- You control the operating system and software
- AWS manages the underlying hardware

EC2 is the **compute layer** of most AWS architectures.

---

## What an EC2 Instance Represents

An **EC2 instance** is:
- A virtual machine created from an image (AMI)
- Capable of running Linux or Windows
- Used to host applications, APIs, services, or background jobs

Although it feels like a traditional server, an EC2 instance is:
- Easy to create
- Easy to delete
- Easy to replace

Key mindset:
> EC2 instances are **temporary compute resources**, not permanent machines.

---

## Why EC2 Is Called “Elastic”

The word **Elastic** means:
- You can scale **up** (bigger instance)
- You can scale **out** (more instances)
- You can scale **down** when demand reduces

This elasticity allows applications to:
- Handle traffic spikes
- Reduce cost during low usage
- Recover from failures automatically (with ASG)

---

## Why EC2 Is Used

EC2 is commonly used because it allows you to:

- Launch compute resources in minutes
- Choose the operating system and instance size
- Scale based on traffic or workload
- Pay only for the time the instance runs
- Integrate with other AWS services (IAM, S3, CloudWatch)

EC2 is flexible enough to support:
- Web applications
- Backend services
- Batch processing
- Development and testing environments

---

## Pay-As-You-Use Model

Unlike traditional servers:
- You don’t buy hardware
- You don’t pay upfront
- You don’t pay when instances are stopped

You are billed based on:
- Instance type
- Running time
- Storage and data transfer

This model enables:
> Cost-efficient and on-demand compute usage.

---

## EC2 Instance Lifecycle (High Level)

An EC2 instance typically goes through:

- **Launch** – instance is created
- **Running** – instance is active
- **Stopped** – instance is powered off
- **Terminated** – instance is permanently deleted

Important note:
> Once terminated, an EC2 instance **cannot be recovered**.

This is why EC2 should be treated as **replaceable compute**.

---

## EC2 in Cloud Architecture (Placement)

EC2 does **not work alone**.

Typical placement:
