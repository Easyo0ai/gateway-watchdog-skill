# Gateway Watchdog

## Overview
The **Gateway Watchdog** ensures high availability of the OpenClaw Gateway daemon. It automatically detects service interruptions, unexpected shutdowns, or unresponsive states, and safely restarts the gateway process without requiring manual intervention.

## Features
- **Continuous Monitoring:** Periodically checks the `openclaw gateway status` to ensure the daemon is running and responsive.
- **Auto-Recovery:** If the gateway is down or enters an error state, the watchdog executes `openclaw gateway restart`.
- **System Stability:** Built with a focus on security and reliability, preventing long downtimes.
- **Logging & Alerting:** Integrates with your workspace `HEARTBEAT.md` lifecycle to log any recovery events.

## Installation
Install via ClawHub:
```bash
clawhub install gateway-watchdog
```

## How it works (for the Agent)
If you are equipped with this skill, you should integrate `gateway-watchdog` logic into your background tasks (e.g., your `HEARTBEAT.md` routine). 

When instructed to run a health check or stabilize the system, use the CLI command:
`openclaw gateway status`

If the result indicates the service is dead, inactive, or unresponsive, immediately execute:
`openclaw gateway restart`

Record any crashes and subsequent restarts in your `memory/` logs so the user stays informed of system instability implicitly.

## License
MIT
