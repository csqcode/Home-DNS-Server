# Home-DNS-Lab
How I self-host my own DNS and add privacy services. Hosted via Technitium on a Ubuntu server. The server supports ad blocking, DNS over HTTPS, and remote VPN access.

## Hardware
- Main Desktop – i3, 4gb ram, 1tb hdd
- Extra Desktop – Celeron, 4gb ram
- Network Switch

## How it Works
With Technitium, my Ubuntu server acts as a fully fledged DNS resolver. All DNS queries on my WiFi are processed through Techntium. Any ads, malware, or other unfavorable sites are blocked. Queries are then sent to Cloudflare for DNS over HTTPS encryption. Throughout all of this, TailScale increases privacy via end-to-end encryption and peer-to-peer connections.

## Status

 | Name | Status |
   |------|-----|
   | Technitium DNS | Core DNS server running |
   | DHCP | Handled by Eero |
   | Blocklists | Lists loaded and updating |
   | DNS Over HTTPS | Cloudflare upstream configured |
   | Eero Integration | Custom DNS set, caching disabled |
   | DNSSEC | Active |
   | TailScale | VPN node active |
   | Technitium Backup Instance | Secondary DNS server running |
   | Auto-transfer | Configured |
   | Splunk/SIEM | Not started |

 ## Notes
 - This guide specifically revolves around trying to integrate Technitium with my Eero router. Eero is a very aggressive router that will automatically redirect DNS unless specific measures are taken. Anyone without an Eero can ignore the steps and have a much easier time setting up Technitium.
 - backup.md does not detail the process of zone transfer with custom zones. 
