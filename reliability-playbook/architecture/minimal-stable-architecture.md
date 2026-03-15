# minimal stable architecture

this is the default example layout i recommend for most builders.

it is written to match openclaw's workspace and skills model.

```text
<workspace>/
├── AGENTS.md
├── SOUL.md
├── MEMORY.md
├── USER.md
├── runbook.md
├── memory/
│   └── YYYY-MM-DD.md
├── skills/
│   ├── verify-completion/
│   │   └── SKILL.md
│   ├── cron-safety/
│   │   └── SKILL.md
│   └── rollback-checks/
│       └── SKILL.md
├── outputs/
│   └── proof-artifacts/
└── logs/
    └── cron_canary.log
```

## what goes where

### AGENTS.md
agent-specific operating notes, workflow boundaries, and persistent task rules.

### SOUL.md
short operating rules, behavior boundaries, confidence calibration, and completion standards.

### MEMORY.md
stable memory that should survive across sessions.

### memory/YYYY-MM-DD.md
short-lived or day-scoped working context.

### USER.md
user preferences, assumptions, and stable context that should persist.

### runbook.md
human-readable workflow rules, escalation paths, known commands, and troubleshooting notes.

### skills/
repeatable safety procedures and verification steps, each as a skill folder containing `SKILL.md`.

### outputs/proof-artifacts/
files or records that prove critical actions happened.

### logs/
cron canary output, workflow logs, error traces.

## stable defaults

- one agent first
- one verified workflow first
- one proof artifact per critical action
- one canary per scheduled workflow
- one rollback note before every update
- one memory cleanup review on a schedule
