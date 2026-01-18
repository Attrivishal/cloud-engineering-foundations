# Monitoring and Observability – CloudWatch

CloudWatch helps engineers **see what is happening inside their systems**
and detect problems early.

---

## Why Monitoring Exists
After deployment, engineers must answer:
- Is the system healthy?
- Is traffic increasing?
- Did something break?

Without monitoring, failures are silent.

---

## What CloudWatch Is
CloudWatch is AWS’s monitoring service that collects:
- Metrics
- Logs
- Alarms

---

## Core CloudWatch Concepts

### Metrics
Numerical values measured over time:
- CPU utilization
- Network traffic
- Request count

Metrics show **system health**.

---

### Logs
Text-based records from applications and systems.
Logs explain **why something failed**.

---

### Alarms
Alarms watch metrics and trigger when thresholds are breached.

Example:
- CPU > 70% for 5 minutes

Alarms prevent silent failures.

---

## CloudWatch in Architecture

User
→ ALB
→ ASG (EC2)
→ S3
→ CloudWatch (metrics + alarms)


CloudWatch observes the system but does not fix it.

---

## Monitoring Mindset
- Metrics tell when something is wrong
- Logs tell why it happened
- Alarms notify engineers early

---

## Interview Summary
"CloudWatch is used to monitor AWS resources using metrics and logs, and alarms
are configured to detect issues before they impact users."

## Monitoring and Alerting Flow

![CloudWatch Alarm Flow](../assets/diagrams/05_cloudwatch_alarm_flow.png)

This diagram shows how metrics are collected, alarms are evaluated, and alerts
are sent to engineers using SNS.
