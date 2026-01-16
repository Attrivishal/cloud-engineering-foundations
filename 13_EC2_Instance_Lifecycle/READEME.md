# EC2 Instance Lifecycle

## Why lifecycle matters
Lifecycle determines billing, data safety, and accessibility.

## EC2 states
- Pending
- Running
- Stopped
- Terminated

## Stop vs Terminate
- Stop: instance off, data safe
- Terminate: instance deleted, data lost (unless backed up)

## Billing behavior
- Running: compute cost
- Stopped: no compute cost, EBS still charged

## Real-world analogy
Stop = switch off computer  
Terminate = throw away computer

## Diagram
Pending → Running → Stopped → Terminated

## Interview explanation
"Stopping an EC2 preserves data, while terminating permanently deletes the instance."
