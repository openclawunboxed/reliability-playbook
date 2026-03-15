# sunday audit

run this once a week.

## execution audit
- can the agent still perform one file write?
- can it still perform one external action you expect?
- does it verify the final state before reporting success?

## scheduling audit
- did the cron canary run?
- did the scheduled output land where expected?
- did any scheduled workflow drift or stop?

## memory audit
- is `today.md` still relevant?
- does `stable-facts.md` contain stale facts?
- is there duplicated or contradictory context?

## cost audit
- did token usage spike unexpectedly?
- is any workflow loading too much context?
- is a stronger model being used for low-value monitoring?

## update audit
- are you still on a version you trust?
- do you know your last known good version?
- do you have fresh backups?

## proof audit
- do critical workflows still leave proof artifacts?
- can you inspect at least one proof artifact from the last week?
