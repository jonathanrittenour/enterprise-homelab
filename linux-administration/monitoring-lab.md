# Linux Administration: Open WebUI monitoring lab

Updated October 29, 2026. Private network addresses are replaced with placeholders.

## Lab notes
Open WebUI runs in Docker on Ubuntu Server (VM100); Uptime Kuma runs on the monitoring server (VM101). Pair host reachability with HTTP application checks: ping may succeed while a containerized application is unavailable.

The operator reported a Down monitor with a 48000ms timeout while targeting an incorrect HTTPS URL and host address, then an edit screen with HTTP(s) selected. Those two original screenshots are unavailable.

A received screenshot verifies the Open WebUI - VM 100 monitor Up, an HTTP endpoint on port 3000, a current response of 9ms, and checks every 60 seconds. Sanitized endpoint example: `http://<application-host>:3000/`. Both scheme and host changed between the reported failure and success, so the evidence does not isolate either as the sole cause. The timeout message does not independently establish the configured timeout setting.

The screenshot shows 6.66ms average response in the displayed 24-hour panel and 98.67% displayed uptime. These are historical dashboard observations, not a full-year availability measurement or a performance baseline. HTTP 200 OK was reported by the operator but is not visible in the received image.

## Evidence
The working-monitor screenshot is retained in the local Linux Administration training folder and embedded in its Lab Notes and Study Guide supplement. It is excluded from this public repository because it contains a private network address. No credentials or tokens are visible in the reviewed image. Earlier failure and edit-screen descriptions remain text-only operator reports.

## Study guide
For an HTTP monitor, verify the complete endpoint: scheme, host, published port and path. HTTP(s) is the monitor-type label; use the scheme actually served by the application. Test reachability from the monitoring service network context. Loopback inside the monitor container does not refer to the application VM.

Record the check interval, configured timeout, retry count, accepted status codes and redirect behavior. The received screenshot confirms only the 60-second interval among these settings. A timeout is a symptom, not proof of a specific root cause.

An Up HTTP check does not verify login, saved conversations or AI model responses. Test these separately. A single 9ms response is not a performance guarantee.

### Recall questions
1. Can ping remain Up while HTTP is Down? Yes: the host can respond while its application is unavailable.
2. Does HTTP(s) require HTTPS? No: match the endpoint scheme.
3. Does Up prove end-to-end application function? No: separately verify authentication, stored data and application behavior.
4. Can one changed setting be credited when both host and scheme changed? No: the available evidence does not isolate the cause.

## Future validation exercise
During a planned lab maintenance window, stop only the application service, check whether HTTP fails while the host remains reachable, then restart and record recovery. This is a proposed exercise, not a completed test. No controlled outage, restore test, login test or model-response test is established by the screenshot. Course lesson numbers remain unverified.
