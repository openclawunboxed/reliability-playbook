# cron canary prompt

```text
create a tiny harmless scheduled task that runs once and writes a timestamped proof artifact to a known location.

requirements:
- do not modify any production data
- log the exact start time
- log the exact completion time
- write a success artifact that can be manually checked
- if the task fails, report the exact failure point
- after the run, verify the artifact exists and the schedule configuration remained unchanged
```
