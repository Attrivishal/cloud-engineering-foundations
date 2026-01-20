What is a NAT Gateway?

A NAT (Network Address Translation) Gateway allows instances in a private subnet to access the internet securely without being directly exposed to inbound internet traffic.

In simple words:

NAT Gateway lets private EC2 instances go out to the internet, but blocks the internet from coming in.

? Why NAT Gateway is Needed

Private EC2 instances often need to:

Download OS updates

Install packages

Access AWS services (via public endpoints)

Call third-party APIs

But exposing these instances directly to the internet is unsafe.

-> NAT Gateway solves this problem.

-- NAT Gateway Placement (VERY IMPORTANT)
Internet
   ↓
Internet Gateway
   ↓
NAT Gateway (Public Subnet)
   ↓
Private EC2 Instances


Key rules:

NAT Gateway must be in a public subnet

Private subnets route internet-bound traffic to NAT

Internet cannot initiate connections to private EC2

-- Traffic Flow (Step-by-Step)

Private EC2 sends request to the internet

Route table forwards traffic to NAT Gateway

NAT Gateway forwards request to the internet

Response comes back to NAT Gateway

NAT Gateway sends response to EC2

-> Outbound only
-> No inbound access from internet

-- Why NAT Gateway is Secure

No public IP on private EC2

Stateful connection tracking

Only response traffic is allowed back

Reduces attack surface

This follows defense-in-depth principles.

-- Cost Awareness (Important)

NAT Gateway:

Is not Free Tier

Charges per hour + per GB

 For this repository:

NAT Gateway is explained conceptually

Not deployed to avoid unnecessary cost

Interviewers care about understanding, not billing.

 Interview-Ready Explanation

“A NAT Gateway allows private subnet resources to access the internet securely without exposing them to inbound internet traffic. It is commonly used for patching, updates, and outbound access.”

-- Key Takeaways

Private EC2 should not be public

NAT Gateway enables safe outbound access

Must live in a public subnet

Not used blindly due to cost