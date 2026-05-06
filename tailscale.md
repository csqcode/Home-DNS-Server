## Goal
To integrate Technitium and various mobile devices with tailscale to allow for DNS benefits when remote.

## Prerequisites
- Technitium installed and running
- Devices that can use a VPN

## Steps
1. Create TailScale account
2. Add DNS to tailnet
3. Disable accept-dns on Technitium
   - ```sudo tailscale set --accept-dns=false```
5. Enable MagicDNS and Override DNS Servers
6. Add new nameserver (In DNS Settings) and set it to TailScale IP of DNS Server
7. Add new users and devices to tailnet
   - For phones and laptops --> Enable TailScale as VPN in settings

## Verification
- Test ad blocker on public wifi or ceullular data
    - https://canyoublockit.com/

## Troubleshooting
1. Can't override DNS Servers in TailScale admin page
   - Cause: TailScale doesn't have another DNS Server to use
   - Solution: Press "Add Nameserver" below Global Nameserver, configure to Technitium IP, and delete the old nameserver
2. Remote devices still have ads
   - Cause: Interference from secondary VPN or DNS over HTTPS
   - Solution: Remove any other VPN. Turn off DNS over HTTPS until set up in Technitium
