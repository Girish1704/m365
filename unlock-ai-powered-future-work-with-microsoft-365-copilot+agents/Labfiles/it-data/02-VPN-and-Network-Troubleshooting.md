# VPN and Network Troubleshooting Guide

**Document Version:** 3.0  
**Last Updated:** January 2026  
**Department:** IT Infrastructure & Network Services  
**Classification:** Internal Use Only

---

## Table of Contents

1. [VPN Overview](#vpn-overview)
2. [VPN Installation and Setup](#vpn-installation-and-setup)
3. [Connecting to VPN](#connecting-to-vpn)
4. [VPN Troubleshooting](#vpn-troubleshooting)
5. [Network Connectivity Issues](#network-connectivity-issues)
6. [WiFi Troubleshooting](#wifi-troubleshooting)
7. [Remote Desktop and RDP](#remote-desktop-and-rdp)

---

## VPN Overview

### Supported VPN Clients

| Client | Platform | Download Link | Use Case |
|--------|----------|---------------|----------|
| Cisco AnyConnect | Windows, Mac, iOS, Android | Software Center / Self-Service | Primary VPN client |
| GlobalProtect | Windows, Mac | Software Center | Backup VPN option |
| Microsoft Always On VPN | Windows 10/11 | Auto-configured | Domain-joined devices |

### VPN Server Addresses

| Region | Primary Server | Backup Server | Port |
|--------|----------------|---------------|------|
| Americas | vpn-us.contoso.com | vpn-us2.contoso.com | 443 |
| Europe | vpn-eu.contoso.com | vpn-eu2.contoso.com | 443 |
| Asia Pacific | vpn-apac.contoso.com | vpn-apac2.contoso.com | 443 |
| Global (Auto-Select) | vpn.contoso.com | - | 443 |

### VPN Requirements

**Minimum System Requirements:**
- Windows 10 version 1909 or later / macOS 11.0 or later
- 4 GB RAM minimum
- 500 MB free disk space
- Active internet connection (minimum 5 Mbps)
- Valid corporate credentials
- Enrolled in Multi-Factor Authentication (MFA)

**Network Requirements:**
- Outbound port 443 (HTTPS) must be open
- Outbound port 500 and 4500 (IPSec) for backup protocols
- No restrictive firewalls blocking VPN traffic
- DNS resolution for vpn.contoso.com

---

## VPN Installation and Setup

### Windows Installation

1. Open **Software Center** from the Start menu
2. Search for "Cisco AnyConnect"
3. Click **Install** and wait for completion
4. Restart your computer when prompted
5. Find "Cisco AnyConnect Secure Mobility Client" in Start menu

### Mac Installation

1. Open **Self Service** application
2. Search for "Cisco AnyConnect"
3. Click **Install**
4. Enter your Mac administrator password when prompted
5. Allow the System Extension in Security & Privacy settings
6. Restart your Mac

### Mobile Device Installation

**iOS:**
1. Open App Store
2. Search "Cisco AnyConnect"
3. Download and install
4. Open app and accept license agreement
5. Allow VPN configuration when prompted

**Android:**
1. Open Google Play Store
2. Search "Cisco AnyConnect"
3. Install and open
4. Grant necessary permissions
5. Allow VPN configuration

### First-Time Configuration

1. Open Cisco AnyConnect
2. In the connection field, enter: `vpn.contoso.com`
3. Click **Connect**
4. Enter your corporate username (without @contoso.com)
5. Enter your password
6. Complete MFA verification
7. Accept the acceptable use policy
8. Connection established - verify with "Connected" status

---

## Connecting to VPN

### Standard Connection Process

1. Ensure you have an active internet connection
2. Open Cisco AnyConnect from system tray or Start menu
3. Select the appropriate server:
   - Use `vpn.contoso.com` for automatic region selection
   - Use regional server if experiencing issues
4. Click **Connect**
5. Enter credentials:
   - Username: Your employee ID or email prefix
   - Password: Your current network password
6. Complete MFA:
   - Approve push notification, OR
   - Enter 6-digit code from Authenticator
7. Wait for connection (typically 5-15 seconds)
8. Verify "Connected" status in system tray

### Split Tunnel vs Full Tunnel

| Mode | Description | When to Use |
|------|-------------|-------------|
| Split Tunnel | Only corporate traffic through VPN | General remote work |
| Full Tunnel | All traffic through VPN | Accessing sensitive systems |

**To switch modes:**
1. Disconnect from VPN
2. In AnyConnect, click the gear icon
3. Select **Preferences**
4. Toggle "Route all traffic through VPN"
5. Reconnect

### Scheduled Auto-Connect

For Windows devices with Always On VPN:
1. Connection is automatic when not on corporate network
2. No manual action required
3. Check VPN status in system tray
4. If not connected, verify network connectivity first

---

## VPN Troubleshooting

### Connection Failed Errors

#### "Connection attempt has failed"

**Causes:**
- No internet connection
- Firewall blocking VPN
- VPN server unreachable
- Incorrect server address

**Solutions:**
1. Verify internet connection (browse to google.com)
2. Try a different network (mobile hotspot)
3. Disable local firewall temporarily to test
4. Try backup VPN server
5. Restart AnyConnect service:
   - Open Services (services.msc)
   - Find "Cisco AnyConnect VPN Agent"
   - Right-click → Restart

#### "Authentication failed"

**Causes:**
- Incorrect password
- Account locked
- MFA issue
- Expired password

**Solutions:**
1. Verify password is current (try web mail login)
2. Check if account is locked (wait 30 minutes or reset password)
3. Ensure MFA is set up correctly
4. Reset password if recently expired

#### "Certificate validation failure"

**Causes:**
- Outdated VPN client
- System date/time incorrect
- Missing root certificates

**Solutions:**
1. Check system date and time are correct
2. Update AnyConnect to latest version
3. Run Windows Update
4. Contact IT to push certificate update

### VPN Keeps Disconnecting

**Every few minutes:**
1. Check internet stability (run continuous ping)
2. Move closer to WiFi router
3. Try wired ethernet connection
4. Disable power saving on network adapter:
   - Device Manager → Network Adapters
   - Right-click adapter → Properties → Power Management
   - Uncheck "Allow computer to turn off this device"

**After idle period:**
1. Adjust AnyConnect timeout settings
2. Enable "Reconnect after disconnect" in preferences
3. Check Windows power settings (prevent sleep)
4. Disable "Allow hybrid sleep"

**During video calls:**
1. Close bandwidth-heavy applications
2. Reduce video quality in meeting app
3. Switch to ethernet connection
4. Use split tunnel mode

### VPN Performance Issues

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Slow file transfers | High latency to server | Use regional VPN server |
| Lag in applications | Bandwidth congestion | Close unnecessary apps |
| Video call choppy | Insufficient bandwidth | Use split tunnel mode |
| Connection timeouts | Server overload | Try backup server |
| DNS resolution slow | VPN DNS issues | Flush DNS cache |

**To flush DNS cache:**
```
ipconfig /flushdns
ipconfig /registerdns
```

### VPN Client Issues

**AnyConnect won't open:**
1. Check if already running in system tray
2. End task in Task Manager and reopen
3. Restart "Cisco AnyConnect VPN Agent" service
4. Repair installation from Control Panel
5. Uninstall and reinstall from Software Center

**AnyConnect crashes:**
1. Update to latest version
2. Disable conflicting software (other VPNs, security tools)
3. Run as Administrator
4. Check Windows Event Viewer for errors
5. Contact IT with crash logs

---

## Network Connectivity Issues

### No Internet Connection

**Basic Diagnostics:**
1. Check physical connections (ethernet cable, WiFi enabled)
2. Look for network icon issues in system tray
3. Try accessing different websites
4. Test on another device on same network

**Windows Network Reset:**
1. Open Settings → Network & Internet
2. Click "Network reset"
3. Click "Reset now"
4. Restart computer
5. Reconnect to network

**Command Line Diagnostics:**
```
ipconfig /all          (view IP configuration)
ping 8.8.8.8           (test internet connectivity)
ping contoso.com       (test DNS resolution)
tracert contoso.com    (trace route to destination)
nslookup contoso.com   (test DNS lookup)
```

### IP Address Issues

**"IP address conflict detected":**
1. Open Command Prompt as Administrator
2. Run: `ipconfig /release`
3. Run: `ipconfig /renew`
4. If persists, restart router/modem

**"No valid IP configuration":**
1. Disable and re-enable network adapter
2. Reset TCP/IP stack:
   ```
   netsh winsock reset
   netsh int ip reset
   ```
3. Restart computer

### DNS Resolution Problems

**Can ping IP but not domain names:**
1. Check DNS server settings
2. Flush DNS cache: `ipconfig /flushdns`
3. Try alternative DNS:
   - Open Network adapter settings
   - IPv4 Properties
   - Use: 8.8.8.8 and 8.8.4.4 (Google DNS)
4. Reset DNS: `netsh int ip reset`

---

## WiFi Troubleshooting

### Cannot Connect to WiFi

**Corporate WiFi (ContosoSecure):**
1. Forget the network and reconnect
2. Verify using correct credentials
3. Check certificate is installed
4. Ensure device is domain-joined or enrolled

**Guest WiFi (ContosoGuest):**
1. Connect and open browser
2. Accept terms on captive portal
3. Use personal email to register
4. Valid for 24 hours

### WiFi Keeps Dropping

**Solutions:**
1. Move closer to access point
2. Check for interference (microwaves, Bluetooth)
3. Forget and reconnect to network
4. Update WiFi adapter driver
5. Change WiFi channel on home router
6. Disable WiFi power saving:
   - Device Manager → Network Adapters
   - WiFi adapter → Properties → Advanced
   - Set "Power Saving Mode" to "Off"

### Slow WiFi Performance

| Issue | Solution |
|-------|----------|
| Too far from router | Move closer or use WiFi extender |
| Too many devices | Disconnect unused devices |
| Old router | Upgrade to WiFi 6 router |
| Interference | Change channel (1, 6, or 11 for 2.4GHz) |
| Background downloads | Pause updates and cloud sync |

### Home WiFi Optimization

**For best remote work experience:**
1. Use 5GHz band when possible (faster, less interference)
2. Position router centrally, elevated
3. Use ethernet for video calls if possible
4. Schedule large downloads outside work hours
5. Consider mesh WiFi for large homes
6. Keep router firmware updated

---

## Remote Desktop and RDP

### Connecting to Remote Desktop

**From VPN:**
1. Connect to VPN first
2. Open Remote Desktop Connection (mstsc)
3. Enter computer name: `yourcomputer.contoso.local`
4. Click Connect
5. Enter credentials when prompted

**Via Remote Desktop Gateway:**
1. Open Remote Desktop Connection
2. Click "Show Options" → "Advanced"
3. Under "Connect from anywhere," click Settings
4. Enter gateway: `rdg.contoso.com`
5. Check "Use my RD Gateway credentials"
6. Connect using computer name

### RDP Troubleshooting

**"Remote Desktop can't connect":**
1. Verify VPN is connected
2. Ping the target computer
3. Verify computer is powered on
4. Check Remote Desktop is enabled on target
5. Verify your account has RDP permission

**"Your credentials did not work":**
1. Use format: CONTOSO\username
2. Verify password is current
3. Check account is not locked
4. Confirm MFA if prompted

**Black screen after connect:**
1. Wait 30 seconds (may be loading)
2. Press Ctrl+Alt+End
3. Sign out and reconnect
4. Restart remote computer (if possible)

### RDP Performance Tips

1. Reduce color depth to 16-bit
2. Disable visual effects in RDP settings
3. Use "Optimize for slow connection"
4. Close unnecessary applications on remote PC
5. Ensure stable VPN connection

---

## Contact Information

| Service | Contact | Hours |
|---------|---------|-------|
| IT Help Desk | helpdesk@contoso.com / ext. 4357 | Mon-Fri 7AM-7PM |
| Network Operations | netops@contoso.com | 24/7 monitoring |
| VPN Support Portal | https://vpnsupport.contoso.com | 24/7 |
| Emergency Network Issues | ext. 4911 | 24/7 |

### Escalation Path

1. **Level 1:** IT Help Desk - Basic troubleshooting
2. **Level 2:** Network Support - Advanced diagnostics
3. **Level 3:** Network Engineering - Infrastructure issues

---

*This document is maintained by IT Infrastructure & Network Services. For updates, contact netops@contoso.com.*
