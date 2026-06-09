# Help Desk Ticket Template

## Purpose

This template is used to document a user issue, troubleshooting steps, and final resolution.

## Ticket Fields

Ticket ID:
Date:
User/Department:
Contact Method:
Device/Asset:
Priority:
Status:

## Issue Summary

Briefly describe the problem in one sentence

## Symptoms

What is the user experiencing?
When did it start?
Is it constant or intermittent?
Is it affecting one user, one device, or multiple users?

## Troubleshooting steps 

#### Initial Triage

- Is the issue affecting one user/device, multiple users, or an entire location?
- Is the issue local to the device, network related, or application-specific?
- When did it start?
- What changed recently?

### OSI Model-based steps

1) Physical 
- Check:
    - Cables
    - Wi-Fi signal,
    - Ports
    - Power
    - Hardware
    - Link Lights
    - Docking station
2) Data-Link
- Check:
    - MAC addresses
    - Wi-Fi / Ethernet connection
    - Network adapter status
    - Switching
    - VLANs
3) Network
- Check:
    - IP addresses
    - subnet mask
    - Default Gateway
    - Routing
    - Test gateway connectivity
4) Transport
- Check:
    - TCP/UDP
    - Ports
    - Connection success/failure
    - Test wether the needed service/port appears reachable
5) Session
- Check:
    - Login sessions
    - Session timeouts
    - VPN session
    - App session
    - Reconnect/re-authenticate id needed
6) Presentation
- Check:
    - Encryption
    - Formatting
    - Certificates
    - Encoding
    - Compability issues IF relevant
7) Application
- Check
    - Actual App/Service
        - browser
        - website
        - email client
        - teams/zoom
        - service status
        - updates
        - cache

## Resolution

What fixed the issue?

## Follow-Up

Is any follow-up needed?
Does the issue need escalation?
Was the user notified?

## Notes

Document clearly enough that another technician could understand what happened

## Example ticket

Ticket ID: HD-0002
Date: YYYY-MM-DD
User/Department: Example User / Accounting
Contact Method: Email
Device/Asset: Windows laptop
Priority: Medium
Status: Resolved

### Issue Summary

User can connect to the company VPN, but cannot access the internal payroll website.

### Symptoms 

User reports VPN shows “connected,” but the internal payroll website does not load.
The issue started this morning.
One user affected.

### Troubleshooting Steps

#### Initial Triage:
- Asked user if they can access public websites and try navigating to www.google.com 
    - user can access external websites

#### OSI Model-based steps
1) Physical:
- Confirmed laptop was powered on, Wi-Fi was enabled, and the signal was stable

2) Data-Link:
- confirmed laptop was connected to the correct SSID and was not repeatedly disconnecting/reconnecting

3) Network:
- Checked IP config to confirm the device had a valid IP address, subnet mask, DNS Server, and default gateway
- Confirmed VPN was connected and assigned to a VPN IP address

4) Transport
- Tested wether the internal website address was reachable over the expected service port, checked HTTPS access on pprt 443 since this is a website

5) Session
- Checked wether the user's VPN session was active and not expired.
- Disconnected and reconnected the VPN to create a fresh session.
- Asked user to sign out and sign back into the internal website

6) Presentation
- Checked for certificate / encryption-related browser warnings.
- User reported a certificate warning when opening the internal payroll website.
- Verified the laptop date and time were correct - incorrect time can cause certificate validation errors

7) Application
- Tested internal payroll website in another browser.
- Cleared browser cache for the internal site
- Checked wether other users could access the payroll website.

### Resolution

- The issue was caused by an expired browser session and a certificate warning triggered after the VPN session became stale.
- Reconnected the VPN confirmed the laptop date/time were correct
- had user sign back into the internal payroll website
- verified the site loaded successfully 

### Follow-UP

- User was advised to reconnect VPN and sign back in if the issue returns
- If multiple users report the same certificate warning, escelate to systems/network team to check the internal site certificate