# Exercise 9: Build Agent Flows and Topics to Automate IT Support Ticket Processing

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will enhance the IT Support Copilot created in the previous exercise by building intelligent topics and automated workflows using Power Automate. You will create a ticket intake topic that collects issue details, build agent flows for automatic ticket categorization and escalation, and integrate these components for seamless automation.

By the end of this exercise, your IT Support Copilot will be able to automatically process support requests, categorize them, send notifications, and escalate critical issues—all without human intervention.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create a Ticket Intake Topic with Generative AI
- Task 2: Build a Power Automate Flow for Ticket Notifications
- Task 3: Create an Escalation Flow for Critical Issues
- Task 4: Connect Flows to the Agent Topics
- Task 5: Add Automated Troubleshooting Responses

### Task 1: Create a Ticket Intake Topic with Generative AI

In this task, you will create a topic that uses generative AI to collect and understand IT support requests.

1. In Microsoft Copilot Studio, open the **IT Support Copilot** you created in the previous exercise.

   ![](./media/ex9-open-agent.png)

1. Click on **Topics** in the left navigation panel.

   ![](./media/ex9-topics-nav.png)

1. Click **+ Add a topic** and select **Create from description with Copilot**.

   ![](./media/ex9-add-topic.png)

1. In the **Describe what the topic does** field, enter the following description:

   ```
   Create a topic that handles IT support ticket submission. The topic should:
   - Greet users and explain that it will help create a support ticket
   - Ask what category their issue belongs to (Hardware, Software, Network, Email, Account Access, or Other)
   - Ask for a detailed description of the problem
   - Ask about the urgency level (Critical, High, Medium, or Low)
   - Ask for the best phone number to reach them
   - Confirm the ticket details before submission
   ```

   ![](./media/ex9-topic-description.png)

1. Click **Create** to generate the topic using AI.

   ![](./media/ex9-create-topic.png)

1. Once the topic is generated, review the conversation flow. The AI will have created:
   - A greeting message
   - Questions for category, description, urgency, and contact
   - Variable assignments for each response

   ![](./media/ex9-generated-topic.png)

1. Click on the topic name at the top and rename it to:

   ```
   New Ticket Intake
   ```

   ![](./media/ex9-rename-topic.png)

1. Add additional trigger phrases by clicking on the **Trigger phrases** section:

   ```
   I need IT help
   My computer is not working
   IT support request
   Technical issue
   System problem
   Help with technology
   Submit a ticket
   Report an issue
   Create support ticket
   I have a problem
   ```

   ![](./media/ex9-trigger-phrases.png)

1. Click **Save** to save the topic.

   ![](./media/ex9-save-topic.png)

### Task 2: Build a Power Automate Flow for Ticket Notifications

In this task, you will create a Power Automate flow that sends email notifications when tickets are created.

1. In the agent editor, click on **Actions** in the left navigation.

   ![](./media/ex9-actions-nav.png)

1. Click **+ Add an action**.

   ![](./media/ex9-add-action.png)

1. Select **Create a new flow** to open Power Automate.

   ![](./media/ex9-create-flow.png)

   >**Note:** Power Automate will open in a new tab. Make sure to allow pop-ups if blocked.

1. In Power Automate, you will see a flow template with a Copilot trigger. Name the flow:

   ```
   IT Ticket Notification Flow
   ```

   ![](./media/ex9-flow-name.png)

1. Click on the **Run a flow from Copilot** trigger to configure inputs. Click **+ Add an input** and add the following inputs:

   | Input Name | Type | Description |
   |------------|------|-------------|
   | IssueCategory | Text | The category of the IT issue |
   | IssueDescription | Text | Detailed description of the problem |
   | UrgencyLevel | Text | How urgent the issue is |
   | ContactPhone | Text | Phone number to reach the user |

   ![](./media/ex9-flow-inputs.png)

1. Click **+ New step** and search for **Compose**. Select the **Compose** action.

   ![](./media/ex9-add-compose.png)

1. In the **Inputs** field, enter the following JSON to create a ticket object:

   ```json
   {
     "TicketID": "@{guid()}",
     "Category": "@{triggerBody()?['text']}",
     "Description": "@{triggerBody()?['text_1']}",
     "Urgency": "@{triggerBody()?['text_2']}",
     "Contact": "@{triggerBody()?['text_3']}",
     "Status": "Open",
     "CreatedDate": "@{utcNow()}"
   }
   ```

   ![](./media/ex9-compose-json.png)

1. Click **+ New step** and search for **Condition**. Select the **Condition** control.

   ![](./media/ex9-add-condition.png)

1. Configure the condition to check if the issue is critical:

   - Click in the first field and select `UrgencyLevel` from the Dynamic content
   - Set the operator to **is equal to**
   - Enter `Critical` in the value field

   ![](./media/ex9-condition-config.png)

1. In the **If yes** branch (for critical issues), click **Add an action**.

   - Search for **Office 365 Outlook**
   - Select **Send an email (V2)**

   ![](./media/ex9-add-email-critical.png)

1. Configure the critical email notification:

   | Field | Value |
   |-------|-------|
   | To | <inject key="AzureAdUserEmail"></inject> |
   | Subject | `🚨 CRITICAL IT TICKET - Immediate Action Required` |
   | Body | (See below) |

   **Email Body:**
   ```
   A CRITICAL IT support ticket has been submitted and requires immediate attention.

   TICKET DETAILS:
   ━━━━━━━━━━━━━━━━━━━━━━━━━━
   Category: @{triggerBody()?['text']}
   Urgency: @{triggerBody()?['text_2']}
   Contact Phone: @{triggerBody()?['text_3']}

   ISSUE DESCRIPTION:
   @{triggerBody()?['text_1']}

   ━━━━━━━━━━━━━━━━━━━━━━━━━━
   ⚠️ This ticket was automatically flagged as CRITICAL.
   Please respond within 15 minutes.
   ```

   ![](./media/ex9-critical-email-config.png)

1. In the **If no** branch (for non-critical issues), click **Add an action**.

   - Search for **Office 365 Outlook**
   - Select **Send an email (V2)**

   ![](./media/ex9-add-email-standard.png)

1. Configure the standard email notification:

   | Field | Value |
   |-------|-------|
   | To | <inject key="AzureAdUserEmail"></inject> |
   | Subject | `New IT Support Ticket - @{triggerBody()?['text']}` |
   | Body | (See below) |

   **Email Body:**
   ```
   A new IT support ticket has been submitted.

   TICKET DETAILS:
   ━━━━━━━━━━━━━━━━━━━━━━━━━━
   Category: @{triggerBody()?['text']}
   Urgency: @{triggerBody()?['text_2']}
   Contact Phone: @{triggerBody()?['text_3']}

   ISSUE DESCRIPTION:
   @{triggerBody()?['text_1']}

   ━━━━━━━━━━━━━━━━━━━━━━━━━━
   The ticket has been added to the support queue.
   ```

   ![](./media/ex9-standard-email-config.png)

1. After the condition block, click **+ New step** and search for **Respond to Copilot**.

   ![](./media/ex9-respond-copilot.png)

1. In the **Respond to Copilot** action, click **+ Add an output** and configure:

   | Field | Value |
   |-------|-------|
   | Type | Text |
   | Name | TicketConfirmation |
   | Value | Your ticket has been created successfully. You will receive a confirmation email shortly. |

   ![](./media/ex9-respond-config.png)

1. Click **Save** in the top right corner to save the flow.

   ![](./media/ex9-save-flow.png)

1. Close the Power Automate tab and return to Copilot Studio.

   ![](./media/ex9-return-copilot.png)

### Task 3: Create an Escalation Flow for Critical Issues

In this task, you will create a separate flow specifically for handling escalation requests.

1. In Copilot Studio, click on **Actions** > **+ Add an action** > **Create a new flow**.

   ![](./media/ex9-create-escalation-flow.png)

1. Name the flow:

   ```
   IT Escalation Flow
   ```

   ![](./media/ex9-escalation-name.png)

1. Configure the trigger inputs:

   | Input Name | Type |
   |------------|------|
   | TicketID | Text |
   | EscalationReason | Text |
   | OriginalCategory | Text |

   ![](./media/ex9-escalation-inputs.png)

1. Click **+ New step** and add **Send an email (V2)** from Office 365 Outlook:

   | Field | Value |
   |-------|-------|
   | To | <inject key="AzureAdUserEmail"></inject> |
   | Subject | `⚡ ESCALATION ALERT - Ticket @{triggerBody()?['text']}` |
   | Body | (See below) |

   **Email Body:**
   ```
   An IT support ticket has been ESCALATED.

   ESCALATION DETAILS:
   ━━━━━━━━━━━━━━━━━━━━━━━━━━
   Ticket ID: @{triggerBody()?['text']}
   Original Category: @{triggerBody()?['text_2']}
   
   ESCALATION REASON:
   @{triggerBody()?['text_1']}

   ━━━━━━━━━━━━━━━━━━━━━━━━━━
   ⚠️ This ticket requires immediate attention from a senior technician.
   Please respond within 15 minutes.
   ```

   ![](./media/ex9-escalation-email.png)

1. Click **+ New step** and add **Respond to Copilot**:

   | Field | Value |
   |-------|-------|
   | Type | Text |
   | Name | EscalationConfirmation |
   | Value | Your issue has been escalated to a senior technician. You will be contacted within 15 minutes. |

   ![](./media/ex9-escalation-respond.png)

1. Click **Save** and close the Power Automate tab.

### Task 4: Connect Flows to the Agent Topics

In this task, you will integrate the flows into your agent topics.

1. In Copilot Studio, go to **Topics** and open the **New Ticket Intake** topic.

   ![](./media/ex9-open-intake-topic.png)

1. Navigate to the end of the conversation flow (after all questions are asked).

1. Click **+** to add a new node, then select **Call an action**.

   ![](./media/ex9-add-action-node.png)

1. Select **IT Ticket Notification Flow** from the list of available actions.

   ![](./media/ex9-select-notification-flow.png)

1. Map the flow inputs to the topic variables:

   | Flow Input | Topic Variable |
   |------------|----------------|
   | IssueCategory | The variable storing category response |
   | IssueDescription | The variable storing description response |
   | UrgencyLevel | The variable storing urgency response |
   | ContactPhone | The variable storing phone response |

   ![](./media/ex9-map-variables.png)

   >**Note:** Variable names may differ based on how AI generated them. Match each input to the corresponding question's saved response.

1. After the action node, add a **Message** node with the confirmation:

   ```
   ✅ Your IT support ticket has been submitted successfully!

   Ticket Summary:
   • Category: {IssueCategory}
   • Urgency: {UrgencyLevel}

   You will receive a confirmation email shortly. A technician will review your request and contact you if needed.
   ```

   ![](./media/ex9-confirmation-message.png)

1. Click **Save** to save the topic.

1. Now create an **Escalation Request** topic. Click **+ Add a topic** > **Create from description with Copilot**.

1. Enter the description:

   ```
   Create a topic for users who want to escalate their IT issue. The topic should:
   - Ask if they have an existing ticket ID (optional)
   - Ask why they need to escalate (issue not resolved, taking too long, critical impact)
   - Ask what category the original issue was about
   - Confirm the escalation will be processed
   ```

   ![](./media/ex9-escalation-topic-desc.png)

1. Click **Create** and review the generated topic.

1. Rename the topic to `Request Escalation` and add trigger phrases:

   ```
   I need to escalate
   This is urgent
   Speak to a manager
   My issue is not resolved
   Need immediate help
   Escalate my ticket
   The problem is still not fixed
   I've been waiting too long
   ```

   ![](./media/ex9-escalation-triggers.png)

1. At the end of the escalation topic, add **Call an action** and select **IT Escalation Flow**.

1. Map the variables and add a confirmation message.

1. Click **Save** to save the topic.

### Task 5: Add Automated Troubleshooting Responses

In this task, you will add conditional troubleshooting guidance based on the issue category.

1. Return to the **New Ticket Intake** topic.

1. After the confirmation message, add a **Condition** node.

   - Click **+** > **Add a condition** > **Branch based on a condition**

   ![](./media/ex9-add-condition-node.png)

1. Configure the first condition:
   - Select the IssueCategory variable
   - Set to **is equal to**
   - Value: `Hardware`

   ![](./media/ex9-hardware-condition.png)

1. In the Hardware branch, add a **Message** node:

   ```
   💡 While we process your hardware issue, try these quick fixes:

   1. Check all cable connections
   2. Restart your computer
   3. Check if the issue occurs with other devices
   4. Look for any physical damage

   If these don't help, a technician will contact you soon.
   ```

   ![](./media/ex9-hardware-message.png)

1. Click **+ New condition** to add another branch for Network issues:

   - Condition: IssueCategory **is equal to** `Network`
   - Message:
   ```
   💡 While we process your network issue, try these quick fixes:

   1. Check if other devices can connect
   2. Restart your router/modem
   3. Disconnect and reconnect to WiFi
   4. Try using an ethernet cable if possible

   Our network team will investigate if the issue persists.
   ```

   ![](./media/ex9-network-condition.png)

1. Add conditions for other categories as needed:

   **Software:**
   ```
   💡 While we process your software issue, try these quick fixes:

   1. Close and reopen the application
   2. Restart your computer
   3. Check for available updates
   4. Clear the application's cache

   A technician will review your request shortly.
   ```

   **Account Access:**
   ```
   💡 For account access issues, you can try:

   1. Self-service password reset: https://passwordreset.microsoftonline.com
   2. Clear browser cache and cookies
   3. Try a different browser
   4. Check if Caps Lock is on

   Your request has been forwarded to our access management team.
   ```

   ![](./media/ex9-other-conditions.png)

1. Add a **Default** branch for other categories with a generic message:

   ```
   A technician will review your request and contact you shortly. Thank you for your patience.
   ```

   ![](./media/ex9-default-message.png)

1. Click **Save** to save all changes.

   ![](./media/ex9-final-save.png)

## Summary

In this exercise, you enhanced the IT Support Copilot with intelligent automation capabilities. You learned how to:

- Create topics using generative AI to quickly build conversation flows
- Build Power Automate flows that integrate with Copilot for automated processing
- Create escalation workflows for critical issues
- Connect flows to agent topics with proper variable mapping
- Add conditional logic for category-specific troubleshooting guidance

Your IT Support Copilot can now automatically collect issue details, categorize tickets, send notifications, escalate critical issues, and provide immediate troubleshooting guidance—all without human intervention.

In the next exercise, you will test the complete solution and deploy it to Microsoft Teams.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
