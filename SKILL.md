# openclaw-gateway-watchdog SKILL

An enterprise-ready **Gateway Watchdog** skill for OpenClaw. This skill ensures your Gateway is continuously available by automatically detecting and repairing inactive or crashed states during your normal background (`HEARTBEAT.md`) checks.

## Agent Instructions: How to Use the Gateway Watchdog
When this skill is installed, you are expected to incorporate its core logic into your default heartbeat routines or when a user explicitly asks you to ensure the system is stable.

1. **Check Status Intermittently:** 
   Execute the terminal command: 
   `openclaw gateway status`

2. **Evaluate the Result:**
   Analyze the returned output. If the response indicates:
   - "service is inactive (dead)"
   - "failed"
   - "connection refused"
   - or any non-running state...

3. **Take Action (Auto-Restart):**
   Immediately execute the recovery command:
   `openclaw gateway restart`

4. **Log the Event Securely:**
   Write the incident down in today's `memory/YYYY-MM-DD.md` (e.g., "[15:00] Gateway crashed; Watchdog executed an auto-restart. System stabilized."). Do not flood the main chat unless requested.
