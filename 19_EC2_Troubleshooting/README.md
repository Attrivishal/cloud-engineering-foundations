Why EC2 Troubleshooting Matters

In real cloud roles, servers will fail.

Knowing how to troubleshoot EC2 issues is more important than launching EC2 instances.

This section focuses on how to think, not just commands.

🔴 Common EC2 Issues & Troubleshooting Approach
1️-- EC2 Instance Not Reachable (SSH Fails)

Possible Causes

Security Group blocking port 22

Wrong key pair

Instance stopped or failed

Disk full

Network misconfiguration

How to Debug

Check instance state

Verify Security Group inbound rules

Confirm correct key pair

Check system status checks

Review logs (via console / CloudWatch)

2️-- Website Not Accessible but Instance is Running

Possible Causes

Application not running

Wrong port exposed

Security Group misconfiguration

ALB health check failing

How to Debug

SSH into instance

Check service status

Verify listening ports

Check Security Group rules

Review application logs

3️-- High CPU Usage

Possible Causes

Application bug

Traffic spike

Infinite loop

Resource under-provisioning

How to Debug

Check CloudWatch CPU metrics

SSH into instance

Use top / htop

Identify offending process

Restart or optimize service

4-- Disk Space Full

Symptoms

SSH login fails

Applications crash

Logs stop writing

How to Debug

Check disk usage (df -h)

Identify large files (du -sh)

Clear unnecessary logs

Resize EBS if required

5-- EC2 Becomes Unhealthy in ALB

What Happens

ALB health check fails

Traffic is stopped to instance

Auto Scaling replaces instance

What to Check

Health check path

Application response

Instance logs

Security Group rules

--> Troubleshooting Mindset (VERY IMPORTANT)

Always think in this order:

Is it running?
 → Is it reachable?
 → Is the service healthy?
 → Is the resource overloaded?
 → Are logs showing errors?


This mindset matters more than commands.