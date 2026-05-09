## Goal
Add new security features to Technitium and TailScale to ensure client privacy

## Prerequisites
- Technitium installed and running
- TailScale installed and running

## Steps
1. In Technitium's "Optional Protocols" tab, enable DNS over HTTPS
2. In the "Proxy and Forwarders" tab, change "Forwarder Protocol" to DNS over HTTPS
3. Copy and paste forwarder IPs into the "Forwarders" box
4. Enable DNS over HTTPS in browser settings
5. Set custom DNS to the Tailscale IP of Technitium

   | Name | URL | Category |
   |------|-----|----------|
   | Cloudflare | https://cloudflare-dns.com/dns-query (1.1.1.2) | Malware, Phishing |
   | Cloudflare | https://cloudflare-dns.com/dns-query (1.0.0.2) | Malware, Phishing, Backup Provider |
   | Quad9 | https://9.9.9.9/dns-query | Malware, Phishing, Backup Provider |

## Verification
- Read logs to see data being sent to and from forwarder

## Troubleshooting
1. Internet is slow or not working
   - Cause: Forwarder may be down or slow
   - Solution: Read logs to ensure it is forwarder's fault, change to another forwarder

   
