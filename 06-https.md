## Goal
Enable https on Technitium webpage to allow for remote access without compromising security

## Prerequisites
- Technitium installed and running
- TailScale installed and running

## Steps
1. Under the "Web Service" tab in Technitium, enable HTTPS
2. In TailScale, enable HTTPS Certificates under the DNS tab
3. Get TailScale cert and key on Technitium machine
   - ```sudo tailscale cert```
   - This will give you the HTTPS link to your webpage
4. Convert cert and key into PFX file
   - Temporarily change key permissions: ```chmod 644 ~/"Your DNS Key"```
   - Convert: ```openssl pkcs12 -export -out ~/your-server-name.your-tailnet.ts.net.pfx \ -inkey ~/"Your DNS Key" \ -in ~/"Your DNS Cert" \ -passout pass:```
   - Change back key permissions: ```chmod 600 ~/"Your DNS Cert"```
5. In the TLS Certificate File Path box, enter the path to your pfx file
6. Create a crontab file to auto-renew certs (They expire every 90 days)
   - ```sudo crontab -e```
   - Paste: ```0 0 1 * * tailscale cert "Your dns webpage link" && openssl pkcs12 -export -out /home/"you"/"your pfx file" -inkey /home/"you"/"Your key" -in /home/"you"/"Your cert" -passout pass: && systemctl restart dns```

## Verification
- Access the Technitium webpage from the new HTTPS link
- To verify crontab - ```sudo crontab -l```

## Troubleshooting
1. New website link isn't working
   - Cause 1: Steps not followed fully
   - Solution 1: If these steps are not exactly followed, the URL will not work
   - Cause 2: URL not typed correctly
   - Solution 2: Ensure URL is typed correctly and that you are using the new port associated with HTTPS
