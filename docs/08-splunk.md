## Goal
Add Splunk to index DNS logs. Allows for a more comprehensive log analysis compared to what Technitium alone provides.

## Prerequisites
- Technitium installed and running
- Extra hardware capable of hosting Splunk

## Steps
1. In Technitium's settings, ensure that "Log All Queries" is turned on
2. On a secondary machine, create a Splunk account and install software
3. Configure Splunk (Ensure its listening on port 9997)
4. On Technitium, install the "Log Exporter" app
   - Edit the following in the config:
    ```
     "syslog": {
		"address": "splunk ip",
		"port": 514,
		"protocol": "UDP",
		"enabled": true
     }
5. On Splunk webpage, add a new data input for Technitium
   - Settings --> Data Inputs --> UDP --> port=514, sourcetype=syslog, enabled
   - Settings --> Fowarding & Receiving --> Configure Receiving --> Listen on port 9997
7. Check Splunk webpage to verify DNS logs are being received
8. Configure dashboards to visualize data
9. Add alerts if necessary

## Verification
- Data will naturally enter Splunk via the Universal Forwarder

## Troubleshooting
1. Splunk not seeing logs
   - Cause: Incorrect configuration
   - Solution: Review Setup. Ensure that everything is properly installed. Make sure the ports were created, configs set up properly, and that Technitium points to the correct machine.

## My Setup
I run Splunk on a Proxmox VM and forward my Technitium logs there. I then take this data and select specific elements to visualize on a dashboard. My categories are: Overview, Security & Threats, Clients & Traffic. It ingests data from a 24-hour period.

   | Name | Role | Data |
   |------|-----|----------|
   | Overview | Gives a general idea of how Technitium is operating | Total Queries, Block Rate, Queries Over Time, Blocked Count, Cache Hit Rate, Top Blocked Domains, Top Queried Domains |
   | Security & Threats | Represents data regarding malicious domains | Blocked Queries by Client, NxDomain by Client, NxDomain Queries Over Time, Suspicious TLD Queries, Suspicious Subdomains |
   | Clients & Traffic | Gives a breakdown of general traffic as well as Remote vs Lan traffic | Queries by Client, Queries by Type, Tailscale Queries, LAN Queries |
