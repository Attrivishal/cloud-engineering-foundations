# Auto Scaling Group (ASG) Fundamentals

## 1. Why Auto Scaling Exists
Even with a load balancer, someone must:
- Add servers when traffic increases
- Remove servers when traffic decreases
- Replace failed servers

Doing this manually is slow and unreliable.

Auto Scaling automates this process.

---

## 2. What Is Auto Scaling?
Auto Scaling automatically increases or decreases
the number of EC2 instances based on demand or health.

More traffic → more EC2s  
Less traffic → fewer EC2s  

No manual intervention required.

---

## 3. What Is an Auto Scaling Group (ASG)?
An Auto Scaling Group manages a group of EC2 instances.

ASG responsibilities:
- Maintain required number of EC2s
- Launch new EC2s when needed
- Terminate unhealthy EC2s
- Replace failed instances automatically

You manage the group, not individual servers.

---

## 4. Core ASG Concepts
- Minimum capacity: lowest number of EC2s
- Desired capacity: normal number of EC2s
- Maximum capacity: upper limit

Example:
Min = 2  
Desired = 2  
Max = 6  

This ensures high availability.

---

## 5. Scale Out vs Scale In
- Scale Out: add EC2 instances during high traffic
- Scale In: remove EC2 instances during low traffic

This saves cost while maintaining performance.

---

## 6. Auto Scaling + Load Balancer
Best practice architecture:

User → Load Balancer → Auto Scaling Group → EC2s

- ASG automatically registers EC2s with the load balancer
- Load balancer sends traffic only to healthy EC2s

---

## 7. Health Checks & Self-Healing
If an EC2:
- Fails health check
- Crashes
- Becomes unhealthy

Then:
- ASG terminates it
- Launches a new EC2 automatically

This is called **self-healing infrastructure**.

---

## 8. Launch Template
ASG uses a launch template to create EC2s.

Launch template includes:
- AMI
- Instance type
- Security groups
- User data

This ensures all EC2s are identical.

---

## 9. Multi-AZ Architecture
ASG can launch EC2s across multiple Availability Zones.

Benefits:
- High availability
- No single point of failure
- Resilience to AZ outages

---

## 10. Stateless EC2 Requirement
EC2s in ASG must be stateless.

Why?
- Instances can be terminated anytime
- New instances can be created anytime

State must be stored in:
- Database
- S3
- Cache services

---

## 11. Diagram to Include
Draw or include:
User → ALB → ASG → EC2s (multiple AZs)

---

## 12. Interview Explanation (Short & Strong)
"An Auto Scaling Group automatically adjusts the number of EC2 instances
based on traffic and health to ensure availability and scalability."
