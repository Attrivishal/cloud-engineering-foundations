# CloudWatch Alarms & Real-World Monitoring Scenarios

This chapter focuses on **how monitoring is actually used in production**.
It explains how CloudWatch alarms are designed, how engineers think about
thresholds, and how real system failures are detected and handled.

This is the bridge between **deploying systems** and **running systems**.

---

## Why Alarms Are Required

Metrics alone are not enough.
Engineers cannot constantly watch dashboards.

Alarms exist to:
- Detect failures early
- Prevent silent outages
- Notify engineers automatically
- Enable fast reaction

Monitoring without alarms gives false confidence.

---

## Alarm Mental Model (Very Important)

CloudWatch alarms follow a simple flow:
----------------------------------------
Metric → Alarm → Action

- Metrics measure system behavior
- Alarms evaluate metrics against thresholds
- Actions notify humans or trigger automation

Alarms **do not fix problems** — they surface them.

---

## Core Alarm Components

Every alarm is built using:

- Metric (what to monitor)
- Threshold (when it is a problem)
- Period & duration (how long it must stay bad)
- Action (what happens next)

Example:
- CPUUtilization > 70%
- For 5 minutes
- Trigger notification

---

## Choosing the Right Metrics

### EC2 Metrics (Must Monitor)

- CPUUtilization  
- StatusCheckFailed  
- NetworkIn / NetworkOut  

These metrics indicate:
- Load on instance
- Instance health
- Traffic anomalies

---

### ALB Metrics (Application Health)

- HealthyHostCount  
- HTTP 5xx errors  
- TargetResponseTime  

These metrics detect:
- Application crashes
- Backend failures
- Performance degradation

---

### ASG Metrics (Availability & Scaling)

- GroupInServiceInstances  
- GroupDesiredCapacity  
- Scaling activities  

These metrics ensure:
- Minimum capacity is maintained
- Scaling works as expected

---

## Thresholds: How Engineers Think

Thresholds are not random numbers.

Key principles:
- Understand baseline behavior
- Avoid instant triggers
- Use duration to prevent false alarms

Common safe starting points:
- CPU > 70% for 5 minutes
- StatusCheckFailed ≥ 1 for 2 minutes
- Unhealthy targets ≥ 1 for 2–3 minutes

Duration is as important as threshold.

---

## Alarm Actions

### Notification (Most Common)
CloudWatch Alarm
→ SNS
→ Email / SMS / Chat



This alerts engineers immediately.

---

### Automation (Advanced)

- Auto Scaling actions
- Lambda-based automation

At entry-level roles:
- Alerting is the primary responsibility
- Automation comes later

---

## Real-World Failure Scenarios

### Scenario 1: High CPU Usage

Alarm:
- CPU > 70% for 5 minutes

Possible causes:
- Traffic spike
- Inefficient code
- Background jobs

Engineer response:
1. Check metric trend
2. Check ALB traffic
3. Check logs
4. Scale or fix application

---

### Scenario 2: Instance Health Check Failure

Alarm:
- StatusCheckFailed ≥ 1

Meaning:
- OS or network issue
- Instance unhealthy

Response:
- ASG replaces instance automatically
- Engineer investigates root cause later

---

### Scenario 3: ALB Shows Unhealthy Targets

Alarm:
- HealthyHostCount < desired

Possible causes:
- Application stopped
- Security group misconfiguration
- Failed deployment

Response:
- Check target group health reason
- Verify security groups
- Restart or rollback application

---

### Scenario 4: No Alarm, But Users Report Issues

Lesson:
- Infrastructure may be healthy
- Application-level monitoring is missing

Action:
- Add alarms for:
  - Response time
  - HTTP 5xx errors

Monitoring must reflect **user experience**.

---

## Common Monitoring Mistakes

- Monitoring only CPU
- No alarm duration
- No notifications configured
- Too many noisy alarms
- Ignoring alarms

Effective monitoring uses **few meaningful alarms**.

---

## CloudWatch in Final Architecture
User
→ ALB
→ ASG (EC2 in private subnet)
→ IAM Role
→ S3
→ CloudWatch (metrics + alarms)
→ SNS (notifications)


CloudWatch provides visibility across the entire system.

---

## Interview Summary

- Metrics show system health
- Logs explain failures
- Alarms detect problems early
- CloudWatch does not fix issues
- Engineers analyze and respond

CloudWatch turns deployments into **operational systems**.


