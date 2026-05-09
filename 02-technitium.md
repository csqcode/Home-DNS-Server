## Goal
Install technitium and configure blocklists

## Prerequisites
- Have ubuntu server working
- Have ethernet connection

## Steps
1. Install Technitium
   - ```curl -sSL https://download.technitium.com/dns/install.sh | sudo bash```
2. Access webpage and change credentials
3. Add blocklists
   
   | Name | URL | Category |
   |------|-----|----------|
   | OISD Big | https://big.oisd.nl | Ads, Tracking, Malware, Phishing|
   | HaGeZi Multi Pro | https://raw.githubusercontent.com/hagezi/dns-blocklists/main/hosts/pro.txt | Ads, Tracking, Telemetry, Phishing, Malware, Scam, Cryptojacking |
   | StevenBlack Unified | https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts | Ads, Malware |
   | HaGeZi NRD Short | https://raw.githubusercontent.com/hagezi/dns-blocklists/main/hosts/newdomains-time-short.txt | Newly Registered Domains |

  Total Domains Blocked (No Duplicates) ~ 800,000
  
  Last Verified: May 2026

  ## Verification
  1. https://www.dnsleaktest.com/
  2. Check ad blocking accross devices
     - https://canyoublockit.com/
    
  ## Troubleshooting
  1. Not blocking major ads
     - Cause: Lists out of date
     - Solution: Update lists
  2. Invalid List
     - Cause: Wrong list URL
     - Solution: Grab proper list URL
