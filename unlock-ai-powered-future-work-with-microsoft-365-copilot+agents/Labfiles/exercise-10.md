# Exercise 10: Test and Deploy IT Support Copilot to Microsoft Teams

## Estimated Duration: 30 Minutes

## Overview

In this exercise, you will perform comprehensive testing of the IT Support Copilot you built in the previous exercises, then deploy it to Microsoft Teams for organization-wide access. You will validate all scenarios, verify flow integrations, and publish the agent to make it available for end users.

This is the final step in building an autonomous IT support solution that can handle tickets, send notifications, escalate issues, and provide troubleshooting guidance—all integrated with Microsoft Teams.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Conduct End-to-End Testing of IT Support Scenarios
- Task 2: Verify Email Notifications and Flow Execution
- Task 3: Test Edge Cases and Error Handling
- Task 4: Publish the Copilot to Microsoft Teams
- Task 5: Test the Copilot in Microsoft Teams

### Task 1: Conduct End-to-End Testing of IT Support Scenarios

In this task, you will systematically test all IT support scenarios to ensure the copilot works correctly.

1. In Microsoft Copilot Studio, open your **IT Support Copilot**.

   ![](./media/ex10-open-copilot.png)

1. Click the **Test** button to open the test panel on the right side.

   ![](./media/ex10-test-panel.png)

1. **Test Scenario 1 - Password Reset Query (Knowledge Base):**

   **Prompt:**
   ```
   I forgot my password and I'm locked out
   ```

   ![](./media/ex10-test-password.png)

   **Expected Results:**
   - The copilot should provide password reset instructions from the knowledge base
   - Should mention self-service password reset options
   - Should offer to create a ticket if needed

   **Verification Checklist:**
   - [ ] Response references knowledge base content
   - [ ] Provides clear step-by-step instructions
   - [ ] Offers escalation option

   ![](./media/ex10-password-result.png)

1. **Test Scenario 2 - VPN Connectivity (Knowledge Base):**

   Click the **Reset** button to start fresh.

   **Prompt:**
   ```
   My VPN keeps disconnecting every few minutes
   ```

   ![](./media/ex10-test-vpn.png)

   **Expected Results:**
   - Copilot provides VPN troubleshooting steps from knowledge base
   - Asks clarifying questions if needed
   - Offers to create a support ticket

   ![](./media/ex10-vpn-result.png)

1. **Test Scenario 3 - Full Ticket Creation Flow:**

   Reset the conversation.

   **Prompt:**
   ```
   I need to submit an IT support ticket
   ```

   ![](./media/ex10-test-ticket.png)

   Follow the conversation and provide:
   - **Category:** Hardware
   - **Description:** My laptop screen is flickering and sometimes goes black for a few seconds
   - **Urgency:** Medium
   - **Phone:** 555-123-4567

   ![](./media/ex10-ticket-flow.png)

   **Expected Results:**
   - All questions are asked in order
   - Variables are captured correctly
   - Flow is triggered (check flow run history)
   - Confirmation message is displayed
   - Category-specific troubleshooting is provided

   ![](./media/ex10-ticket-result.png)

1. **Test Scenario 4 - Critical Ticket (Escalation Path):**

   Reset the conversation.

   **Prompt:**
   ```
   Submit a ticket
   ```

   Provide:
   - **Category:** Network
   - **Description:** The entire office has lost internet connectivity. Nobody can work.
   - **Urgency:** Critical
   - **Phone:** 555-999-0000

   ![](./media/ex10-test-critical.png)

   **Expected Results:**
   - Critical urgency is recognized
   - Immediate escalation is triggered
   - Urgent email notification is sent

   ![](./media/ex10-critical-result.png)

1. **Test Scenario 5 - Escalation Request:**

   Reset the conversation.

   **Prompt:**
   ```
   I need to escalate my issue, it's still not resolved
   ```

   ![](./media/ex10-test-escalate.png)

   **Expected Results:**
   - Escalation topic is triggered
   - Questions about ticket ID and reason are asked
   - Escalation flow is executed
   - Confirmation message is displayed

   ![](./media/ex10-escalate-result.png)

1. Document any issues found during testing in the table below:

   | Test Scenario | Status | Issues Found | Resolution |
   |---------------|--------|--------------|------------|
   | Password Reset | ☐ Pass / ☐ Fail | | |
   | VPN Issues | ☐ Pass / ☐ Fail | | |
   | Ticket Creation | ☐ Pass / ☐ Fail | | |
   | Critical Ticket | ☐ Pass / ☐ Fail | | |
   | Escalation | ☐ Pass / ☐ Fail | | |

### Task 2: Verify Email Notifications and Flow Execution

In this task, you will verify that the Power Automate flows are executing correctly.

1. Open a new browser tab and navigate to:

   ```
   https://make.powerautomate.com
   ```

   ![](./media/ex10-power-automate.png)

1. Sign in with your lab credentials if prompted.

1. Click on **My flows** in the left navigation.

   ![](./media/ex10-my-flows.png)

1. Find the **IT Ticket Notification Flow** and click on it.

   ![](./media/ex10-select-flow.png)

1. Review the **Run history** to see recent executions.

   ![](./media/ex10-run-history.png)

1. Click on a recent run to see the execution details:

   - Verify all steps completed successfully (green checkmarks)
   - Check the input values passed from Copilot
   - Verify the email was sent

   ![](./media/ex10-flow-details.png)

1. Similarly, check the **IT Escalation Flow** run history.

   ![](./media/ex10-escalation-history.png)

1. Open a new tab and navigate to Outlook:

   ```
   https://outlook.office.com
   ```

   ![](./media/ex10-outlook.png)

1. Check your inbox for the notification emails:

   - Standard ticket notifications
   - Critical ticket notifications (with 🚨 emoji)
   - Escalation alerts (with ⚡ emoji)

   ![](./media/ex10-email-inbox.png)

1. Verify email content:

   - Ticket details are correctly populated
   - Category, urgency, and description match what was submitted
   - Contact phone number is included

   ![](./media/ex10-email-content.png)

### Task 3: Test Edge Cases and Error Handling

In this task, you will test how the copilot handles unexpected inputs and edge cases.

1. Return to Copilot Studio and open the test panel.

1. **Edge Case 1 - Off-Topic Question:**

   **Prompt:**
   ```
   What's the weather like today?
   ```

   ![](./media/ex10-test-weather.png)

   **Expected:** The copilot should politely redirect to IT support topics or indicate it cannot help with that request.

   ![](./media/ex10-weather-result.png)

1. **Edge Case 2 - Vague Request:**

   **Prompt:**
   ```
   Something is wrong
   ```

   ![](./media/ex10-test-vague.png)

   **Expected:** The copilot should ask clarifying questions to understand the issue.

   ![](./media/ex10-vague-result.png)

1. **Edge Case 3 - Multiple Issues:**

   **Prompt:**
   ```
   My email isn't working and my printer is jammed and my computer is slow
   ```

   ![](./media/ex10-test-multiple.png)

   **Expected:** The copilot should acknowledge multiple issues and either address them one at a time or ask which is most urgent.

   ![](./media/ex10-multiple-result.png)

1. **Edge Case 4 - Angry/Frustrated User:**

   **Prompt:**
   ```
   This is ridiculous! Nothing ever works around here and IT never helps!
   ```

   ![](./media/ex10-test-frustrated.png)

   **Expected:** The copilot should respond empathetically and professionally, then attempt to help.

   ![](./media/ex10-frustrated-result.png)

1. Review the test results. If any edge cases are not handled well, you can:

   - Add new topics to handle specific scenarios
   - Modify instructions to improve responses
   - Add fallback topic configurations

   ![](./media/ex10-review-tests.png)

### Task 4: Publish the Copilot to Microsoft Teams

In this task, you will publish the IT Support Copilot and make it available in Microsoft Teams.

1. In Copilot Studio, click **Publish** in the top menu bar.

   ![](./media/ex10-publish-button.png)

1. Review the publishing checklist:

   - ✅ All topics are saved
   - ✅ Flows are connected and working
   - ✅ Knowledge base is synced
   - ✅ Testing is complete

   ![](./media/ex10-publish-checklist.png)

1. Click **Publish** to publish your copilot.

   ![](./media/ex10-confirm-publish.png)

1. Wait for the publishing process to complete. You should see a success message.

   ![](./media/ex10-publish-success.png)

1. Click on **Channels** in the left navigation.

   ![](./media/ex10-channels.png)

1. Find **Microsoft Teams** and click on it.

   ![](./media/ex10-teams-channel.png)

1. Click **Turn on Teams** to enable the Teams channel.

   ![](./media/ex10-turn-on-teams.png)

1. Configure the Teams settings:

   | Setting | Value |
   |---------|-------|
   | Display name | `IT Support Copilot` |
   | Short description | `AI-powered IT support assistant` |
   | Long description | `Get instant help with IT issues including password resets, VPN problems, laptop performance, and more.` |

   ![](./media/ex10-teams-settings.png)

1. Click **Save** to save the Teams configuration.

1. Click **Open the app in Teams** or **Add to Teams** to install the bot in Teams.

   ![](./media/ex10-add-to-teams.png)

   >**Note:** If prompted about permissions, click **Allow** or **Add**.

### Task 5: Test the Copilot in Microsoft Teams

In this task, you will test the copilot directly within Microsoft Teams.

1. Microsoft Teams should open with your IT Support Copilot. If not, search for "IT Support Copilot" in Teams.

   ![](./media/ex10-teams-copilot.png)

1. Start a conversation with the copilot:

   **Prompt:**
   ```
   Hi, I need help with an IT issue
   ```

   ![](./media/ex10-teams-hello.png)

   **Expected:** The copilot should respond and offer to help.

   ![](./media/ex10-teams-response.png)

1. **Test 1 - Knowledge Base Query in Teams:**

   **Prompt:**
   ```
   How do I reset my password?
   ```

   ![](./media/ex10-teams-password.png)

   **Expected:** The copilot should provide password reset instructions from the knowledge base.

   ![](./media/ex10-teams-password-result.png)

1. **Test 2 - Create Ticket in Teams:**

   **Prompt:**
   ```
   I need to submit a support ticket
   ```

   ![](./media/ex10-teams-ticket.png)

   Follow the conversation flow and verify:
   - All questions are asked correctly
   - Responses are captured
   - Confirmation is provided
   - Email notification is received

   ![](./media/ex10-teams-ticket-complete.png)

1. **Test 3 - Verify Adaptive Cards (if applicable):**

   Some responses may include rich adaptive cards with buttons and formatting.

   ![](./media/ex10-teams-cards.png)

1. Verify the copilot is working correctly in Teams:

   | Feature | Teams Test Status |
   |---------|------------------|
   | Basic conversation | ☐ Working |
   | Knowledge base queries | ☐ Working |
   | Ticket creation | ☐ Working |
   | Flow execution | ☐ Working |
   | Email notifications | ☐ Working |

1. (Optional) Share the copilot with your team:

   - In Teams, right-click on the IT Support Copilot
   - Select **Share** or **Get link**
   - Share with colleagues for broader testing

   ![](./media/ex10-share-copilot.png)

## Summary

In this exercise, you completed the full lifecycle of building and deploying an IT Support Copilot. You learned how to:

- Conduct comprehensive end-to-end testing of all scenarios
- Verify Power Automate flow execution and email notifications
- Test edge cases and error handling for robust user experience
- Publish a copilot and enable the Microsoft Teams channel
- Test the copilot directly within Microsoft Teams
- Validate that all integrations work seamlessly in the production environment

Your IT Support Copilot is now live in Microsoft Teams, ready to help employees with:
- ✅ Password reset and account access issues
- ✅ VPN and network connectivity problems
- ✅ Laptop performance troubleshooting
- ✅ Printer and hardware issues
- ✅ Automatic ticket creation and notifications
- ✅ Critical issue escalation

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
