# cron safety

for every scheduled workflow:

1. maintain a canary task
2. log timestamps and outcomes
3. verify outputs exist
4. pause trust in scheduled workflows if the canary fails
