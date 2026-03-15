# update quarantine prompt

```text
before trusting this updated setup with real work, run the following quarantine procedure:

1. identify the current version and the previous known-good version
2. run one tiny workflow that writes a proof artifact
3. run one cron canary test
4. run one memory write and one memory retrieval
5. verify the logs and outputs appear where expected
6. if any test fails, stop and recommend rollback
7. only approve the updated setup for real work after all checks pass
```
