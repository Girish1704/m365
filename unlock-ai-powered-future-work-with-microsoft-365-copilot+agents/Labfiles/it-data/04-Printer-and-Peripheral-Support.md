# Printer and Peripheral Support Guide

**Document Version:** 1.8  
**Last Updated:** January 2026  
**Department:** IT End User Services  
**Classification:** Internal Use Only

---

## Table of Contents

1. [Office Printer Setup](#office-printer-setup)
2. [Common Printer Issues](#common-printer-issues)
3. [Print Job Management](#print-job-management)
4. [Secure Print and Follow-Me Printing](#secure-print-and-follow-me-printing)
5. [Home Printer Setup](#home-printer-setup)
6. [Peripheral Devices](#peripheral-devices)
7. [Requesting Printer Support](#requesting-printer-support)

---

## Office Printer Setup

### Available Printers by Location

| Building | Floor | Printer Name | Capabilities | Location |
|----------|-------|--------------|--------------|----------|
| HQ | 1 | HQ-1F-MFP01 | Print, Copy, Scan, Fax | Near reception |
| HQ | 2 | HQ-2F-MFP01 | Print, Copy, Scan | Kitchen area |
| HQ | 2 | HQ-2F-CLR01 | Color print only | Creative dept |
| HQ | 3 | HQ-3F-MFP01 | Print, Copy, Scan | Central hall |
| Branch A | 1 | BRA-1F-MFP01 | Print, Copy, Scan | Main office |
| Remote | - | Follow-Me | All printers | Any location |

### Adding Office Printers (Windows)

**Automatic Installation:**
1. Open Settings → Devices → Printers & scanners
2. Click "Add a printer or scanner"
3. Wait for discovery (may take 30 seconds)
4. Select the desired printer from the list
5. Click "Add device"

**Manual Installation:**
1. Open Settings → Devices → Printers & scanners
2. Click "Add a printer or scanner"
3. Click "The printer I want isn't listed"
4. Select "Select a shared printer by name"
5. Enter: `\\printserver.contoso.local\PrinterName`
   - Example: `\\printserver.contoso.local\HQ-2F-MFP01`
6. Click Next and wait for driver installation
7. Print test page to verify

**Print Server Address:** `\\printserver.contoso.local`

### Adding Office Printers (Mac)

1. System Preferences → Printers & Scanners
2. Click the + button
3. Select the "IP" tab
4. Protocol: IPP
5. Address: Enter printer IP (see IT portal for IPs)
6. Queue: Leave blank or enter printer name
7. Name: Enter friendly name
8. Click Add

---

## Common Printer Issues

### Printer Shows "Offline"

**Quick Fixes (try in order):**

1. **Check physical status:**
   - Is printer powered on? (Look for lights)
   - Any error lights or messages on display?
   - Is paper loaded?

2. **Restart print spooler:**
   - Press Windows + R
   - Type: `services.msc`
   - Find "Print Spooler"
   - Right-click → Restart

3. **Set printer online:**
   - Settings → Devices → Printers & scanners
   - Select the printer → Open queue
   - Printer menu → Uncheck "Use Printer Offline"

4. **Remove and re-add printer:**
   - Settings → Devices → Printers & scanners
   - Select printer → Remove device
   - Re-add using steps above

### Paper Jams

**Standard Jam Clearance:**
1. Turn off printer
2. Open all access doors (front, back, sides)
3. Gently remove jammed paper (pull in direction of paper path)
4. Check for small torn pieces
5. Close all doors
6. Turn on printer
7. Wait for ready status
8. Reprint document

**Common Jam Locations:**
| Location | Access | Notes |
|----------|--------|-------|
| Input tray | Lift tray, pull paper | Check for overfilled tray |
| Fuser area | Open rear door | Caution: May be hot |
| Output area | Check output tray | Paper may be stuck halfway |
| Duplex unit | Access from bottom/back | Common for double-sided |

**Preventing Jams:**
- Don't overfill paper trays
- Fan paper before loading
- Use correct paper size and type
- Store paper in dry location
- Remove curled or damaged sheets

### Print Quality Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Faded prints | Low toner | Replace toner cartridge |
| Black lines | Dirty drum | Clean or replace drum |
| Smeared print | Fuser issue | Contact IT for service |
| Spotty print | Debris on drum | Print cleaning page |
| Crooked print | Paper guides | Adjust paper guides |
| Wrong colors | Color calibration | Run calibration from printer |

**Running Printer Cleaning:**
1. On printer display: Settings → Maintenance
2. Select "Print Cleaning Page"
3. Follow instructions
4. May need to run multiple times

### Printer Not Printing

**Troubleshooting Steps:**

1. **Check print queue:**
   - Settings → Devices → Printers & scanners
   - Select printer → Open queue
   - Cancel all stuck jobs (Ctrl + A, then Delete)

2. **Verify printer connection:**
   - Ping printer: `ping printername.contoso.local`
   - Check network cable (for network printers)
   - Restart printer

3. **Check default printer:**
   - Ensure correct printer is set as default
   - Right-click printer → Set as default

4. **Update printer driver:**
   - Device Manager → Print queues
   - Right-click printer → Update driver

5. **Test with Notepad:**
   - Open Notepad, type test text
   - Print to isolate application issues

### Error Messages

| Error | Meaning | Action |
|-------|---------|--------|
| "Toner Low" | Toner running out | Order replacement, can continue printing |
| "Toner Empty" | Must replace to print | Replace toner cartridge |
| "Paper Empty" | Tray needs paper | Load paper in indicated tray |
| "Paper Mismatch" | Wrong size loaded | Load correct size or change job settings |
| "Door Open" | Cover not closed | Close all covers securely |
| "Service Required" | Internal error | Contact IT for service |
| "Memory Full" | Too complex/large job | Simplify document or print in parts |

---

## Print Job Management

### Viewing and Canceling Print Jobs

**From Windows:**
1. Settings → Devices → Printers & scanners
2. Select printer → Open queue
3. View all pending jobs
4. Right-click job → Cancel

**From Printer:**
1. Locate printer display panel
2. Navigate to Jobs or Queue
3. Select your job (by username)
4. Press Cancel or Delete

### Managing Large Print Jobs

**Best Practices:**
- Print in batches (50-100 pages)
- Use off-peak hours for large jobs
- Consider color vs B&W for cost
- Use draft quality for internal documents

**Canceling Stuck Jobs:**
1. Stop print spooler:
   - Open Services (services.msc)
   - Stop "Print Spooler"
2. Clear print queue files:
   - Navigate to: `C:\Windows\System32\spool\PRINTERS`
   - Delete all files in folder
3. Start print spooler
4. Retry print job

---

## Secure Print and Follow-Me Printing

### What is Secure Print?

Secure Print holds your document at the print server until you authenticate at the printer. This:
- Prevents others from seeing your documents
- Reduces waste from unclaimed prints
- Allows printing to any enabled printer

### How to Use Secure Print

**Sending a Secure Print Job:**
1. In any application, select Print
2. Choose "Contoso Secure Print" as printer
3. Click Print
4. Document is held for 24 hours

**Releasing at Printer:**
1. Walk to any Secure Print enabled printer
2. Badge in with your employee ID card
3. View your waiting documents
4. Select documents to print or "Print All"
5. Collect your printouts

### Follow-Me Printing

Follow-Me extends Secure Print across all locations:
1. Print to "Contoso Follow-Me" from anywhere
2. Badge in at any printer in any office
3. Your jobs follow you to that location
4. Print when and where convenient

### Secure Print Troubleshooting

| Issue | Solution |
|-------|----------|
| Jobs not showing at printer | Wait 2-3 minutes for sync, badge out/in |
| Badge not recognized | Try different printer, contact IT for badge check |
| Jobs expired | Resend print job (24-hour expiration) |
| Print quality issues | Same as regular printer troubleshooting |

---

## Home Printer Setup

### Supported Home Printers

IT provides limited support for personal printers. For full support:
- Use corporate printing via VPN to office printers
- Request a company-issued portable printer

### Basic Home Printer Setup

**USB Connected:**
1. Connect printer to laptop via USB
2. Wait for automatic driver installation
3. If needed, download driver from manufacturer website
4. Print test page

**WiFi Connected:**
1. Connect printer to your home WiFi
2. Find printer IP (usually on printer display or print network config)
3. Settings → Devices → Printers & scanners
4. Add printer → Search or enter IP

**Manufacturer Support Links:**
| Brand | Support URL |
|-------|-------------|
| HP | support.hp.com |
| Canon | usa.canon.com/support |
| Epson | epson.com/support |
| Brother | support.brother.com |
| Lexmark | support.lexmark.com |

### Printing via VPN to Office Printers

1. Connect to VPN
2. Office printers should appear automatically
3. If not, add manually using print server path
4. Note: Large jobs may be slow over VPN
5. Consider printing to PDF and using Secure Print later

---

## Peripheral Devices

### Monitors

**Connecting External Monitors:**
1. Connect via HDMI, DisplayPort, or USB-C
2. Press Windows + P to select display mode:
   - Duplicate: Same on both screens
   - Extend: Spread across screens
   - Second screen only: External only
3. Adjust resolution in Settings → Display

**Monitor Not Detected:**
1. Check cable connections
2. Try different cable
3. Try different port on laptop
4. Update graphics driver
5. Restart laptop

**Supported Configurations:**
| Laptop Port | Max External Monitors | Notes |
|-------------|----------------------|-------|
| USB-C/Thunderbolt | Up to 3 | Via dock or daisy chain |
| HDMI | 1 | Direct connection |
| USB-C dock | Up to 3 | Depends on dock model |

### Docking Stations

**Standard Docks Supported:**
- Dell WD19S Thunderbolt Dock
- HP USB-C Dock G5
- Lenovo ThinkPad USB-C Dock

**Dock Setup:**
1. Connect dock to power
2. Connect peripherals to dock
3. Connect laptop via USB-C/Thunderbolt
4. First connection installs drivers automatically
5. May need restart for full functionality

**Dock Troubleshooting:**
| Issue | Solution |
|-------|----------|
| Monitors flickering | Update dock firmware |
| USB devices not recognized | Try different ports, update drivers |
| No power to laptop | Check power adapter connection |
| Network issues through dock | Use laptop's built-in WiFi as backup |

### Webcams and Headsets

**Supported Devices:**
- Logitech C920/C922/BRIO
- Microsoft LifeCam HD-3000
- Jabra Speak series
- Poly (Plantronics) headsets

**Webcam Not Working:**
1. Check privacy settings:
   - Settings → Privacy → Camera
   - Enable camera access
   - Enable for specific apps
2. Check if physically covered (privacy slider)
3. Try different USB port
4. Check in Device Manager for errors
5. Update webcam driver

**Audio Device Issues:**
1. Check it's set as default:
   - Right-click speaker icon → Sounds
   - Playback/Recording tabs
   - Set device as Default
2. Check mute status
3. Update audio drivers
4. Try different USB port

### Keyboards and Mice

**Wireless Device Setup:**
1. Insert USB receiver
2. Turn on device
3. Windows installs automatically
4. If pairing needed, press connect button on device

**Bluetooth Device Pairing:**
1. Put device in pairing mode (usually hold power button)
2. Settings → Devices → Bluetooth
3. Enable Bluetooth if off
4. Click "Add Bluetooth device"
5. Select device from list
6. Complete pairing

**Troubleshooting:**
| Issue | Solution |
|-------|----------|
| Lag or stuttering | Replace batteries, move receiver closer |
| Not responding | Turn off/on, re-pair |
| Keys stuck | Clean keyboard, check for debris |
| Double clicking mouse | Clean sensor, may need replacement |

---

## Requesting Printer Support

### Self-Service Options

**Before contacting IT:**
1. Check this guide for solutions
2. Power cycle the printer
3. Check printer display for specific errors
4. Verify paper and toner levels
5. Try from a different computer

### Submitting a Printer Ticket

1. Go to IT Service Portal: https://itportal.contoso.com
2. Select "Printer Support"
3. Include:
   - Printer name/location
   - Specific error message
   - What you were trying to print
   - Steps already attempted
   - Screenshot if applicable

### Toner and Supply Requests

**Office Printers:**
- Toner is automatically reordered
- If urgent: Submit ticket or call ext. 4357

**Request Process:**
1. IT Service Portal → Request → Printer Supplies
2. Select printer from dropdown
3. Select supply type (toner, drum, staples)
4. Delivery typically within 24-48 hours

### Printer Relocation or New Printer

**Relocating a Printer:**
1. Submit ticket 2 weeks in advance
2. Include current and new location
3. IT will coordinate move and reconfiguration

**Requesting New Printer:**
1. Requires manager approval
2. Submit request through IT Service Portal
3. Include business justification
4. Allow 2-4 weeks for procurement

---

## Contact Information

| Service | Contact | Hours |
|---------|---------|-------|
| IT Help Desk | helpdesk@contoso.com / ext. 4357 | Mon-Fri 7AM-7PM |
| Printer Support | printers@contoso.com | Mon-Fri 8AM-5PM |
| Supply Orders | supplies@contoso.com | Order anytime |
| Peripheral Support | hardware@contoso.com | Mon-Fri 8AM-5PM |

---

*This document is maintained by IT End User Services. For updates, contact enduser@contoso.com.*
