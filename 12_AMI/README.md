# Amazon Machine Image (AMI)

## Why AMI exists
Creating servers manually every time is slow and inconsistent.

## What is an AMI?
An AMI is a template that contains:
- Operating system
- Root volume snapshot
- Boot configuration

## Key characteristics
- Immutable (cannot be modified)
- Region-specific
- Used to launch EC2 instances

## AMI vs Snapshot
- Snapshot: backup of a disk
- AMI: launch template for EC2

## Real-world analogy
AMI is a ready-made server image.

## Diagram
Snapshot → AMI → EC2 Instance

## Interview explanation
"An AMI is an immutable template used to launch EC2 instances consistently."
