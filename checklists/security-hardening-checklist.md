# security hardening checklist

## permissions
- enable only the tools the workflow actually requires
- remove tools that are not essential
- require human approval for destructive or irreversible actions where possible

## secrets
- do not expose broad credentials if narrower credentials work
- isolate secrets from logs and casual outputs
- rotate credentials if a workspace or tool setup has been shared widely

## exposure
- do not expose services more broadly than necessary
- avoid internet exposure when local-only or vpn-only access is enough
- review any browser, websocket, or automation surfaces you enable

## workflows
- separate low-risk monitoring from high-risk execution
- add proof steps to critical actions
- log sensitive failures without leaking secrets
