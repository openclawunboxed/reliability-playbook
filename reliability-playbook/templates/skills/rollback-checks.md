# rollback checks

before update:
- record version
- backup workspace
- backup memory
- note last known good version

after update:
- rerun tiny workflow
- verify proof artifact
- verify cron canary
- verify memory write and retrieval
