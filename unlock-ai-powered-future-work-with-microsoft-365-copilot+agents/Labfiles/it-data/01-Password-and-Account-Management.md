# Password and Account Management Guide

**Document Version:** 2.1  
**Last Updated:** January 2026  
**Department:** IT Security & Identity Management  
**Classification:** Internal Use Only

---

## Table of Contents

1. [Password Policy Overview](#password-policy-overview)
2. [Self-Service Password Reset](#self-service-password-reset)
3. [Account Lockout Resolution](#account-lockout-resolution)
4. [Multi-Factor Authentication (MFA)](#multi-factor-authentication-mfa)
5. [Common Account Issues](#common-account-issues)
6. [Emergency Access Procedures](#emergency-access-procedures)

---

## Password Policy Overview

### Current Password Requirements

All employee passwords must meet the following criteria:

| Requirement | Specification |
|-------------|---------------|
| Minimum Length | 14 characters |
| Maximum Length | 128 characters |
| Uppercase Letters | At least 1 required |
| Lowercase Letters | At least 1 required |
| Numbers | At least 1 required |
| Special Characters | At least 1 required (!@#$%^&*()_+-=[]{}|;:,.<>?) |
| Password History | Cannot reuse last 12 passwords |
| Maximum Age | 90 days (prompted 14 days before expiry) |
| Minimum Age | 1 day (prevents rapid cycling) |

### Password Best Practices

**DO:**
- Use a passphrase (e.g., "Coffee@Morning2026!Sunshine")
- Use a password manager for storing complex passwords
- Create unique passwords for each system
- Change your password immediately if you suspect compromise

**DON'T:**
- Use personal information (birthdays, pet names, addresses)
- Share passwords with anyone, including IT staff
- Write passwords on sticky notes or store in plain text
- Use common words or patterns (Password123!, Qwerty@2026)

### Prohibited Password Patterns

The system will reject passwords containing:
- Your username or email address
- Company name variations (Contoso, C0nt0s0, etc.)
- Sequential characters (abcd, 1234, qwerty)
- Repeated characters (aaaa, 1111)
- Common dictionary words without modification
- Previously breached passwords (checked against database)

---

## Self-Service Password Reset

### Prerequisites for Self-Service Password Reset (SSPR)

Before you can use SSPR, ensure you have registered at least TWO of the following:

1. **Mobile Phone** - For SMS verification codes
2. **Alternate Email** - Personal email address (not company email)
3. **Microsoft Authenticator App** - Push notifications or codes
4. **Security Questions** - Answer 3 of 5 pre-selected questions
5. **Office Phone** - For voice call verification

### How to Register for SSPR

1. Navigate to: https://aka.ms/ssprsetup
2. Sign in with your corporate credentials
3. Complete registration for at least 2 authentication methods
4. Verify each method works correctly
5. Save your security question answers securely

### Password Reset Steps

**Method 1: Online Portal**

1. Go to https://passwordreset.microsoftonline.com
2. Enter your corporate email address
3. Complete the CAPTCHA verification
4. Choose your verification method:
   - Text my mobile phone
   - Call my mobile phone
   - Email my alternate email
   - Answer security questions
5. Enter the verification code received
6. Create your new password following policy requirements
7. Confirm the new password
8. Click "Finish" to complete the reset

**Method 2: Windows Login Screen**

1. On the Windows login screen, click "I forgot my password"
2. Enter your corporate email address
3. Complete CAPTCHA verification
4. Select verification method and complete verification
5. Enter and confirm new password
6. Sign in with new credentials

**Method 3: Microsoft Authenticator App**

1. Open Microsoft Authenticator on your mobile device
2. Tap on your work account
3. Select "Change password"
4. Verify your identity using biometrics or PIN
5. Enter current password (if known) or select "Forgot password"
6. Follow prompts to create new password

### Password Reset Troubleshooting

| Issue | Solution |
|-------|----------|
| "You are not registered for SSPR" | Contact IT Help Desk to register or visit https://aka.ms/ssprsetup |
| Verification code not received | Check spam folder, verify phone number, wait 2 minutes and retry |
| "Password doesn't meet requirements" | Ensure 14+ characters with uppercase, lowercase, number, and special character |
| "Password was used recently" | Choose a completely different password (12 password history) |
| Account locked after reset | Wait 30 minutes or contact IT Help Desk |

---

## Account Lockout Resolution

### Automatic Lockout Policy

Accounts are automatically locked after:
- **5 failed login attempts** within a 15-minute window
- **Automatic unlock** after 30 minutes of no activity
- **Manual unlock** available from IT Help Desk immediately

### Lockout Indicators

You may be locked out if you see:
- "Your account has been locked"
- "Too many failed attempts"
- "Account temporarily disabled"
- "Sign-in blocked for security reasons"

### Self-Service Unlock Steps

1. **Wait 30 minutes** - Account automatically unlocks
2. **Reset password** - Use SSPR at https://passwordreset.microsoftonline.com
3. **Clear cached credentials:**
   - Press Windows + R
   - Type: `rundll32.exe keymgr.dll,KRShowKeyMgr`
   - Delete any entries related to your organization
   - Restart applications and sign in fresh

### Common Lockout Causes

| Cause | Resolution |
|-------|------------|
| Forgotten password | Use SSPR to reset |
| Caps Lock enabled | Check Caps Lock indicator and retry |
| Old password cached on mobile | Update password on all devices |
| Outlook/Teams using old password | Sign out and back in with new password |
| VPN client caching credentials | Disconnect VPN, update password, reconnect |
| Mapped drives with saved credentials | Remove and re-add with new credentials |
| Scheduled tasks using old password | Update scheduled task credentials |

### Preventing Future Lockouts

1. Update password on all devices immediately after changing
2. Sign out of all applications before password change
3. Use "Sign out everywhere" option when resetting password
4. Update password manager entries promptly
5. Don't share credentials across personal and work accounts

---

## Multi-Factor Authentication (MFA)

### Supported MFA Methods

| Method | Security Level | Recommended For |
|--------|----------------|-----------------|
| Microsoft Authenticator (Push) | Highest | All employees (Primary) |
| Microsoft Authenticator (TOTP) | High | Backup method |
| Hardware Security Key (FIDO2) | Highest | Executives, IT Staff |
| SMS Text Message | Medium | Backup only |
| Voice Call | Medium | Accessibility needs |

### Setting Up Microsoft Authenticator

1. Download Microsoft Authenticator from App Store or Google Play
2. Open the app and tap "Add account"
3. Select "Work or school account"
4. Choose "Scan QR code"
5. Go to https://aka.ms/mfasetup on your computer
6. Sign in and select "Add method" > "Authenticator app"
7. Scan the QR code displayed on screen
8. Complete test notification to verify setup

### MFA Troubleshooting

**"I don't have my phone"**
1. Use backup authentication method if configured
2. Contact IT Help Desk for temporary access pass
3. Request emergency bypass (requires manager approval)

**"Authenticator not receiving notifications"**
1. Check phone has internet connection
2. Open Authenticator and pull down to refresh
3. Check notification permissions are enabled
4. Check Do Not Disturb is disabled
5. Try using the 6-digit code instead of push notification

**"Code is invalid or expired"**
1. Verify phone time is correct (enable automatic time)
2. Wait for new code (codes valid for 30 seconds)
3. Ensure you're using the correct account in Authenticator
4. Remove and re-add the account in Authenticator

### Temporary Access Pass

For emergency access without MFA:
1. Contact IT Help Desk: helpdesk@contoso.com or ext. 4357
2. Verify identity with employee ID and security questions
3. Receive temporary access pass valid for 8 hours
4. Use the pass instead of MFA for the specified duration
5. Set up new MFA method immediately after regaining access

---

## Common Account Issues

### "Your session has expired"

**Cause:** Token timeout or policy enforcement

**Resolution:**
1. Close all browser tabs and applications
2. Clear browser cache: Ctrl + Shift + Delete
3. Close and reopen browser
4. Sign in again with current credentials
5. If persistent, sign out of all sessions at https://myaccount.microsoft.com

### "You don't have permission to access this resource"

**Cause:** Missing group membership or license

**Resolution:**
1. Verify you should have access (check with your manager)
2. Submit access request through IT Service Portal
3. Wait for approval and provisioning (typically 24-48 hours)
4. Sign out and back in after access is granted

### "This sign-in was blocked"

**Cause:** Conditional Access policy or security detection

**Resolution:**
1. Check if you're using an approved device
2. Verify you're on a compliant network (VPN if remote)
3. Ensure your device meets security requirements
4. Contact IT Security if traveling internationally
5. Complete any required compliance attestations

### Email Synchronization Issues

**Outlook not receiving new emails:**
1. Check internet connection
2. Verify account status at https://portal.office.com
3. Remove and re-add account in Outlook
4. Run Office repair from Control Panel
5. Clear Outlook cache and restart

**Mobile device not syncing:**
1. Check device has internet access
2. Verify account password is current
3. Remove and re-add corporate account
4. Check MDM enrollment status
5. Restart device after re-adding account

---

## Emergency Access Procedures

### After-Hours Account Issues

**IT Help Desk Hours:** Monday-Friday, 7:00 AM - 7:00 PM EST

**After-Hours Emergency Line:** 1-800-555-HELP (4357)
- Available 24/7 for critical business needs
- Requires manager authorization for password resets
- $50 charge applies for non-emergency calls

### Executive Access Recovery

For VP level and above:
1. Call Executive IT Support: ext. 5000
2. Verify identity with executive assistant
3. Temporary password provided within 15 minutes
4. In-person verification required within 24 hours

### Compromised Account Response

If you suspect your account is compromised:
1. **Immediately call IT Security:** ext. 4500 or security@contoso.com
2. **Do not** attempt to sign in again
3. **Do not** click any links in suspicious emails
4. Note the time and any suspicious activity observed
5. IT Security will disable account and investigate
6. New credentials issued after verification

### Reporting Security Incidents

All security concerns should be reported to:
- **Email:** security@contoso.com
- **Phone:** ext. 4500
- **Portal:** https://security.contoso.com/report

Include in your report:
- Date and time of incident
- Description of suspicious activity
- Screenshots if available
- List of potentially affected data or systems

---

## Contact Information

| Service | Contact | Hours |
|---------|---------|-------|
| IT Help Desk | helpdesk@contoso.com / ext. 4357 | Mon-Fri 7AM-7PM |
| Password Reset Portal | https://passwordreset.microsoftonline.com | 24/7 |
| MFA Setup | https://aka.ms/mfasetup | 24/7 |
| IT Security Team | security@contoso.com / ext. 4500 | Mon-Fri 8AM-6PM |
| After-Hours Emergency | 1-800-555-HELP | 24/7 |

---

*This document is maintained by the IT Security & Identity Management team. For updates or corrections, contact identity@contoso.com.*
