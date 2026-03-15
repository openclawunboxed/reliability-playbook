# reliability audit scorecard

score each category from 0 to 5.

## 1. execution reliability
- 0 = tasks often report success without doing anything
- 1 = actions sometimes work but fail silently
- 2 = some actions are verified, many are not
- 3 = most critical actions are verified
- 4 = all critical actions are verified
- 5 = all actions are verified and failures trigger escalation

score: ____

## 2. scheduling reliability
- 0 = no scheduled task testing
- 1 = cron runs but is not checked
- 2 = some scheduled tasks are observed manually
- 3 = cron canary exists
- 4 = canary exists and failures pause important workflows
- 5 = canary, logs, and escalation paths are in place

score: ____

## 3. memory hygiene
- 0 = memory is a dumping ground
- 1 = memory is rarely reviewed
- 2 = some pruning happens
- 3 = short-term and stable memory are separated
- 4 = memory is reviewed on a schedule
- 5 = memory boundaries, pruning, and reset conditions are explicit

score: ____

## 4. cost control
- 0 = token spend is unpredictable
- 1 = costs are noticed after the damage is done
- 2 = some context trimming exists
- 3 = model choice is matched to task type
- 4 = loops and large context are controlled
- 5 = model routing, context budgets, and failure caps are explicit

score: ____

## 5. rollback readiness
- 0 = no rollback process
- 1 = backups are inconsistent
- 2 = version info is sometimes recorded
- 3 = workspace and memory are backed up before updates
- 4 = test workflow is rerun after updates
- 5 = rollback path is rehearsed and documented

score: ____

## 6. security posture
- 0 = agent has broad access by default
- 1 = secrets and tools are loosely controlled
- 2 = some least-privilege thinking exists
- 3 = only required tools are enabled
- 4 = secrets, permissions, and risky actions are bounded
- 5 = least privilege, isolation, and review are standard practice

score: ____

## 7. observability / proof
- 0 = no reliable logs or proof artifacts
- 1 = logs exist but are not useful
- 2 = some workflows leave evidence
- 3 = critical workflows leave proof artifacts
- 4 = proof artifacts and logs are reviewed
- 5 = proof artifacts, logs, and escalation rules are systematic

score: ____

## total

add all scores.

total: ____ / 35

## score bands

- 0 to 10 = fragile demo
- 11 to 20 = risky operator setup
- 21 to 30 = usable with guardrails
- 31 to 35 = trustworthy workflow base
