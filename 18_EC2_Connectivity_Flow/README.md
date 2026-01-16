# EC2 Connectivity Flow

## Why this topic matters
Most EC2 issues are connectivity-related.

## End-to-end request flow
User
→ Internet
→ Public IP
→ Internet Gateway
→ Route Table
→ Subnet
→ Security Group
→ EC2
→ OS Firewall
→ Application

## Debugging mindset
Check each layer step by step.

## Common failure points
- Missing public IP
- Wrong route table
- Security group blocking port
- Service not running

## Diagram
Layered flow from user to application

## Interview explanation
"EC2 connectivity depends on networking, routing, security groups, and application state."
