# Laptop and Performance Troubleshooting Guide

**Document Version:** 2.5  
**Last Updated:** January 2026  
**Department:** IT End User Services  
**Classification:** Internal Use Only

---

## Table of Contents

1. [Performance Overview](#performance-overview)
2. [Slow Startup Issues](#slow-startup-issues)
3. [Application Performance](#application-performance)
4. [Memory and Storage](#memory-and-storage)
5. [Hardware Issues](#hardware-issues)
6. [Maintenance and Optimization](#maintenance-and-optimization)
7. [Requesting Hardware Support](#requesting-hardware-support)

---

## Performance Overview

### Standard Device Specifications

| Device Type | Processor | RAM | Storage | Recommended For |
|-------------|-----------|-----|---------|-----------------|
| Standard Laptop | Intel i5 / AMD Ryzen 5 | 8 GB | 256 GB SSD | General office work |
| Power User Laptop | Intel i7 / AMD Ryzen 7 | 16 GB | 512 GB SSD | Development, analytics |
| Executive Laptop | Intel i7 / AMD Ryzen 7 | 16 GB | 512 GB SSD | Travel, presentations |
| Workstation | Intel i9 / AMD Ryzen 9 | 32 GB | 1 TB SSD | CAD, video editing |

### Baseline Performance Expectations

| Action | Expected Time |
|--------|---------------|
| Cold boot to login screen | < 30 seconds |
| Login to usable desktop | < 60 seconds |
| Office applications launch | < 10 seconds |
| Browser launch | < 5 seconds |
| Wake from sleep | < 5 seconds |

### Quick Diagnostics Checklist

Before troubleshooting, check:
- [ ] How long since last restart? (Restart if > 7 days)
- [ ] Is disk space > 20% free?
- [ ] Are Windows updates pending?
- [ ] Is CPU/RAM usage abnormally high?
- [ ] Are there many startup programs?

---

## Slow Startup Issues

### Cold Boot Takes Too Long (> 2 minutes)

**Immediate Steps:**
1. **Check startup programs:**
   - Press Ctrl + Shift + Esc (Task Manager)
   - Go to "Startup" tab
   - Disable unnecessary items (High impact first)
   - Recommended to disable: Spotify, Discord, Adobe Updaters
   
2. **Run startup repair:**
   - Open Command Prompt as Administrator
   - Run: `sfc /scannow`
   - Wait for completion (15-20 minutes)
   - Restart computer

3. **Check disk health:**
   - Open Command Prompt as Administrator
   - Run: `chkdsk C: /f /r`
   - Schedule for next restart
   - Restart and wait for completion

### Login Takes Too Long (> 2 minutes)

**Causes and Solutions:**

| Cause | Symptom | Solution |
|-------|---------|----------|
| Profile corruption | "Preparing Windows" for 5+ min | Contact IT for profile reset |
| Group Policy updates | First login after update | Wait 5-10 min, will be faster next time |
| Roaming profile sync | Large profile size | Clear temp files, old downloads |
| Network issues | Can't reach domain controller | Check network connection |
| Antivirus scanning | High disk activity | Scheduled scan in progress, wait |

**Reduce Login Time:**
1. Clear temporary files (see Maintenance section)
2. Reduce desktop icons (move to folders)
3. Disable OneDrive sync on startup if not needed immediately
4. Ensure latest Windows updates installed

### System Hangs at Logo/Spinning Dots

**Try these in order:**

1. **Wait 10 minutes** - May be installing updates
2. **Force restart:**
   - Hold power button 10 seconds
   - Wait 30 seconds
   - Power on
3. **Safe Mode boot:**
   - Restart and press F8 repeatedly
   - Select "Safe Mode with Networking"
   - If works, likely driver or software issue
4. **Recovery options:**
   - Boot from Windows installation media
   - Select "Repair your computer"
   - Try "Startup Repair"

---

## Application Performance

### Microsoft Office Running Slow

**Outlook Slow:**
1. **Compact mailbox:**
   - File → Account Settings → Data Files
   - Select mailbox → Settings → Compact Now
2. **Reduce mailbox size:**
   - Archive old emails
   - Empty Deleted Items and Junk
   - Remove large attachments
3. **Disable add-ins:**
   - File → Options → Add-ins
   - Manage: COM Add-ins → Go
   - Uncheck non-essential add-ins
4. **Create new profile:**
   - Control Panel → Mail → Show Profiles
   - Add new profile
   - Set as default

**Excel Slow:**
1. Check file size (>50MB may cause issues)
2. Remove unnecessary formatting
3. Convert formulas to values where possible
4. Disable automatic calculations temporarily
5. Close other memory-intensive applications

**Teams Slow:**
1. Clear Teams cache:
   - Close Teams completely
   - Navigate to: `%appdata%\Microsoft\Teams`
   - Delete: Cache, blob_storage, databases, GPUcache, tmp
   - Restart Teams
2. Reduce startup items
3. Disable GPU hardware acceleration (Settings → General)
4. Update to latest version

### Browser Performance Issues

**Chrome/Edge Running Slow:**
1. **Clear browsing data:**
   - Ctrl + Shift + Delete
   - Select "All time"
   - Clear cached images and files
2. **Disable extensions:**
   - Settings → Extensions
   - Disable all, enable one by one to find culprit
3. **Reset browser:**
   - Settings → Reset settings
   - Restore settings to defaults
4. **Check for malware:**
   - Run: `chrome://settings/cleanup` (Chrome)
   - Let browser scan and clean

**Too Many Tabs:**
| Tabs Open | RAM Usage | Recommendation |
|-----------|-----------|----------------|
| < 10 | ~1-2 GB | Normal |
| 10-25 | ~2-4 GB | Consider closing some |
| 25-50 | ~4-8 GB | Performance impact likely |
| > 50 | 8+ GB | Will cause system slowdown |

### Applications Freezing/Not Responding

**Immediate Fix:**
1. Wait 30 seconds (may recover)
2. Press Ctrl + Shift + Esc
3. Find frozen app → End Task
4. Reopen application

**If Frequent:**
1. Update application to latest version
2. Repair application:
   - Settings → Apps → Find app → Modify → Repair
3. Clear application cache/data
4. Uninstall and reinstall
5. Check for Windows updates
6. Report recurring issues to IT

---

## Memory and Storage

### High Memory Usage

**Check What's Using Memory:**
1. Open Task Manager (Ctrl + Shift + Esc)
2. Click "Memory" column to sort
3. Identify top consumers

**Common Memory Hogs:**
| Application | Typical Usage | Action |
|-------------|---------------|--------|
| Chrome/Edge (many tabs) | 2-8 GB | Close unnecessary tabs |
| Teams | 500 MB - 2 GB | Restart periodically |
| Outlook | 300 MB - 1 GB | Compact mailbox |
| Visual Studio | 2-8 GB | Normal for developers |
| Antivirus scan | 1-2 GB | Wait for completion |

**Reduce Memory Usage:**
1. Close unused applications
2. Disable startup programs
3. Reduce browser tabs
4. Restart computer (clears memory)
5. If chronic issue, request RAM upgrade from IT

### Low Disk Space

**Check Disk Space:**
1. Open File Explorer
2. Right-click C: drive → Properties
3. View used vs free space

**Minimum Required:** 15% free space (20% recommended)

**Free Up Space - Quick Wins:**

| Location | Potential Savings | How to Clean |
|----------|-------------------|--------------|
| Downloads folder | 5-50 GB | Delete old downloads |
| Recycle Bin | 1-10 GB | Empty Recycle Bin |
| Temp files | 1-10 GB | Disk Cleanup tool |
| Windows Update cache | 1-20 GB | Disk Cleanup → System files |
| Browser cache | 1-5 GB | Browser settings → Clear cache |
| Teams cache | 1-5 GB | Delete cache folders |

**Using Disk Cleanup:**
1. Search "Disk Cleanup" in Start menu
2. Select C: drive
3. Click "Clean up system files"
4. Select all categories
5. Click OK → Delete Files

**Storage Sense (Automatic):**
1. Settings → System → Storage
2. Enable "Storage Sense"
3. Configure to run automatically
4. Set to delete temp files and empty Recycle Bin

### OneDrive Sync Issues

**OneDrive Using Too Much Space:**
1. Right-click OneDrive in system tray
2. Settings → Account
3. Click "Choose folders"
4. Uncheck folders you don't need locally
5. Files remain in cloud, freed locally

**Sync Not Working:**
1. Check internet connection
2. Right-click OneDrive icon → Pause syncing → Resume
3. Sign out and sign back in
4. Reset OneDrive:
   - Press Windows + R
   - Run: `%localappdata%\Microsoft\OneDrive\onedrive.exe /reset`
   - Wait 2 minutes, reopen OneDrive

---

## Hardware Issues

### Overheating

**Symptoms:**
- Fans running loudly constantly
- Laptop hot to touch
- Performance throttling
- Unexpected shutdowns

**Solutions:**
1. **Ensure ventilation:**
   - Don't use on soft surfaces (beds, couches)
   - Use laptop stand or cooling pad
   - Keep vents clear
2. **Clean vents:**
   - Use compressed air to blow out dust
   - Keep 6 inches away from vents
3. **Reduce load:**
   - Close unnecessary applications
   - Reduce screen brightness
   - Switch to power saver mode
4. **Check running processes:**
   - Task Manager → Look for high CPU apps
   - End unnecessary processes

**If overheating persists:** Submit hardware support ticket

### Battery Issues

**Battery Not Charging:**
1. Check power adapter connection (both ends)
2. Try different power outlet
3. Inspect cable for damage
4. Remove and reseat battery (if removable)
5. Update BIOS from manufacturer website
6. Submit IT ticket if no resolution

**Battery Draining Quickly:**
| Cause | Solution |
|-------|----------|
| Screen brightness high | Reduce to 50-70% |
| WiFi/Bluetooth always on | Disable when not needed |
| Background apps | Close unused applications |
| Power plan set to performance | Switch to Balanced |
| Battery age (> 3 years) | Request replacement |

**Check Battery Health:**
1. Open Command Prompt as Administrator
2. Run: `powercfg /batteryreport`
3. Open the generated HTML report
4. Check "Design Capacity" vs "Full Charge Capacity"
5. If Full Charge < 50% of Design, request replacement

### Display Issues

**Screen Flickering:**
1. Update display driver
2. Check refresh rate (Settings → Display → Advanced)
3. Disable Windows visual effects
4. Connect external monitor to test
5. Boot in Safe Mode to test

**External Monitor Not Detected:**
1. Check cable connection
2. Try different cable/port
3. Press Windows + P → Select display mode
4. Update display drivers
5. Check monitor power and input source

**Resolution Issues:**
1. Right-click desktop → Display settings
2. Select recommended resolution
3. Click "Detect" for external monitors
4. Update graphics drivers

### Keyboard and Touchpad Issues

**Keys Not Working:**
1. Restart computer
2. Check for stuck keys
3. Update keyboard driver
4. Try external keyboard
5. Run Hardware Troubleshooter

**Touchpad Not Working:**
1. Check if disabled (function key toggle)
2. Settings → Devices → Touchpad
3. Ensure touchpad is enabled
4. Update touchpad driver
5. Check if mouse connected (may auto-disable touchpad)

---

## Maintenance and Optimization

### Weekly Maintenance Checklist

- [ ] Restart computer (if running > 3 days)
- [ ] Check for Windows updates
- [ ] Clear browser cache
- [ ] Empty Downloads folder
- [ ] Empty Recycle Bin
- [ ] Close unused applications
- [ ] Check available disk space

### Monthly Maintenance

- [ ] Run Disk Cleanup (including system files)
- [ ] Run full antivirus scan
- [ ] Update applications
- [ ] Review startup programs
- [ ] Check for driver updates
- [ ] Backup important files
- [ ] Clean keyboard and screen

### Optimization Settings

**Power Settings for Performance:**
1. Settings → System → Power & sleep
2. Additional power settings → High performance
3. Change plan settings → Never turn off hard disk

**Visual Effects (for older hardware):**
1. Right-click Start → System
2. Advanced system settings
3. Performance → Settings
4. Select "Adjust for best performance" or customize

**Disable Unnecessary Services:**
1. Search "Services" in Start
2. Set to Manual or Disabled:
   - Fax
   - Print Spooler (if no printer)
   - Bluetooth (if not used)
   - Xbox services (if not used)

### Windows Update Best Practices

1. Install updates weekly
2. Schedule updates outside work hours
3. Restart promptly after updates
4. Allow 2-3 restarts for major updates
5. Don't interrupt update process
6. Keep 10GB free for updates

---

## Requesting Hardware Support

### When to Contact IT

**Submit ticket for:**
- Hardware making unusual noises
- Physical damage (screen, keyboard, ports)
- Battery won't hold charge
- Repeated blue screens
- Overheating despite troubleshooting
- Performance issues after all self-service steps

### How to Submit Hardware Ticket

1. Go to IT Service Portal: https://itportal.contoso.com
2. Select "Hardware Support"
3. Include:
   - Device model and serial number
   - Detailed description of issue
   - Steps already tried
   - When problem started
   - Error messages (screenshots)
4. Attach photos if physical damage

### Hardware Replacement Process

| Device Age | Process |
|------------|---------|
| Under warranty (< 3 years) | Repair or manufacturer replacement |
| Out of warranty (3-4 years) | IT assessment for refresh |
| Refresh eligible (> 4 years) | New device via IT procurement |

### Loaner Device Request

For critical hardware failures:
1. Contact IT Help Desk immediately
2. Request loaner device
3. Available for up to 2 weeks
4. Must return when primary device is fixed

---

## Contact Information

| Service | Contact | Hours |
|---------|---------|-------|
| IT Help Desk | helpdesk@contoso.com / ext. 4357 | Mon-Fri 7AM-7PM |
| Hardware Support | hardware@contoso.com | Mon-Fri 8AM-5PM |
| Device Pickup/Dropoff | IT Service Center, Building A, Room 101 | Mon-Fri 9AM-4PM |
| Emergency Hardware | ext. 4911 | 24/7 |

---

*This document is maintained by IT End User Services. For updates, contact enduser@contoso.com.*
