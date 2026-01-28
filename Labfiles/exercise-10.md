# Exercise 10: Implement Agent Flows to Streamline IT Support Operations

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will implement agent flows using Microsoft Copilot Studio to streamline IT support operations. Agent flows combine the conversational capabilities of agents with the automation power of Power Automate, enabling intelligent ticket routing, automated troubleshooting, and seamless escalation to human agents.

You will build an IT Support agent that can handle common IT issues, automatically create and route support tickets, and provide self-service solutions to employees.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Design the IT Support workflow
- Task 2: Create the IT Support agent
- Task 3: Build intelligent ticket routing flow
- Task 4: Implement automated troubleshooting
- Task 5: Configure escalation and handoff

### Task 1: Design the IT Support Workflow

In this task, you will plan the IT support workflow before building.

1. Open Microsoft Copilot Studio at `https://copilotstudio.microsoft.com`.

   ![](./media/ex10-copilot-studio.png)

1. Before building, design the IT support workflow:

   ```
   IT SUPPORT WORKFLOW DESIGN

   USER INITIATES SUPPORT REQUEST
            ↓
   AGENT GATHERS INFORMATION
   - Issue category
   - Description
   - Urgency level
   - User details
            ↓
   AUTOMATED TRIAGE
   - Common issues → Self-service solutions
   - Complex issues → Create ticket
   - Critical issues → Immediate escalation
            ↓
   TICKET CREATION & ROUTING
   - Create ticket in IT system
   - Route to appropriate team
   - Set priority based on urgency
            ↓
   FOLLOW-UP & RESOLUTION
   - Monitor ticket status
   - Update user on progress
   - Collect satisfaction feedback
   ```

   ![](./media/ex10-workflow-design.png)

1. Define the issue categories for routing:

   | Category | Description | Routing |
   |----------|-------------|---------|
   | Password Reset | Account access issues | Self-service + Auto-reset |
   | Hardware | Physical equipment issues | Hardware Team |
   | Software | Application problems | Software Team |
   | Network | Connectivity issues | Network Team |
   | Security | Security concerns | Security Team (High Priority) |
   | Access Request | Permission requests | Access Management Team |

   ![](./media/ex10-categories.png)

1. Define priority levels:

   | Priority | Response Time | Criteria |
   |----------|---------------|----------|
   | Critical | 15 minutes | System down, security breach, executive impact |
   | High | 1 hour | Multiple users affected, key system degraded |
   | Medium | 4 hours | Single user, workaround available |
   | Low | 1 business day | Minor issues, enhancement requests |

   ![](./media/ex10-priorities.png)

### Task 2: Create the IT Support Agent

In this task, you will create the IT Support agent with comprehensive capabilities.

1. In Copilot Studio, click **+ Create** > **New copilot**.

   ![](./media/ex10-create-copilot.png)

1. Select **Create from description** and enter:

   ```
   Create an IT Support agent that helps employees with technology issues. The agent should:
   
   - Greet users and identify their IT problem
   - Categorize issues (password, hardware, software, network, security, access)
   - Provide self-service solutions for common problems
   - Create support tickets for complex issues
   - Route tickets to the appropriate IT team
   - Track and update users on ticket status
   - Escalate critical issues to human agents immediately
   - Collect satisfaction feedback after resolution
   ```

   ![](./media/ex10-agent-description.png)

1. Configure the agent settings:

   | Field | Value |
   |-------|-------|
   | Name | `IT Support Agent-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `Intelligent IT support assistant that helps employees resolve technology issues and manages support tickets` |

   ![](./media/ex10-agent-settings.png)

1. Click **Create** to generate the agent.

   ![](./media/ex10-create-button.png)

1. Once created, customize the agent's greeting message in **Topics**:

   ```
   Hello! 👋 I'm your IT Support assistant. I'm here to help you with any technology issues.

   I can help with:
   🔐 Password and account issues
   💻 Hardware problems
   📱 Software and applications
   🌐 Network and connectivity
   🔒 Security concerns
   🔑 Access requests

   What can I help you with today?
   ```

   ![](./media/ex10-greeting.png)

### Task 3: Build Intelligent Ticket Routing Flow

In this task, you will create flows that automatically route tickets to the appropriate team.

1. Navigate to **Topics** and create a new topic called `Create Support Ticket`.

   ![](./media/ex10-create-topic.png)

1. Define trigger phrases:

   ```
   I need to create a ticket
   Report an issue
   I have a problem
   Something is broken
   I need IT help
   Submit a support request
   Log an incident
   ```

   ![](./media/ex10-trigger-phrases.png)

1. Build the conversation flow to gather information:

   **Step 1: Issue Category**
   
   Add a **Question** node:
   ```
   I'd be happy to help you create a support ticket. First, let me understand your issue.

   What category best describes your problem?
   ```
   
   Options:
   - Password/Account Issues
   - Hardware Problem
   - Software/Application Issue
   - Network/Connectivity
   - Security Concern
   - Access Request
   - Other

   Save response as variable: `IssueCategory`

   ![](./media/ex10-category-question.png)

1. **Step 2: Issue Description**

   Add a **Question** node:
   ```
   Please describe your issue in detail. Include any error messages you've seen.
   ```

   Save response as variable: `IssueDescription`

   ![](./media/ex10-description-question.png)

1. **Step 3: Urgency Level**

   Add a **Question** node:
   ```
   How urgently do you need this resolved?
   ```

   Options:
   - Critical - I cannot work at all
   - High - Major impact on my work
   - Medium - I can work with limitations
   - Low - Minor inconvenience

   Save response as variable: `UrgencyLevel`

   ![](./media/ex10-urgency-question.png)

1. **Step 4: Create Ticket Action**

   Navigate to **Actions** and click **+ Add an action** > **Create a flow**.

   ![](./media/ex10-create-flow.png)

1. In Power Automate, build the ticket creation flow:

   **Flow Name:** `Create IT Support Ticket`

   **Inputs from Copilot:**
   - IssueCategory (Text)
   - IssueDescription (Text)
   - UrgencyLevel (Text)
   - UserEmail (Text)

   ![](./media/ex10-flow-inputs.png)

1. **Determine Routing Team** (Add a Compose or Switch action):

   ```
   Routing Logic:
   
   If IssueCategory = "Password/Account Issues" → Route to: Identity Team
   If IssueCategory = "Hardware Problem" → Route to: Hardware Support
   If IssueCategory = "Software/Application Issue" → Route to: Application Support
   If IssueCategory = "Network/Connectivity" → Route to: Network Team
   If IssueCategory = "Security Concern" → Route to: Security Team
   If IssueCategory = "Access Request" → Route to: Access Management
   Else → Route to: General IT Support
   ```

   ![](./media/ex10-routing-logic.png)

1. **Set Priority** based on urgency:

   ```
   If UrgencyLevel = "Critical" → Priority: 1
   If UrgencyLevel = "High" → Priority: 2
   If UrgencyLevel = "Medium" → Priority: 3
   If UrgencyLevel = "Low" → Priority: 4
   ```

   ![](./media/ex10-priority-logic.png)

1. **Create the Ticket** (Use SharePoint, Dataverse, or your ticketing system):

   For this lab, create a SharePoint list item:

   | Field | Value |
   |-------|-------|
   | Site | Your SharePoint site |
   | List | IT Support Tickets |
   | Title | `[Category] - [First 50 chars of description]` |
   | Description | IssueDescription |
   | Category | IssueCategory |
   | Priority | Calculated priority |
   | Assigned Team | Routing result |
   | Reported By | UserEmail |
   | Status | New |

   ![](./media/ex10-create-ticket-action.png)

1. **Send Confirmation Email**:

   Add Office 365 Outlook action:
   
   | Field | Value |
   |-------|-------|
   | To | UserEmail |
   | Subject | `IT Support Ticket Created - [Ticket ID]` |
   | Body | Confirmation with ticket details |

   ![](./media/ex10-send-confirmation.png)

1. **Return Ticket ID** to Copilot:

   Add output variable: TicketID

   ![](./media/ex10-return-output.png)

1. Save and return to Copilot Studio. Connect the flow to your topic.

   ![](./media/ex10-connect-flow.png)

1. Add a confirmation message after the flow:

   ```
   ✅ Your support ticket has been created successfully!

   📋 Ticket Number: {TicketID}
   📁 Category: {IssueCategory}
   ⚡ Priority: {UrgencyLevel}
   👥 Assigned to: {AssignedTeam}

   You'll receive a confirmation email shortly. Our team will respond based on the priority:
   - Critical: Within 15 minutes
   - High: Within 1 hour
   - Medium: Within 4 hours
   - Low: Within 1 business day

   Is there anything else I can help you with?
   ```

   ![](./media/ex10-confirmation-message.png)

### Task 4: Implement Automated Troubleshooting

In this task, you will add self-service troubleshooting for common issues.

1. Create a new topic: `Password Reset Self-Service`.

   ![](./media/ex10-password-topic.png)

1. Add trigger phrases:

   ```
   I forgot my password
   Reset my password
   Can't log in
   Account locked
   Password expired
   I need a new password
   ```

   ![](./media/ex10-password-triggers.png)

1. Build the troubleshooting flow:

   **Step 1: Identify the account type**
   ```
   I can help you with your password. Which account are you having trouble with?
   ```
   
   Options:
   - Windows/Computer login
   - Email/Microsoft 365
   - VPN
   - Application-specific
   - Other

   ![](./media/ex10-account-type.png)

1. **For Windows/M365 passwords**, provide self-service:

   ```
   For Windows and Microsoft 365 password resets, you can use self-service:

   🔐 SELF-SERVICE PASSWORD RESET:
   1. Go to https://passwordreset.microsoftonline.com
   2. Enter your work email address
   3. Complete the verification (phone or email)
   4. Create a new password

   ⚠️ PASSWORD REQUIREMENTS:
   - Minimum 12 characters
   - Include uppercase and lowercase letters
   - Include at least one number
   - Include at least one special character

   Were you able to reset your password successfully?
   ```

   ![](./media/ex10-self-service.png)

1. Add follow-up based on response:

   **If successful:**
   ```
   Great! I'm glad the self-service reset worked for you. 

   💡 TIP: Consider setting up additional verification methods in your security settings for easier future resets.

   Is there anything else I can help you with?
   ```

   **If unsuccessful:**
   ```
   I understand the self-service isn't working for you. Let me create a support ticket with our Identity team.

   This issue will be treated as High priority and someone will contact you within 1 hour.
   ```
   → Route to ticket creation flow

   ![](./media/ex10-followup-logic.png)

1. Create additional troubleshooting topics:

   **Network Troubleshooting:**
   ```
   Let's troubleshoot your network issue:

   🔍 BASIC CHECKS:
   1. Are you connected to the company WiFi or VPN?
   2. Can you access any websites?
   3. Have you tried restarting your computer?

   📡 QUICK FIXES TO TRY:
   1. Disconnect and reconnect to WiFi
   2. Restart your network adapter:
      - Right-click network icon → Troubleshoot problems
   3. If on VPN, disconnect and reconnect

   Did any of these steps resolve your issue?
   ```

   ![](./media/ex10-network-troubleshooting.png)

### Task 5: Configure Escalation and Handoff

In this task, you will set up escalation to human agents for complex issues.

1. Navigate to **Settings** > **Customer engagement** or **Agent transfer**.

   ![](./media/ex10-agent-settings.png)

1. Configure human handoff settings:

   | Field | Value |
   |-------|-------|
   | Enable transfer to agent | Yes |
   | Queue | IT Support Queue |
   | Wait message | Custom |
   | Transfer message | Custom |

   ![](./media/ex10-handoff-settings.png)

1. Create an **Escalation** topic:

   Trigger phrases:
   ```
   Talk to a human
   I need a real person
   This is urgent
   Escalate this
   Transfer me to IT
   Agent please
   ```

   ![](./media/ex10-escalation-triggers.png)

1. Build the escalation flow:

   ```
   I understand you'd like to speak with an IT support specialist directly.

   Before I transfer you, could you briefly describe your issue? This will help our team assist you faster.
   ```

   Save response as: `EscalationReason`

   ![](./media/ex10-escalation-reason.png)

1. Add conditional logic for critical issues:

   **Condition:** If description contains "security breach", "hacked", "virus", "ransomware", "data leak"
   
   **Then:**
   ```
   🚨 SECURITY ALERT DETECTED 🚨

   I'm immediately escalating this to our Security Response Team. 

   ⚠️ IMPORTANT WHILE YOU WAIT:
   - Do NOT click any suspicious links
   - Do NOT enter any passwords
   - Disconnect from the network if instructed
   - Do NOT delete any files

   A security specialist will be with you in the next 5 minutes. Please stay on this chat.
   ```
   → Trigger high-priority alert flow

   ![](./media/ex10-security-escalation.png)

1. For normal escalations, add transfer node:

   Add **Transfer to agent** node:
   ```
   I'm transferring you to our IT Support team now. 

   📋 I've shared the following with the agent:
   - Your issue category
   - Description of the problem
   - Troubleshooting steps already attempted

   Current estimated wait time: 5-10 minutes

   Thank you for your patience!
   ```

   ![](./media/ex10-transfer-node.png)

1. Create a **Status Check** topic for ticket follow-up:

   Trigger phrases:
   ```
   Check my ticket status
   What's the status of my request
   Update on my issue
   Any progress on my ticket
   When will my issue be fixed
   ```

   ![](./media/ex10-status-triggers.png)

1. Build the status check flow:

   ```
   I can help you check your ticket status. Please provide your ticket number.

   If you don't have your ticket number, I can look it up using your email address.
   ```

   → Query ticket system and return status

   ![](./media/ex10-status-flow.png)

1. Test the complete IT Support agent:

   - Navigate to **Test** panel
   - Try various scenarios:
     - Password reset (self-service path)
     - Hardware issue (ticket creation)
     - Security concern (emergency escalation)
     - Status check

   ![](./media/ex10-test-agent.png)

1. Publish the agent once testing is complete:

   - Click **Publish**
   - Enable in Microsoft 365 Copilot channel

   ![](./media/ex10-publish.png)

## Summary

In this exercise, you successfully:

- Designed a comprehensive IT support workflow with intelligent routing
- Created an IT Support agent with multiple capabilities
- Built automated ticket creation and routing flows using Power Automate
- Implemented self-service troubleshooting for common issues like password resets
- Configured intelligent escalation with priority handling for security incidents
- Set up human handoff for complex issues
- Created ticket status tracking functionality

Your IT Support agent can now handle the majority of common IT issues automatically while ensuring complex problems reach human specialists quickly.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
