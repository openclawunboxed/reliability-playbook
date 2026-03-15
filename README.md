# openclaw reliability playbook

practical assets for building openclaw systems that actually run work.

repo: https://github.com/openclawunboxed/reliability-playbook

## what this is

most openclaw problems are not intelligence problems.

they are reliability problems.

this repo gives you the boring but useful building blocks that make openclaw systems more trustworthy:

- verification prompts
- cron canary patterns
- rollback checklists
- reliability scorecards
- minimal workspace templates
- architecture notes
- real workflow examples
- a beginner-friendly install guide
- the full paid article in `article/openclaw-reliability-playbook.md`

## who this is for

- builders trying to move from demos to real workflows
- founders automating parts of a business
- operators who need reliability, not just novelty
- self-hosters who want fewer silent failures and lower token waste

## start here

### beginner path

1. read `howtoinstall.md`
2. read `article/openclaw-reliability-playbook.md`
3. run `checklists/reliability-audit-scorecard.md`
4. complete `checklists/sunday-audit.md`
5. copy `prompts/done-means-done.md` into `SOUL.md`
6. install one skill from `templates/skills/`
7. harden one workflow only before expanding

### advanced path

1. read `architecture/operator-doctrine.md`
2. read `architecture/minimal-stable-architecture.md`
3. install skills into `<workspace>/skills/` or `~/.openclaw/skills/`
4. use `checklists/rollback-checklist.md` and `checklists/security-hardening-checklist.md`
5. adapt the examples to your own workflow and stack

## repo structure

```text
.
├── article/
│   └── openclaw-reliability-playbook.md
├── architecture/
│   ├── minimal-stable-architecture.md
│   ├── operator-doctrine.md
│   └── reliability-principles.md
├── checklists/
│   ├── reliability-audit-scorecard.md
│   ├── rollback-checklist.md
│   ├── security-hardening-checklist.md
│   └── sunday-audit.md
├── examples/
│   ├── agency-lead-monitoring.md
│   ├── crm-update-workflow.md
│   └── report-generation-workflow.md
├── prompts/
│   ├── completion-verification.md
│   ├── cron-canary.md
│   ├── done-means-done.md
│   ├── memory-hygiene.md
│   └── update-quarantine.md
├── templates/
│   ├── logs/
│   ├── outputs/
│   ├── skills/
│   ├── memory/
│   ├── runbook.md
│   └── soul.md
├── howtoinstall.md
└── assets/
    └── article-links.md
```

## the operator doctrine

- boring before clever
- verify before celebrate
- one workflow before many agents
- rollback before update
- least privilege always
- cheap models for monitoring, strong models for reasoning
- logs or it did not happen

## quick reality check

if your workflows do not verify the destination system, leave proof artifacts, and survive an update without drama, you do not have automation yet.

you have a demo.

## disclaimer

these assets are designed to improve reliability, not guarantee it. openclaw behavior depends on your environment, model choice, permissions, integrations, and update history. test every workflow in your own setup before trusting it with real business work.
