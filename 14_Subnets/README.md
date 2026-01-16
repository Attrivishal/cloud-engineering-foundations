# Subnets

## Why subnets exist
Not all servers should be exposed to the internet.

## What is a subnet?
A subnet is a logical network segment inside a VPC.

## Public subnet
- Route to Internet Gateway
- Can receive internet traffic

## Private subnet
- No direct IGW route
- Not reachable from internet

## Important rule
Subnet type depends on routing, not name.

## Real-world analogy
Subnets are neighborhoods inside a city.

## Diagram
VPC
 ├── Public Subnet
 └── Private Subnet

## Interview explanation
"A subnet becomes public or private based on its route table."
