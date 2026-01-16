# Load Balancer Fundamentals (ALB Focused)

## 1. Why Load Balancer Exists (The Real Problem)
If an application runs on a single EC2 instance:
- If EC2 crashes → application is down
- If traffic increases → server becomes slow
- This creates a single point of failure

Modern applications must be:
- Highly available
- Scalable
- Fault tolerant

This is why load balancers exist.

---

## 2. What Load Balancing Means
Load balancing means distributing incoming user traffic
across multiple backend servers instead of sending all traffic
to a single server.

Instead of:
User → EC2

We use:
User → Load Balancer → Multiple EC2s

---

## 3. What Is a Load Balancer?
A load balancer is a service that:
- Receives traffic from users
- Checks which backend servers are healthy
- Forwards requests only to healthy servers

Users never directly connect to EC2 instances.

---

## 4. Application Load Balancer (ALB)
ALB is the most commonly used AWS load balancer.

### Key characteristics:
- Works at Layer 7 (Application layer)
- Understands HTTP and HTTPS
- Can route traffic based on:
  - URL path
  - Hostname
  - Headers

Example routing:
- /api → EC2 group A
- /images → EC2 group B

---

## 5. Target Groups
A target group is a logical group of backend servers
that receive traffic from the load balancer.

Targets can be:
- EC2 instances
- IP addresses

ALB always sends traffic to a target group, not directly to EC2.

---

## 6. Health Checks (Very Important)
The load balancer continuously checks backend servers.

If:
- EC2 crashes
- Application stops responding

Then:
- ALB marks it unhealthy
- Stops sending traffic to it automatically

This provides fault tolerance.

---

## 7. Where Load Balancer Lives (Network Design)
- ALB is placed in a **public subnet**
- EC2 instances are placed in **private subnets**

Traffic flow:
User → ALB (public) → EC2 (private)

This improves security.

---

## 8. Security Group Design
- ALB Security Group:
  - Allow 80/443 from internet
- EC2 Security Group:
  - Allow traffic only from ALB Security Group

EC2 is never exposed to the internet.

---

## 9. What Load Balancer Does NOT Do
- Does not fix application bugs
- Does not store data
- Does not replace servers
- Only distributes traffic

---

## 10. Real-World Analogy
Think of a restaurant:
- Customers = users
- Receptionist = load balancer
- Tables = EC2 servers

The receptionist sends customers only to available tables.

---

## 11. Diagram to Include
Draw or include a diagram showing:
User → ALB → Target Group → Multiple EC2s (private subnet)

---

## 12. Interview Explanation (Short & Strong)
"A load balancer distributes incoming traffic across multiple servers
to improve availability, scalability, and fault tolerance."
