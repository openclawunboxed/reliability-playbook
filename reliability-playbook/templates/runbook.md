# runbook

## purpose
this instance supports one or more defined workflows and should optimize for reliability over novelty.

## workflow rules
- verify final state after every critical action
- use proof artifacts where possible
- log failure points clearly
- do not continue silently after verification fails

## update rules
- backup before updating
- run quarantine tests after updating
- rollback if verification fails
