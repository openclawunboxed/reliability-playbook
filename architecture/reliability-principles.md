# reliability principles

## the problem

most openclaw setups fail in boring ways:

- tasks reported as complete when the final artifact is missing
- cron jobs that still run but produce garbage or nothing
- memory that grows into contradictory sludge
- token burn caused by oversized context and recursive loops
- updates that silently change behavior

## the core principle

a task is not done because the model said it is done.

a task is done when the intended result exists in the target system and has been directly verified.

## the five layers of reliability

### 1. execution reliability

did the action actually execute?

### 2. state reliability

did the destination system change in the intended way?

### 3. schedule reliability

did the workflow run at the correct time and keep running over time?

### 4. environment reliability

did updates, permissions, dependencies, or hardware change the system behavior?

### 5. proof reliability

do you have logs, artifacts, or checks that confirm the workflow really worked?

## design consequences

- every critical workflow needs a proof step
- every scheduled workflow needs a canary
- every update needs a quarantine and rollback path
- every memory system needs pruning and boundaries
- every agent should have the minimum permissions required
