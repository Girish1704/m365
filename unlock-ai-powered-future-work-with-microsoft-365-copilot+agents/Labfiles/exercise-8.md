# Exercise 8: Build an Autonomous Agent and Implement Agent Flows to Streamline IT Support Operations Using Copilot Studio

## Estimated Duration: 120 Minutes

## Overview

In this exercise, you will build an autonomous agent using Microsoft Copilot Studio that can independently handle IT support tasks. You will also implement agent flows using Power Automate to create automated workflows that streamline IT support operations.

Autonomous agents can proactively take actions, trigger workflows, and complete tasks without constant human intervention, making them ideal for IT support scenarios like ticket triage, automated responses, and escalation management.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create an IT Support Autonomous Agent
- Task 2: Configure autonomous agent capabilities
- Task 3: Build an agent flow for ticket categorization
- Task 4: Create an escalation flow for critical issues
- Task 5: Implement automated response workflows
- Task 6: Test the autonomous agent and flows

### Task 1: Create an IT Support Autonomous Agent

In this task, you will create an autonomous agent designed for IT support operations.

1. In the VM, open **Microsoft Edge** browser and navigate to:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex8-studio-url.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex8-signin.png)

1. On the Copilot Studio home page, click **+ Create** from the left navigation.

   ![](./media/ex8-create.png)

1. Select **New agent**.

   ![](./media/ex8-new-agent.png)

1. In the **Describe your agent** field, enter a detailed description:

   **Agent Description:**
   ```
   Create an autonomous IT support agent that can:
   - Automatically categorize incoming IT support requests
   - Provide immediate troubleshooting assistance
   - Escalate critical issues to appropriate teams
   - Track and update ticket status
   - Generate reports on common issues
   - Work independently to resolve routine problems
   - Trigger automated workflows for repetitive tasks
   
   The agent should be efficient, accurate, and capable of handling high volumes of requests with minimal human intervention.
   ```

   ![](./media/ex8-agent-description.png)

1. Click **Create** to generate the agent.

1. Once created, configure the agent settings:

   - Click **Settings** from the top menu
   - Update the following:

   | Field | Value |
   |-------|-------|
   | Name | `IT Support Automator-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `An autonomous agent that handles IT support tickets, automates responses, and streamlines support operations` |

   ![](./media/ex8-agent-settings.png)

1. Click **Save** to save the settings.

### Task 2: Configure Autonomous Agent Capabilities

In this task, you will configure the agent's autonomous capabilities and behaviors.

1. In the agent editor, click on **Topics** in the left navigation.

   ![](./media/ex8-topics.png)

1. Click **+ New topic** > **From blank** to create the main ticket intake topic.

1. Name the topic `New Ticket Intake` and add trigger phrases:

   ```
   I need IT help
   My computer is not working
   IT support request
   Technical issue
   System problem
   Help with technology
   Submit a ticket
   Report an issue
   ```

   ![](./media/ex8-intake-triggers.png)

1. Build the conversation flow to collect ticket information:

   **Step 1 - Greeting Message:**
   
   Add a **Message** node:
   ```
   Welcome to IT Support! I'm an automated assistant that can help resolve your technical issues quickly. Let me collect some information about your problem.
   ```

   ![](./media/ex8-greeting-message.png)

1. **Step 2 - Collect Issue Category:**

   Add a **Question** node:
   - Question text: `What category best describes your issue?`
   - Identify: Multiple choice options
   - Options:
     - Hardware (Computer, Monitor, Keyboard, Mouse)
     - Software (Applications, Operating System)
     - Network (Internet, VPN, WiFi)
     - Email (Outlook, Calendar)
     - Account Access (Password, Permissions)
     - Other

   - Save response as: `IssueCategory`

   ![](./media/ex8-category-question.png)

1. **Step 3 - Collect Issue Description:**

   Add a **Question** node:
   - Question text: `Please describe the issue in detail. Include any error messages you see.`
   - Identify: User's entire response
   - Save response as: `IssueDescription`

   ![](./media/ex8-description-question.png)

1. **Step 4 - Collect Urgency Level:**

   Add a **Question** node:
   - Question text: `How urgent is this issue?`
   - Identify: Multiple choice options
   - Options:
     - Critical - Work completely stopped
     - High - Major impact on work
     - Medium - Some impact on productivity
     - Low - Minor inconvenience

   - Save response as: `UrgencyLevel`

   ![](./media/ex8-urgency-question.png)

1. **Step 5 - Collect Contact Information:**

   Add a **Question** node:
   - Question text: `What is the best phone number to reach you if needed?`
   - Identify: Phone number
   - Save response as: `ContactPhone`

   ![](./media/ex8-phone-question.png)

1. Click **Save** to save the topic.

### Task 3: Build an Agent Flow for Ticket Categorization

In this task, you will create a Power Automate flow that automatically categorizes and routes tickets.

1. In the agent editor, click on **Actions** in the left navigation.

   ![](./media/ex8-actions.png)

1. Click **+ Add an action**.

   ![](./media/ex8-add-action.png)

1. Select **Create a new flow**.

   ![](./media/ex8-create-flow.png)

1. Power Automate will open. Name the flow:

   ```
   IT Ticket Categorization Flow
   ```

   ![](./media/ex8-flow-name.png)

1. The flow should have a trigger **Run a flow from Copilot**. Configure the input parameters:

   - Click **+ Add an input**
   - Add the following inputs:

   | Input Name | Type |
   |------------|------|
   | IssueCategory | Text |
   | IssueDescription | Text |
   | UrgencyLevel | Text |
   | ContactPhone | Text |

   ![](./media/ex8-flow-inputs.png)

1. Add a **Compose** action to create the ticket object:

   - Click **+ New step**
   - Search for and select **Compose**
   - Configure:

   ```json
   {
     "TicketID": "@{guid()}",
     "Category": "@{triggerBody()?['text']}",
     "Description": "@{triggerBody()?['text_1']}",
     "Urgency": "@{triggerBody()?['text_2']}",
     "Contact": "@{triggerBody()?['text_3']}",
     "Status": "Open",
     "CreatedDate": "@{utcNow()}",
     "AssignedTeam": "Pending"
   }
   ```

   ![](./media/ex8-compose-ticket.png)

1. Add a **Condition** to check urgency level:

   - Click **+ New step**
   - Search for and select **Condition**
   - Configure:
     - Left value: `UrgencyLevel`
     - Operator: `is equal to`
     - Right value: `Critical - Work completely stopped`

   ![](./media/ex8-urgency-condition.png)

1. In the **If yes** branch, add actions for critical tickets:

   **Action 1 - Send urgent notification email:**
   
   - Click **Add an action** in the Yes branch
   - Search for **Office 365 Outlook** > **Send an email (V2)**
   - Configure:
     - To: <inject key="AzureAdUserEmail"></inject>
     - Subject: `CRITICAL IT TICKET - Immediate Action Required`
     - Body:
     ```
     A critical IT support ticket has been submitted:
     
     Category: @{triggerBody()?['text']}
     Description: @{triggerBody()?['text_1']}
     Contact Phone: @{triggerBody()?['text_3']}
     
     Please respond immediately.
     ```

   ![](./media/ex8-urgent-email.png)

1. In the **If no** branch, add actions for non-critical tickets:

   **Action - Send standard notification:**
   
   - Click **Add an action** in the No branch
   - Search for **Office 365 Outlook** > **Send an email (V2)**
   - Configure:
     - To: <inject key="AzureAdUserEmail"></inject>
     - Subject: `New IT Support Ticket - @{triggerBody()?['text']}`
     - Body:
     ```
     A new IT support ticket has been submitted:
     
     Category: @{triggerBody()?['text']}
     Urgency: @{triggerBody()?['text_2']}
     Description: @{triggerBody()?['text_1']}
     Contact Phone: @{triggerBody()?['text_3']}
     
     The ticket has been added to the queue.
     ```

   ![](./media/ex8-standard-email.png)

1. Add a **Respond to Copilot** action after the condition:

   - Click **+ New step** after the condition block
   - Search for **Respond to Copilot**
   - Add an output:
     - Name: `TicketConfirmation`
     - Value: `Your ticket has been created and categorized. Ticket reference number is provided in the confirmation email.`

   ![](./media/ex8-respond-copilot.png)

1. Click **Save** to save the flow.

   ![](./media/ex8-save-flow.png)

1. Return to Copilot Studio and refresh the actions list.

   ![](./media/ex8-refresh-actions.png)

### Task 4: Create an Escalation Flow for Critical Issues

In this task, you will create a separate flow for handling escalations.

1. In the agent editor, click **Actions** > **+ Add an action** > **Create a new flow**.

1. Name the flow:

   ```
   IT Escalation Flow
   ```

   ![](./media/ex8-escalation-flow-name.png)

1. Configure the trigger with inputs:

   | Input Name | Type |
   |------------|------|
   | TicketID | Text |
   | EscalationReason | Text |
   | OriginalCategory | Text |

   ![](./media/ex8-escalation-inputs.png)

1. Add actions for the escalation:

   **Action 1 - Send Teams notification:**
   
   - Click **+ New step**
   - Search for **Microsoft Teams** > **Post message in a chat or channel**
   - Configure:
     - Post as: Flow bot
     - Post in: Channel
     - Team: Select your team (or skip if not available)
     - Channel: Select appropriate channel
     - Message:
     ```
     **ESCALATION ALERT**
     
     Ticket ID: @{triggerBody()?['text']}
     Original Category: @{triggerBody()?['text_2']}
     Escalation Reason: @{triggerBody()?['text_1']}
     
     Please review and take immediate action.
     ```

   >**Note:** If Teams posting is not available, use email notification instead.

   ![](./media/ex8-teams-notification.png)

1. **Action 2 - Send escalation email:**
   
   - Search for **Office 365 Outlook** > **Send an email (V2)**
   - Configure:
     - To: <inject key="AzureAdUserEmail"></inject>
     - Subject: `ESCALATION - IT Ticket @{triggerBody()?['text']}`
     - Body:
     ```
     An IT ticket has been escalated:
     
     Ticket ID: @{triggerBody()?['text']}
     Original Category: @{triggerBody()?['text_2']}
     Escalation Reason: @{triggerBody()?['text_1']}
     
     This ticket requires immediate attention from a senior technician.
     ```

   ![](./media/ex8-escalation-email.png)

1. Add **Respond to Copilot** action:

   - Name: `EscalationConfirmation`
   - Value: `Your issue has been escalated to a senior technician. You will be contacted within 15 minutes.`

   ![](./media/ex8-escalation-respond.png)

1. Click **Save** to save the flow.

### Task 5: Implement Automated Response Workflows

In this task, you will configure the agent to use the flows and provide automated responses.

1. Return to Copilot Studio and open the **New Ticket Intake** topic.

   ![](./media/ex8-open-intake.png)

1. After collecting all information, add a **Call an action** node:

   - Click **+ Add node** > **Call an action**
   - Select the **IT Ticket Categorization Flow**

   ![](./media/ex8-call-action.png)

1. Map the flow inputs to the variables collected:

   - IssueCategory: `IssueCategory`
   - IssueDescription: `IssueDescription`
   - UrgencyLevel: `UrgencyLevel`
   - ContactPhone: `ContactPhone`

   ![](./media/ex8-map-inputs.png)

1. Add a **Message** node after the flow call to confirm the ticket:

   ```
   Your IT support ticket has been created and is being processed.

   Category: {IssueCategory}
   Urgency: {UrgencyLevel}

   Based on your issue, here are some immediate troubleshooting steps you can try while we process your ticket:
   ```

   ![](./media/ex8-confirmation-message.png)

1. Add **Condition** nodes to provide category-specific troubleshooting:

   **Condition 1 - Hardware Issues:**
   
   - If `IssueCategory` equals "Hardware (Computer, Monitor, Keyboard, Mouse)"
   - Add message:
   ```
   Hardware Troubleshooting Steps:
   1. Check all cable connections
   2. Try restarting the device
   3. Check if the issue occurs with other devices
   4. Look for any physical damage
   
   If the problem persists, a technician will contact you.
   ```

   ![](./media/ex8-hardware-condition.png)

   **Condition 2 - Network Issues:**
   
   - If `IssueCategory` equals "Network (Internet, VPN, WiFi)"
   - Add message:
   ```
   Network Troubleshooting Steps:
   1. Check if other devices can connect
   2. Restart your router/modem
   3. Try disconnecting and reconnecting to WiFi
   4. If using VPN, try reconnecting
   
   If the problem persists, our network team will investigate.
   ```

   ![](./media/ex8-network-condition.png)

   **Condition 3 - Account Access:**
   
   - If `IssueCategory` equals "Account Access (Password, Permissions)"
   - Add message:
   ```
   Account Access Quick Help:
   1. Try the self-service password reset at https://passwordreset.microsoftonline.com
   2. Clear your browser cache and cookies
   3. Try accessing from a different browser
   
   For permission issues, your request has been forwarded to the access management team.
   ```

   ![](./media/ex8-account-condition.png)

1. Create a new topic for **Escalation Request**:

   - Name: `Request Escalation`
   - Trigger phrases:
     ```
     I need to escalate
     This is urgent
     Speak to a manager
     My issue is not resolved
     Need immediate help
     Escalate my ticket
     ```

   ![](./media/ex8-escalation-topic.png)

1. Build the escalation conversation:

   - Add question to get ticket ID or describe original issue
   - Add question to get escalation reason
   - Call the **IT Escalation Flow**
   - Provide confirmation message

   ![](./media/ex8-escalation-flow-call.png)

1. Click **Save** to save all changes.

### Task 6: Test the Autonomous Agent and Flows

In this task, you will test the complete autonomous agent with its integrated flows.

1. Click the **Test** button to open the test panel.

   ![](./media/ex8-test-button.png)

1. **Test 1 - Standard Ticket Creation:**

   **Prompt:**
   ```
   I need IT help
   ```

   ![](./media/ex8-test-start.png)

   **Expected Flow:**

   The agent should ask for category, description, urgency, and contact:

   ![](./media/ex8-test-category.png)

1. Continue the conversation:

   - Select: `Network (Internet, VPN, WiFi)`
   - Description: `My VPN keeps disconnecting every few minutes. I cannot maintain a stable connection to work remotely.`
   - Urgency: `High - Major impact on work`
   - Phone: `555-123-4567`

   ![](./media/ex8-test-complete.png)

   **Expected Output:**

   The agent should:
   - Confirm ticket creation
   - Provide network troubleshooting steps
   - Trigger the categorization flow (check your email)

   ![](./media/ex8-test-result.png)

1. **Test 2 - Critical Issue:**

   Start a new conversation:

   **Prompt:**
   ```
   Submit a ticket
   ```

   Provide information:
   - Category: `Hardware (Computer, Monitor, Keyboard, Mouse)`
   - Description: `Multiple computers in the finance department are completely non-functional. Team cannot process payroll.`
   - Urgency: `Critical - Work completely stopped`
   - Phone: `555-999-1111`

   ![](./media/ex8-test-critical.png)

   **Expected Output:**

   The agent should:
   - Recognize the critical urgency
   - Trigger immediate escalation
   - Send urgent notification email

   ![](./media/ex8-critical-result.png)

1. **Test 3 - Escalation Request:**

   **Prompt:**
   ```
   I need to escalate my issue
   ```

   ![](./media/ex8-test-escalate.png)

   **Expected Output:**

   The agent should collect escalation details and trigger the escalation flow:

   ![](./media/ex8-escalate-result.png)

1. **Test 4 - Check Email Notifications:**

   Open a new browser tab and go to:

   ```
   https://outlook.office.com
   ```

   ![](./media/ex8-check-email.png)

   Verify that you received:
   - Ticket creation notifications
   - Escalation notifications (if triggered)

   ![](./media/ex8-email-received.png)

1. Once all tests pass, click **Publish** to publish the agent.

   ![](./media/ex8-publish.png)

1. Select the channels for publishing and confirm.

   ![](./media/ex8-publish-confirm.png)

## Summary

In this exercise, you built an autonomous IT Support agent using Microsoft Copilot Studio. You learned how to:

- Create an autonomous agent for IT support operations
- Configure intelligent ticket intake and categorization
- Build Power Automate flows for automated processing
- Implement escalation workflows for critical issues
- Provide context-aware automated troubleshooting responses
- Test and validate the complete autonomous system

Autonomous agents with integrated flows can significantly reduce IT support workload by handling routine tasks automatically while ensuring critical issues are escalated appropriately.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
