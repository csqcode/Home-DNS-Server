## Goal
To create a backup instance of technitium that is constantly running. Prevents internet failure if main device goes down.

## Prerequisites
- Technitium installed and running
- Secondary computer

## Steps
1. Follow earlier steps in setup.md and technitium.md for basic installation
2. In Technitium's Webpage settings, scroll down and click on the "Backup Settings" button
   - Check every box (logs are optional)
   - Press "Backup"
3. On the Technitium Webpage of your second device, go to settings and click the "Restore Settings button
4. Upload the zip file from your main device
5. Restart Technitium on your secondary device
   - ```sudo systemctl restart dns.service```
6. Set Eero's secondary DNS to secondary device IP

## Verification
- Technitium Webpage of secondary device should see queries
- Queries are still processed if main device fails

## Troubleshooting
1. No internet access on secondary device
    - Cause: DNS not configured
    - Solution: Temporarily set to Cloudflare
       - ```sudo nano /etc/resolv.conf```
       - Replace the nameserver line with: ```nameserver: 8.8.8.8```
