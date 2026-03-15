# example: agency lead monitoring workflow

## goal
monitor inbound leads, add them to the crm, and write a summary report.

## steps
1. watch inbox or source system for new lead events
2. extract lead information
3. add lead to crm
4. write lead summary to report file
5. verify crm entry exists
6. verify report file exists

## common failure before hardening
- agent says task complete
- crm entry missing
- report file missing or incomplete

## hardened version
- completion verification prompt required
- proof artifact path for report file
- crm state checked directly
- cron canary verifies scheduler health

## business consequence
without verification, leads can vanish silently.
with verification, the workflow becomes usable and auditable.
