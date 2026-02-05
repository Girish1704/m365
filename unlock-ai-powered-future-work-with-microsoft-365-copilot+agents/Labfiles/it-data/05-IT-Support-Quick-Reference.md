# IT Support Quick Reference Card

**Document Version:** 1.0  
**Last Updated:** January 2026  
**Department:** IT Help Desk  
**Classification:** Internal Use Only

---

## 🚨 Emergency Contacts

| Issue | Contact | Availability |
|-------|---------|--------------|
| **IT Help Desk** | ext. 4357 / helpdesk@contoso.com | Mon-Fri 7AM-7PM |
| **After-Hours Emergency** | 1-800-555-HELP | 24/7 |
| **Security Incident** | ext. 4500 / security@contoso.com | 24/7 |
| **Network Emergency** | ext. 4911 | 24/7 |

---

## 🔐 Password & Account Issues

### Forgot Password?
**Self-Service Reset:** https://passwordreset.microsoftonline.com

1. Enter your email address
2. Complete verification (text, call, or authenticator)
3. Create new password (14+ chars, upper, lower, number, special)
4. Sign in with new password

### Account Locked?
- Wait 30 minutes for auto-unlock, OR
- Reset password using link above, OR
- Call IT Help Desk

### Password Requirements
| Requirement | Value |
|-------------|-------|
| Minimum length | 14 characters |
| Must include | Uppercase, lowercase, number, special character |
| Cannot reuse | Last 12 passwords |
| Expires | Every 90 days |

---

## 🌐 VPN Connection

### Quick Connect
1. Open Cisco AnyConnect
2. Server: `vpn.contoso.com`
3. Enter username and password
4. Complete MFA verification
5. Connected!

### VPN Not Working?
| Try This | How |
|----------|-----|
| Check internet | Can you browse google.com? |
| Restart client | Close AnyConnect, reopen |
| Try backup server | vpn-us2.contoso.com |
| Restart service | services.msc → Restart "Cisco AnyConnect VPN Agent" |
| Different network | Try mobile hotspot |

---

## 💻 Slow Computer?

### Quick Fixes (Try in Order)
1. **Restart** (if running > 3 days)
2. **Close unused apps** (check Task Manager)
3. **Clear temp files** (Disk Cleanup)
4. **Check disk space** (need 15%+ free)
5. **Disable startup apps** (Task Manager → Startup)

### Performance Check Commands
```
# Open Task Manager
Ctrl + Shift + Esc

# Check disk space
Win + E → Right-click C: → Properties

# Run Disk Cleanup
Search "Disk Cleanup" → Select C: → Clean
```

---

## 🖨️ Printer Issues

### Printer Offline?
1. Check printer is powered on
2. Restart Print Spooler:
   - `services.msc` → "Print Spooler" → Restart
3. Open print queue → Uncheck "Use Printer Offline"
4. Remove and re-add printer

### Paper Jam
1. Turn off printer
2. Open all doors
3. Remove paper (pull in paper direction)
4. Check for torn pieces
5. Close doors and power on

### Adding Office Printer
Server: `\\printserver.contoso.local`

Example: `\\printserver.contoso.local\HQ-2F-MFP01`

---

## 📱 MFA & Authenticator

### MFA Not Working?
| Issue | Solution |
|-------|----------|
| No notification | Open app and refresh, check internet |
| Code invalid | Check phone time is automatic |
| Phone lost | Call Help Desk for temp access pass |

### Setting Up New Phone
1. https://aka.ms/mfasetup
2. Add authentication method
3. Scan QR code with new phone
4. Complete verification test

---

## 📧 Outlook Problems

### Outlook Slow?
1. Compact mailbox: File → Account Settings → Compact Now
2. Archive old emails
3. Disable add-ins: File → Options → Add-ins
4. Clear cache: Delete OST file and restart

### Can't Connect?
1. Check internet connection
2. Verify password is current
3. Remove and re-add account
4. Run Office repair

---

## 🎥 Teams Issues

### Clear Teams Cache
1. Close Teams completely
2. Navigate to: `%appdata%\Microsoft\Teams`
3. Delete: Cache, blob_storage, databases, GPUcache, tmp
4. Restart Teams

### Audio/Video Not Working
1. Settings → Privacy → Enable camera/microphone
2. Check device selected in Teams settings
3. Update Teams and device drivers
4. Restart computer

---

## 🌐 WiFi & Network

### Can't Connect to WiFi?
1. Click WiFi icon → Forget network → Reconnect
2. Check correct password
3. Restart WiFi adapter:
   - Settings → Network → WiFi → Turn off/on
4. Restart computer

### No Internet?
```
# Run these in Command Prompt:
ipconfig /release
ipconfig /renew
ipconfig /flushdns
```

---

## 📋 Common Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| Task Manager | Ctrl + Shift + Esc |
| Lock computer | Win + L |
| Run dialog | Win + R |
| Search | Win + S |
| Snipping tool | Win + Shift + S |
| Switch windows | Alt + Tab |
| Close window | Alt + F4 |
| Display settings | Win + P |

---

## 🔧 Useful System Commands

| Command | What It Does |
|---------|--------------|
| `services.msc` | Opens Windows Services |
| `devmgmt.msc` | Opens Device Manager |
| `control` | Opens Control Panel |
| `msconfig` | System Configuration |
| `cleanmgr` | Disk Cleanup |
| `ncpa.cpl` | Network Connections |

---

## 📞 When to Call Help Desk

**CALL if:**
- Self-service steps didn't work
- Hardware is damaged
- You see security warnings
- Repeated blue screens
- Suspected security breach
- Need software installation

**INCLUDE:**
- Your location
- Device model
- Error message (exact wording)
- What you were doing
- What you've tried

---

## 🌐 Self-Service Portals

| Portal | URL | Use For |
|--------|-----|---------|
| Password Reset | passwordreset.microsoftonline.com | Reset forgotten password |
| MFA Setup | aka.ms/mfasetup | Add/change auth methods |
| My Account | myaccount.microsoft.com | Security info, devices |
| IT Service Portal | itportal.contoso.com | Submit tickets, requests |
| Software Center | Start menu → Software Center | Install approved software |

---

## ⏰ Support Hours

| Service | Hours |
|---------|-------|
| IT Help Desk | Mon-Fri 7AM-7PM EST |
| After-Hours Emergency | 24/7 (critical issues only) |
| Hardware Support | Mon-Fri 8AM-5PM EST |
| On-Site Support | By appointment |

**Response Times:**
- Critical (system down): 15 minutes
- High (major impact): 1 hour
- Medium (work impacted): 4 hours
- Low (minor issue): 24 hours

---

*Keep this card handy! For full documentation, visit: https://itdocs.contoso.com*

*IT Help Desk: ext. 4357 | helpdesk@contoso.com*
