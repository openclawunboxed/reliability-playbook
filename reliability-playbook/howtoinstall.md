# how to install this repo into openclaw

this repo is a **toolkit**, not a one-click installer.

that means you do **not** load the whole repo into openclaw and hope it magically absorbs the vibes.

you use it in one of two ways:

1. **beginner path**: keep the repo as reference and copy the core pieces into your openclaw workspace
2. **advanced path**: install the reusable procedures as custom skills and keep the rest as reference docs

this guide shows both.

---

## what openclaw expects

openclaw works around a workspace. the official docs point to these files and folders as the core building blocks:

- `AGENTS.md`
- `SOUL.md`
- `USER.md`
- `MEMORY.md`
- `memory/YYYY-MM-DD.md`
- `<workspace>/skills/`

the default workspace is usually:

```text
~/.openclaw/workspace
```

per-agent skills can live in:

```text
<workspace>/skills
```

shared skills visible to all agents on the machine can live in:

```text
~/.openclaw/skills
```

openclaw also supports extra shared skill directories through `skills.load.extraDirs` in config.

---

## fastest install for most users

this is the best path if you want to use the playbook without turning your workspace into a spaghetti cave.

### step 1: keep this repo as reference

clone or download the repo somewhere safe.

example:

```bash
git clone https://github.com/openclawunboxed/reliability-playbook.git
```

or download the zip and extract it.

---

### step 2: open your target openclaw workspace

use your existing agent workspace or make a dedicated one.

you will usually be working in something like:

```text
~/.openclaw/workspace
```

if you use multiple agents, use the specific workspace for the agent you want to harden.

---

### step 3: copy the core behavior into your workspace

use this mapping.

| repo file | where to use it in openclaw | what to do |
|---|---|---|
| `templates/soul.md` | `SOUL.md` | copy the core behavioral rules into your workspace `SOUL.md` |
| `templates/runbook.md` | `AGENTS.md` or `runbook.md` | use it as your operator runbook and startup conventions |
| `prompts/done-means-done.md` | `SOUL.md` or `AGENTS.md` | add the completion standard so the agent must verify outcomes |
| `templates/memory/stable-facts.md` | `MEMORY.md` | keep durable facts, decisions, and stable rules here |
| `templates/memory/today.md` | `memory/YYYY-MM-DD.md` | use for daily notes, working state, and temporary context |
| `checklists/*.md` | keep nearby in workspace or repo | use them as human checklists before updates or live runs |
| `examples/*.md` | repo reference docs | read these after the core setup is in place |

if you only do one thing, do this:

- put the **done means done** rule into `SOUL.md`
- put the **stable facts** structure into `MEMORY.md`
- keep the repo open while you run the audits

that alone makes the toolkit useful.

---

## best install for serious users

if you want openclaw to reuse the procedures directly, turn the reusable pieces into skills.

### step 1: create skill folders

inside your workspace:

```text
<workspace>/skills/verify-completion/
<workspace>/skills/cron-safety/
<workspace>/skills/rollback-checks/
```

or, if you want them shared across all local agents:

```text
~/.openclaw/skills/verify-completion/
~/.openclaw/skills/cron-safety/
~/.openclaw/skills/rollback-checks/
```

### step 2: convert the repo files into skill files

copy these files:

- `templates/skills/verify-completion.md`
- `templates/skills/cron-safety.md`
- `templates/skills/rollback-checks.md`

into the folders above as:

```text
SKILL.md
```

example:

```text
~/.openclaw/skills/verify-completion/SKILL.md
~/.openclaw/skills/cron-safety/SKILL.md
~/.openclaw/skills/rollback-checks/SKILL.md
```

this is the cleanest way to make the repo operational inside openclaw instead of keeping everything as reading material.

### step 3: verify openclaw can see the installed skills

run:

```bash
openclaw skills
```

confirm the skill appears and is eligible. if requirements are missing, openclaw will tell you what is unavailable.


---

## recommended starter workspace layout

here is a practical workspace shape that fits the repo.

```text
<workspace>/
├── AGENTS.md
├── SOUL.md
├── MEMORY.md
├── USER.md
├── memory/
│   └── 2026-03-15.md
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
```

---

## the easiest order to use the repo

for most subscribers, this is the right order:

1. read `README.md`
2. read `article/openclaw-reliability-playbook.md`
3. run `checklists/reliability-audit-scorecard.md`
4. complete `checklists/sunday-audit.md`
5. copy `prompts/done-means-done.md` into `SOUL.md`
6. install the skill files you want
7. use the examples last

that keeps the repo beginner-friendly while still being valuable to experts.

---

## after you copy the files

once your memory files are in place, refresh memory indexing if needed:

```bash
openclaw memory index
openclaw memory status
```

if you want to search what is in memory:

```bash
openclaw memory search "verification"
```

these commands work over `MEMORY.md` and `memory/*.md`.

---

## beginner install in 5 minutes

if you want the shortest path, do this:

### 1. copy these into your workspace

- `prompts/done-means-done.md` → paste into `SOUL.md`
- `templates/memory/stable-facts.md` → paste into `MEMORY.md`
- `templates/skills/verify-completion.md` → save as `<workspace>/skills/verify-completion/SKILL.md`

### 2. run these docs manually

- `checklists/reliability-audit-scorecard.md`
- `checklists/sunday-audit.md`
- `checklists/rollback-checklist.md`

### 3. test one workflow only

examples:

- lead monitoring
- report generation
- crm update

do **not** try to install every file and redesign your whole system on day one.

one workflow first.
then prove it works.
then expand.

---

## what not to do

### do not paste the whole repo into one giant prompt

that creates context sludge and makes the agent worse.

### do not point a production agent at this repo and assume it is fully installed

the repo is structured to support openclaw, but it is not a plug-and-play workspace by default.

### do not skip verification

the entire point of this playbook is to stop fake completion.

### do not use `config.apply`, `configure`, or `doctor` on a live workspace without a backup

there is a recent issue report about `openclaw configure` and `openclaw doctor` overwriting workspace markdown files. back up your workspace first.

---

## best practice setup by user type

### if you are a beginner

- keep the repo open in your browser
- copy only the core files into your workspace
- use one skill
- run one workflow

### if you are intermediate

- install the three reliability skills
- move stable rules into `SOUL.md`, `AGENTS.md`, and `MEMORY.md`
- add proof-artifact and logs folders

### if you are advanced

- make a dedicated reliability agent workspace
- install the skills as shared or per-agent skills
- use the repo as your operating reference
- wire the prompts and checklists into your deployment workflow

---

## references used for this install guide

official docs and current references:

- workspace, migration, and where things live on disk: https://docs.openclaw.ai/help/faq
- memory files and usage: https://docs.openclaw.ai/concepts/memory
- cli memory commands: https://docs.openclaw.ai/cli and https://docs.openclaw.ai/cli/memory
- skills folders and precedence: https://docs.openclaw.ai/tools/skills
- skills config: https://docs.openclaw.ai/tools/skills-config
- agents template and workspace file conventions: https://docs.openclaw.ai/reference/templates/AGENTS
- current issue about workspace file overwrites: https://github.com/openclaw/openclaw/issues/27919

---

## final advice

this repo is most useful when you treat it like a **toolkit** and not a magic spell.

copy the minimum useful pieces into your workspace.
install the skills you actually need.
run one workflow.
verify the result.

that is how you make openclaw more reliable without turning your setup into an archaeological dig.

back up your workspace and `~/.openclaw/openclaw.json` first.
