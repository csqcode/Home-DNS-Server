# Home-DNS-Lab
How I self-host my own DNS and add privacy services. Hosted via Technitium on a Ubuntu server. The server supports ad blocking, DNS over HTTPS, and remote VPN access.

## Hardware
- Main Desktop – i3, 4gb ram, 1tb hdd
- Network Switch

## How it Works
With Technitium, my Ubuntu server acts as a fully fledged DNS resolver. All DNS queries on my WiFi are processed through Techntium. Any ads, malware, or other unfavorable sites are blocked. Queries are then sent to Cloudflare for DNS over HTTPS encryption. Throughout all of this, TailScale increases privacy via end-to-end encryption and peer-to-peer connections.

## Status
