# Exercise 10: Test and Deploy IT Support Copilot to Microsoft Teams

## Estimated Duration: 30 Minutes

## Overview

In this exercise, you will perform comprehensive end-to-end testing of your IT Support Copilot, verify that tickets are being created correctly in Freshdesk, and then deploy the copilot to Microsoft Teams for organization-wide access.

This is the final step in building an autonomous IT support solution that uses the knowledge base to provide troubleshooting guidance and creates tickets in Freshdesk when escalation is needed—all integrated with Microsoft Teams.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Test IT Support Topics End-to-End
- Task 2: Verify Tickets in Freshdesk Portal
- Task 3: Test Knowledge Base Integration
- Task 4: Publish the Copilot to Microsoft Teams
- Task 5: Test the Copilot in Microsoft Teams

### Task 1: Test IT Support Topics End-to-End

In this task, you will systematically test all three IT support topics to ensure they work correctly with Freshdesk integration.

1. In Microsoft Copilot Studio, open your **IT Support Copilot**.

   ![](./media/ex10-open-copilot.png)

1. Click the **Test** button to open the test panel on the right side.

   ![](./media/ex10-test-panel.png)

1. Ensure all 3 topics are **enabled**:
   - CredentialResetSupport
   - VPNConnectivitySupport
   - HardwareSupportAssistant

1. Open a second browser tab with your **Freshdesk portal**:
   ```
   https://your-company-name.freshdesk.com
   ```

1. Sign in to Freshdesk and navigate to **Tickets** to monitor ticket creation in real-time.

   ![](./media/ex10-freshdesk-tickets.png)

   >**Tip:** Keep both Copilot Studio and Freshdesk tabs visible for testing.

1. **Test Scenario 1 - CredentialResetSupport Topic:**

   In the Copilot Studio test panel, click **Reset** to start a fresh conversation.

   **Prompt:**
   ```
   I forgot my password
   ```

   ![](./media/ex10-test-password.png)

1. Follow the conversation flow:
   - Provide your username when asked (e.g., `jsmith`)
   - Review the self-service reset instructions from the knowledge base
   - When asked if the issue is resolved, say: **No**
   - Confirm you want to create a support ticket

1. **Expected Results:**
   - Copilot should ask for username and provide reset instructions
   - Should offer to create a ticket when issue isn't resolved
   - Should display confirmation message after ticket creation

   ![](./media/ex10-password-result.png)

1. **Test Scenario 2 - VPNConnectivitySupport Topic:**

   Click **Reset** to start fresh.

   **Prompt:**
   ```
   VPN won't connect
   ```

   ![](./media/ex10-test-vpn.png)

1. Follow the conversation:
   - Describe the error (e.g., `Authentication failed when trying to connect`)
   - Provide location (e.g., `Working from home`)
   - Follow troubleshooting steps provided
   - When asked if resolved, say: **No, still not working**
   - Confirm ticket creation

1. **Expected Results:**
   - Copilot collects error message and location
   - Provides relevant troubleshooting steps
   - Creates ticket with location in subject line

   ![](./media/ex10-vpn-result.png)

1. **Test Scenario 3 - HardwareSupportAssistant Topic:**

   Click **Reset** to start fresh.

   **Prompt:**
   ```
   My laptop is slow
   ```

   ![](./media/ex10-test-hardware.png)

1. Follow the conversation:
   - Select device type when asked (e.g., `Laptop`)
   - Describe the issue (e.g., `Very slow performance, takes 10 minutes to boot`)
   - Follow diagnostic steps
   - When asked if resolved, say: **No**
   - Confirm ticket creation

1. **Expected Results:**
   - Copilot identifies device type and captures symptoms
   - Provides device-specific troubleshooting
   - Creates ticket with device type in subject

   ![](./media/ex10-hardware-result.png)

### Task 2: Verify Tickets in Freshdesk Portal

In this task, you will verify that all test tickets were created correctly in Freshdesk.

1. Switch to your **Freshdesk portal** browser tab.

1. Go to **Tickets** in the left navigation (or click on **All Tickets**).

   ![](./media/ex10-freshdesk-all-tickets.png)

1. You should see the tickets created during testing. Verify you have tickets with subjects like:
   - "Password Reset Assistance – jsmith"
   - "Connectivity Issue – home" (or similar)
   - "Hardware Issue – Laptop"

   ![](./media/ex10-freshdesk-ticket-list.png)

1. Click on the **Password Reset** ticket to open it.

1. Verify the ticket details:

   | Field | Expected Value |
   |-------|----------------|
   | Subject | Contains "Password Reset Assistance" and username |
   | Description | Contains username and reason for escalation |
   | Priority | Medium |
   | Status | Open |
   | Requester Email | Your lab email address |

   ![](./media/ex10-freshdesk-ticket-details.png)

1. Click on the **Connectivity Issue** ticket and verify:

   | Field | Expected Value |
   |-------|----------------|
   | Subject | Contains "Connectivity Issue" and location |
   | Description | Contains error message and location details |
   | Priority | Medium |
   | Status | Open |

1. Click on the **Hardware Issue** ticket and verify:

   | Field | Expected Value |
   |-------|----------------|
   | Subject | Contains "Hardware Issue" and device type |
   | Description | Contains device type and issue description |
   | Priority | Medium |
   | Status | Open |

1. Document your test results:

   | Test Scenario | Topic Triggered | Ticket Created | Details Correct |
   |---------------|-----------------|----------------|-----------------|
   | Password Reset | ☐ Yes / ☐ No | ☐ Yes / ☐ No | ☐ Yes / ☐ No |
   | VPN Connectivity | ☐ Yes / ☐ No | ☐ Yes / ☐ No | ☐ Yes / ☐ No |
   | Hardware Issue | ☐ Yes / ☐ No | ☐ Yes / ☐ No | ☐ Yes / ☐ No |

   >**Troubleshooting:** If tickets are not appearing:
   >- Check that the Freshdesk flow is published in Copilot Studio
   >- Verify the Freshdesk connection is valid (test the flow manually)
   >- Check for any error messages in the test panel

### Task 3: Test Knowledge Base Integration

In this task, you will verify that your copilot can answer questions directly from the knowledge base without creating tickets.

1. Return to the **Copilot Studio** test panel and click **Reset**.

1. Ask a general IT question:

   **Prompt:**
   ```
   How do I set up MFA on my account?
   ```

   ![](./media/ex10-test-kb-mfa.png)

1. **Expected Results:**
   - Copilot provides a direct answer from the knowledge base
   - Does NOT trigger a topic or offer to create a ticket immediately
   - Provides helpful step-by-step instructions

   ![](./media/ex10-kb-mfa-result.png)

1. Try another knowledge base query:

   **Prompt:**
   ```
   What VPN client should I use?
   ```

1. Verify the response comes from your uploaded IT Support documents.

1. Test a hardware-related knowledge query:

   **Prompt:**
   ```
   How do I clean up disk space on my laptop?
   ```

1. **Expected:** Copilot should provide disk cleanup instructions from the knowledge base.

1. If responses are generic or not pulling from your knowledge base:
   - Go to **Settings** → **Generative AI**
   - Ensure the knowledge source toggle is enabled
   - Verify your SharePoint IT Support site is connected with status **Ready**

### Task 4: Publish the Copilot to Microsoft Teams

In this task, you will publish your IT Support Copilot and make it available in Microsoft Teams.

1. In Copilot Studio, click **Publish** in the top menu bar.

   ![](./media/ex10-publish-button.png)

1. Review the publishing checklist:

   - ✅ All topics are saved and enabled
   - ✅ Freshdesk flow is connected and published
   - ✅ Knowledge base is synced and ready
   - ✅ All testing is complete

   ![](./media/ex10-publish-checklist.png)

1. Click **Publish** to publish your copilot.

   ![](./media/ex10-confirm-publish.png)

1. Wait for the publishing process to complete (1-2 minutes). You should see a success message.

   ![](./media/ex10-publish-success.png)

1. Click on **Channels** in the left navigation.

   ![](./media/ex10-channels.png)

1. Find **Microsoft Teams** and click on it.

   ![](./media/ex10-teams-channel.png)

1. Click **Turn on Teams** to enable the Teams channel.

   ![](./media/ex10-turn-on-teams.png)

1. Configure the Teams availability:

   - Select **Show to everyone in my org** (recommended for company-wide access)
   - Or select **Show to users or groups** for limited rollout

   ![](./media/ex10-teams-availability.png)

1. Click **Submit for admin approval** (or **Add to Teams** if you have permissions).

   >**Note:** Depending on your organization's policies, the copilot may need admin approval before appearing in the Teams app catalog.

1. Click **Open the app in Teams** or **Add to Teams** to install the bot in Teams.

   ![](./media/ex10-add-to-teams.png)

### Task 5: Test the Copilot in Microsoft Teams

In this task, you will test the complete user journey within Microsoft Teams.

1. Microsoft Teams should open with your IT Support Copilot. 

   If not, open Teams manually:
   ```
   https://teams.microsoft.com
   ```

1. Sign in with your lab credentials if prompted:
   - **Email:** <inject key="AzureAdUserEmail"></inject>
   - **Password:** <inject key="AzureAdUserPassword"></inject>

1. In Teams, click **Apps** in the left sidebar.

1. Search for **IT Support Copilot** and click on it.

   ![](./media/ex10-teams-search.png)

1. Click **Add** to add the copilot to your Teams.

1. The copilot chat will open automatically.

   ![](./media/ex10-teams-copilot.png)

1. **Test 1 - Password Reset in Teams:**

   **Prompt:**
   ```
   I forgot my password
   ```

   ![](./media/ex10-teams-password.png)

1. Follow the conversation:
   - Provide username when asked
   - Review the self-service instructions
   - When asked if resolved, say: **No**
   - Confirm ticket creation

1. Verify:
   - Confirmation message appears in Teams
   - Switch to Freshdesk and verify the ticket was created

   ![](./media/ex10-teams-password-complete.png)

1. **Test 2 - VPN Issue in Teams:**

   **Prompt:**
   ```
   VPN won't connect from home
   ```

1. Follow the conversation and escalate to ticket creation.

1. Verify ticket appears in Freshdesk with correct details.

1. **Test 3 - Knowledge Base Query in Teams:**

   **Prompt:**
   ```
   What are the steps to reset my password?
   ```

   ![](./media/ex10-teams-kb-query.png)

1. **Expected:** The copilot should provide instructions from the knowledge base without offering to create a ticket.

   ![](./media/ex10-teams-kb-result.png)

1. (Optional) **Share the copilot with your team:**

   - In Copilot Studio, go to **Channels** → **Microsoft Teams**
   - Click **Availability options**
   - Copy the **Share link**
   - Share via email or Teams channel:

   ```
   New IT Support Copilot Available!

   Get instant IT support directly in Teams. Our new copilot can help with:
   - Password resets and account lockouts
   - VPN and connectivity issues
   - Hardware troubleshooting (laptops, printers, monitors, keyboards)
   - And more!

   Simply search for "IT Support Copilot" in Teams Apps to get started.
   ```

## Summary

In this exercise, you completed the full lifecycle of testing and deploying your IT Support Copilot. You learned how to:

- Test all three AI-generated topics (CredentialResetSupport, VPNConnectivitySupport, HardwareSupportAssistant)
- Verify that tickets are created correctly in Freshdesk with proper subject, description, and priority
- Validate knowledge base integration for direct answers without ticket creation
- Publish a copilot and enable the Microsoft Teams channel
- Test the complete user experience directly within Microsoft Teams

Your IT Support Copilot is now live in Microsoft Teams, ready to help employees with:
- ✅ Password reset and account access issues (with Freshdesk escalation)
- ✅ VPN and network connectivity problems (with Freshdesk escalation)
- ✅ Hardware troubleshooting for laptops, printers, and peripherals (with Freshdesk escalation)
- ✅ Direct answers from the IT knowledge base
- ✅ Automatic ticket creation in Freshdesk when issues cannot be self-resolved

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
