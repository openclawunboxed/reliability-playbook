# rollback checklist

use this before every update.

## before update

- record current openclaw version
- record current model settings
- record enabled tools and permissions
- backup workspace files
- backup memory files
- backup config files
- note the last known good version
- prepare exact rollback commands
- choose one tiny workflow as the test workflow

## after update

- rerun the tiny workflow
- verify the final artifact exists
- verify cron canary still writes output
- verify one memory write
- verify one memory retrieval
- verify logs still appear where expected

## if anything fails

- revert to the last known good version
- restore workspace and memory backups
- rerun the tiny workflow
- do not proceed with the new version until the cause is understood
