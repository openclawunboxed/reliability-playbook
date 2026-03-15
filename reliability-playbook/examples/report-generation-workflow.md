# example: report generation workflow

## goal
compile a daily summary report from source data.

## common failure modes
- source data fetch silently fails
- report file not written
- outdated memory contaminates summary

## hardening moves
- verify source fetch response
- verify report file exists and is not empty
- use small bounded context for the report task
- leave timestamped proof artifact in outputs/
