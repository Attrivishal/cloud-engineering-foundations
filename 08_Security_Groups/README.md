# Security Groups

## What is a Security Group?
A Security Group is a cloud-level, stateful firewall for EC2 instances.

## Key properties
- Instance-level
- Stateful
- Allow rules only
- Implicit deny

## Best practices
- Do not open SSH to 0.0.0.0/0
- Allow only required ports

## Diagram
Internet → Security Group → EC2

## Interview explanation
"A Security Group controls network traffic for EC2 using allow rules."
