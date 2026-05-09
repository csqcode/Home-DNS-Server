## Goal
Change settings on eero router to ensure it doesn't intercept DNS queries. 

## Prerequisites
- Eero router
- Technitium installed and prepared to handle traffic

## Steps
1. Disable all Security+ features
2. Disable local caching
3. Set Custom DNS to Technitium IP
4. Set Backup DNS to Cloudflare (1.1.1.2)

## Verification
- dnsleaktest.com

## Troubleshooting
1. Custom DNS is greyed out
   - Cause: All Security+ features must be disabled
   - Solution: Disable all security+ features
2. Some devices do not receive adblocking benefits
   - Cause 1: Some devices have a hardcoded DNS
   - Solution 1: Implement pfsense to redirect queries to Technitium
   - Cause 2: Device has a VPN enabled
   - Solution 2: Disable VPN
