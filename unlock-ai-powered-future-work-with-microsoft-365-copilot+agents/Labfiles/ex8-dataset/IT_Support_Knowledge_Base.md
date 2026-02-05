# IT Support Knowledge Base
## Frequently Asked Questions and Solutions

---

## PASSWORD AND ACCOUNT ISSUES

### How do I reset my password?
1. Go to the self-service password reset portal: https://passwordreset.microsoftonline.com
2. Enter your work email address
3. Complete the verification using your registered method (phone, email, or authenticator app)
4. Create a new password following our password policy
5. Sign in with your new password

### What are the password requirements?
- Minimum 12 characters
- At least one uppercase letter (A-Z)
- At least one lowercase letter (a-z)
- At least one number (0-9)
- At least one special character (!@#$%^&*)
- Cannot reuse last 10 passwords
- Password expires every 90 days

### My account is locked. What should I do?
Account lockout occurs after 5 failed login attempts. Your options:
1. **Wait 30 minutes** - The account will automatically unlock
2. **Self-service unlock** - Use the password reset portal
3. **Contact IT** - Call extension 4357 for immediate assistance

### I changed my password but my phone/tablet can't sync email
After changing your password, you must update it on all your devices:
1. Open the Mail or Outlook app on your device
2. Go to Account Settings
3. Enter your new password when prompted
4. Wait for the sync to complete

---

## VPN AND CONNECTIVITY ISSUES

### How do I connect to VPN?
1. Open the VPN client application on your computer
2. Enter the server address: vpn.contoso.com
3. Enter your username (same as email without @contoso.com)
4. Enter your password
5. Complete MFA verification if prompted
6. Click Connect

### VPN won't connect - troubleshooting steps
Try these steps in order:
1. **Check internet connection** - Ensure you can browse websites
2. **Restart VPN client** - Close completely and reopen
3. **Verify credentials** - Ensure username/password are correct
4. **Check for updates** - Update the VPN client if available
5. **Restart computer** - A reboot often resolves connection issues
6. **Try backup gateway** - Use vpn2.contoso.com as alternate server

### VPN keeps disconnecting
Common causes and solutions:
1. **Unstable internet** - Move closer to router, use ethernet cable
2. **Sleep mode** - Disable sleep mode when connected to VPN
3. **Firewall blocking** - Temporarily disable firewall to test
4. **VPN timeout** - Reconnect if idle for more than 30 minutes

### Do I need VPN to access email?
- **No VPN needed** - Office 365 apps (Outlook, Teams, OneDrive) work without VPN
- **VPN required** - Internal file shares, internal websites, legacy applications

---

## LAPTOP PERFORMANCE ISSUES

### My laptop is running slow
General troubleshooting steps:
1. **Restart your computer** - This clears temporary files and memory
2. **Close unnecessary programs** - Check Task Manager (Ctrl+Shift+Esc)
3. **Check disk space** - Ensure at least 10GB free on C: drive
4. **Run Disk Cleanup** - Search for "Disk Cleanup" in Start menu
5. **Check for updates** - Install pending Windows updates
6. **Scan for malware** - Run Windows Defender full scan

### How do I check what's using my computer's resources?
1. Press Ctrl+Shift+Esc to open Task Manager
2. Click "More details" if in simple view
3. Look at CPU, Memory, and Disk columns
4. Right-click high-usage items and select "End task" if not needed

### My laptop is overheating
To prevent damage and improve performance:
1. Ensure vents are not blocked
2. Use laptop on hard, flat surface (not bed or carpet)
3. Clean vents with compressed air
4. Close resource-intensive applications
5. Consider a laptop cooling pad
6. If problem persists, contact IT for hardware inspection

### C: drive is red/low on space
Critical! Take action immediately:
1. Run Disk Cleanup (search in Start menu)
2. Empty Recycle Bin
3. Move files to OneDrive or network drive
4. Uninstall unused applications
5. Clear browser cache and downloads folder

---

## PRINTER ISSUES

### How do I add a network printer?
1. Open Settings > Devices > Printers & Scanners
2. Click "Add a printer or scanner"
3. Wait for the printer to appear in the list
4. Select the printer and click "Add device"
5. If not found, click "The printer I want isn't listed"
6. Enter printer path: \\printserver\printer-name

### Printer shows as offline
To bring printer back online:
1. Open Settings > Devices > Printers & Scanners
2. Click on your printer
3. Click "Open queue"
4. Click "Printer" menu > "Use Printer Online"
5. If still offline, restart the Print Spooler service

### Print job is stuck in queue
To clear stuck print jobs:
1. Open Services (search in Start menu)
2. Find "Print Spooler" service
3. Right-click and select "Stop"
4. Navigate to C:\Windows\System32\spool\PRINTERS
5. Delete all files in this folder
6. Go back to Services and start "Print Spooler"
7. Try printing again

### Printer is printing blank pages
Check these items:
1. Ensure toner/ink cartridges are installed and have ink
2. Remove protective tape from new cartridges
3. Run printer self-test/cleaning cycle
4. Check if correct paper size is loaded
5. Reinstall printer drivers

---

## GENERAL IT SUPPORT

### What can IT Support help with?
Our IT Help Desk can assist with:
- Password resets and account issues
- VPN and network connectivity
- Laptop and desktop problems
- Printer issues
- Software installation requests
- Email and Office 365 issues
- Security concerns and phishing reports

### How do I contact IT Support?
- **Phone:** Extension 4357 (HELP)
- **Email:** itsupport@contoso.com
- **Portal:** helpdesk.contoso.com
- **Teams:** IT Help Desk channel
- **Hours:** Monday-Friday, 7 AM - 7 PM
- **After hours:** Emergency line for critical issues only

### I accidentally deleted an important file
Don't panic! Try these recovery options:
1. **Check Recycle Bin** - Files stay there for 30 days
2. **OneDrive** - Check version history (right-click > Version history)
3. **SharePoint** - Check the site's Recycle Bin
4. **Contact IT** - We may be able to restore from backup (up to 30 days)

### I think I received a phishing email
DO NOT click any links or attachments! Instead:
1. Forward the email to security@contoso.com
2. Delete the email from your inbox
3. If you clicked anything, contact IT immediately
4. Change your password as a precaution

### I spilled liquid on my laptop
Act immediately:
1. Power off the laptop (hold power button 5 seconds)
2. Unplug the power cord
3. Turn laptop upside down to drain liquid
4. DO NOT turn it back on
5. Contact IT Support immediately
6. Bring laptop to IT for assessment

---

## CONTACT INFORMATION

**IT Help Desk**
- Phone: (555) 123-4357
- Email: itsupport@contoso.com
- Portal: helpdesk.contoso.com
- Location: Building A, Floor 2, Room 205

**Hours of Operation**
- Monday - Friday: 7:00 AM - 7:00 PM
- Saturday: 9:00 AM - 1:00 PM (limited support)
- Sunday: Closed (emergency line only)

**Emergency Support (Critical Issues Only)**
- Phone: (555) 123-9999
- Available 24/7 for system-wide outages and security incidents
