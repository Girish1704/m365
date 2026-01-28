# Exercise 6: Extend Microsoft 365 Copilot Chat with a HR Agent Built Using Microsoft Copilot Studio

## Estimated Duration: 90 Minutes

## Overview

In this exercise, you will build a comprehensive HR Agent using Microsoft Copilot Studio that extends Microsoft 365 Copilot Chat capabilities. Microsoft Copilot Studio provides a powerful low-code platform for creating intelligent agents that can handle complex conversations, connect to enterprise data sources, and integrate with Microsoft 365 Copilot.

You will create an HR agent that can answer employee questions about policies, benefits, leave management, and direct complex queries to appropriate HR personnel.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access Microsoft Copilot Studio
- Task 2: Create a new HR Agent
- Task 3: Configure agent topics and conversations
- Task 4: Add knowledge sources to the agent
- Task 5: Configure agent actions and integrations
- Task 6: Test and publish the agent to Microsoft 365 Copilot

### Task 1: Access Microsoft Copilot Studio

In this task, you will navigate to Microsoft Copilot Studio and explore its interface.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to Microsoft Copilot Studio:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex6-copilot-studio-url.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex6-studio-signin.png)

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. You will be redirected to the Microsoft Copilot Studio home page. Take a moment to explore the interface:

   - **Home** — Overview and quick actions
   - **Agents** — List of all your created agents
   - **Environments** — Manage different environments
   - **Solutions** — Package and deploy solutions

   ![](./media/ex6-studio-home.png)

1. If prompted to select an environment, choose the default environment or your organization's environment.

   ![](./media/ex6-select-environment.png)

   >**Note:** Microsoft Copilot Studio uses the Power Platform environment infrastructure. Different environments allow you to separate development, testing, and production workloads.

### Task 2: Create a New HR Agent

In this task, you will create a new agent specifically designed for HR assistance.

1. On the Copilot Studio home page, click **+ Create** from the left navigation panel.

   ![](./media/ex6-create-copilot.png)

1. You will see different options for creating an agent:
   - **Start from template** — Use pre-built templates
   - **Start from blank** — Build from scratch
   - **New agent** — Use AI to generate initial setup

   ![](./media/ex6-creation-options.png)

1. Select **New agent** for an AI-assisted setup.

   ![](./media/ex6-new-agent.png)

1. In the **Describe your agent** field, enter the following description:

   **Agent Description:**
   ```
   Create an HR assistant that helps employees with:
   - Company policies and procedures
   - Leave management (vacation, sick leave, parental leave)
   - Benefits information (health insurance, retirement, wellness)
   - Onboarding information for new employees
   - Performance review processes
   - General HR FAQs
   
   The agent should be professional, empathetic, and helpful. It should escalate complex issues to human HR representatives.
   ```

   ![](./media/ex6-agent-description.png)

1. Click **Create** to proceed.

1. Copilot Studio will generate a new agent based on your description. Wait for the agent to be created.

1. Once created, update the agent settings by selecting **Settings** from the top menu:

   | Field | Value |
   |-------|-------|
   | Name | `HR Assistant-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `An intelligent HR assistant that helps employees with policies, benefits, and HR-related questions.` |

   ![](./media/ex6-agent-settings.png)

1. Click **Save** to save your agent settings.

   ![](./media/ex6-agent-created.png)

1. Wait for the agent to be created. Copilot Studio will automatically generate initial topics based on your description.

   ![](./media/ex6-agent-generating.png)

### Task 3: Configure Agent Topics and Conversations

In this task, you will configure and customize conversation topics for your HR agent.

1. Once the agent is created, you will be in the agent editor. Navigate to the **Topics** section.

   ![](./media/ex6-topics-section.png)

1. You will see some auto-generated topics based on your description. Common topics include:
   - Greeting
   - Leave request
   - Benefits inquiry
   - Escalate to human

   ![](./media/ex6-auto-topics.png)

1. Click on **+ Add a topic** > **Create from blank** to create a custom topic.

   ![](./media/ex6-create-topic.png)

1. Create a new topic for leave balance inquiries:

   | Field | Value |
   |-------|-------|
   | Name | `Leave Balance Inquiry` |
   | Description | `Helps employees check their leave balance and understand leave policies` |

   ![](./media/ex6-leave-topic.png)

1. In the **Trigger phrases** section, add phrases that would activate this topic:

   ```
   What is my leave balance
   How many vacation days do I have
   Check my PTO balance
   How much leave do I have left
   Can I see my time off balance
   What's my sick leave balance
   ```

   ![](./media/ex6-trigger-phrases.png)

1. Design the conversation flow using the visual designer:

   - **Step 1:** Add a **Message** node with a greeting:
     ```
     I'd be happy to help you with your leave balance information!
     ```

   - **Step 2:** Add a **Question** node asking for leave type:
     ```
     What type of leave would you like to check?
     ```
     Add options:
     - Annual/Vacation Leave
     - Sick Leave
     - Personal Leave
     - All Leave Types

   ![](./media/ex6-conversation-flow.png)

1. For each option, add appropriate responses:

   **For Annual Leave:**
   ```
   Based on our standard policy, full-time employees are entitled to 20 days of annual leave per year.
   
   To check your specific balance:
   1. Log into the HR Portal
   2. Navigate to "My Leave"
   3. Your current balance will be displayed
   
   Would you like me to help you with anything else related to leave?
   ```

   ![](./media/ex6-annual-leave-response.png)

1. Add conditional logic for complex scenarios. Click **+ Add node** > **Condition**.

   ![](./media/ex6-add-condition.png)

1. Create a topic for escalation to HR. Go back to **Topics** and create a new topic:

   | Field | Value |
   |-------|-------|
   | Name | `Escalate to HR` |
   | Description | `Transfers the conversation to a human HR representative` |

   Trigger phrases:
   ```
   I want to talk to HR
   Connect me to a human
   Speak to HR representative
   This is urgent
   I need human help
   Transfer to HR team
   ```

   ![](./media/ex6-escalation-topic.png)

1. In the conversation flow, add:

   ```
   I understand you'd like to speak with an HR representative directly. Let me connect you.

   Before I transfer you, could you briefly describe your concern? This will help our HR team assist you more effectively.
   ```

   ![](./media/ex6-escalation-flow.png)

1. Add a **Transfer to agent** node or configure escalation settings.

   ![](./media/ex6-transfer-agent.png)

### Task 4: Add Knowledge Sources to the Agent

In this task, you will connect knowledge sources to enable the agent to provide accurate, grounded responses.

1. Navigate to the **Knowledge** section in your agent configuration.

   ![](./media/ex6-knowledge-section.png)

1. Click **+ Add knowledge** to add a new knowledge source.

   ![](./media/ex6-add-knowledge.png)

1. You will see different knowledge source options:
   - **Public websites** — Crawl and index web content
   - **Files** — Upload documents directly
   - **SharePoint** — Connect to SharePoint sites
   - **Dataverse** — Connect to Dataverse tables

   ![](./media/ex6-knowledge-options.png)

1. Select **SharePoint** to connect to your HR SharePoint site created earlier.

   ![](./media/ex6-select-sharepoint.png)

1. Enter the SharePoint site URL or search for your HR Policies site:

   ```
   https://<inject key="TenantName" enableCopy="false"/>.sharepoint.com/sites/HRPolicies-<inject key="DeploymentID" enableCopy="false"/>
   ```

   ![](./media/ex6-sharepoint-url.png)

1. Select the site and click **Add**.

   ![](./media/ex6-add-sharepoint-source.png)

1. Wait for the content to be indexed. This may take a few minutes.

   ![](./media/ex6-indexing.png)

1. Let's also upload some additional HR documents. Click **+ Add knowledge** > **Files**.

   ![](./media/ex6-add-files.png)

1. Create a new document with employee benefits information. First, open Word and create a document with this content:

   ```
   EMPLOYEE BENEFITS GUIDE

   HEALTH INSURANCE
   - Company provides comprehensive medical, dental, and vision coverage
   - Coverage begins on the first day of the month following hire date
   - Employees can add dependents during open enrollment or qualifying life events
   - Premium sharing: Company pays 80%, Employee pays 20%

   RETIREMENT BENEFITS
   - 401(k) plan with company match up to 6%
   - Immediate vesting for employee contributions
   - Company match vests over 3 years (1/3 per year)
   - Enrollment available immediately upon hire

   PAID TIME OFF
   - Vacation: 20 days per year (accrues monthly)
   - Sick Leave: 10 days per year
   - Personal Days: 3 days per year
   - Holidays: 11 paid holidays per year

   WELLNESS BENEFITS
   - Gym membership reimbursement: up to $50/month
   - Mental health counseling: 6 free sessions per year
   - Annual wellness stipend: $500

   ADDITIONAL BENEFITS
   - Life insurance: 2x annual salary
   - Disability insurance: Short-term and long-term
   - Employee Assistance Program (EAP)
   - Flexible Spending Accounts (FSA/HSA)
   ```

   ![](./media/ex6-benefits-document.png)

1. Save the document and upload it to the knowledge base.

   ![](./media/ex6-upload-document.png)

1. Verify the knowledge sources are added and indexed.

   ![](./media/ex6-knowledge-added.png)

### Task 5: Configure Agent Actions and Integrations

In this task, you will add actions that allow the agent to perform tasks and integrate with other systems.

1. Navigate to the **Actions** section in your agent.

   ![](./media/ex6-actions-section.png)

1. Click **+ Add an action** to create a new action.

   ![](./media/ex6-add-action.png)

1. You will see options for different action types:
   - **Pre-built connector actions** — Use Power Platform connectors
   - **Custom actions** — Build with Power Automate
   - **AI Builder actions** — Use AI capabilities

   ![](./media/ex6-action-types.png)

1. Select **Create a new flow** to build a custom action with Power Automate.

   ![](./media/ex6-create-flow.png)

1. Create an action to send an email notification to HR when escalation is needed:

   | Field | Value |
   |-------|-------|
   | Name | `Send HR Notification` |
   | Description | `Sends an email to HR team when an employee escalates an issue` |

   ![](./media/ex6-notification-action.png)

1. In the Power Automate designer, configure the flow:

   - **Trigger:** When the action is called from Copilot
   - **Input:** Employee name, Email, Issue description
   - **Action:** Send email using Office 365 Outlook connector
   - **Recipient:** HR team email or distribution list
   - **Subject:** `[HR Escalation] Employee Inquiry - {Employee Name}`
   - **Body:** Include employee details and issue description

   ![](./media/ex6-flow-design.png)

1. Save the flow and return to Copilot Studio.

   ![](./media/ex6-save-flow.png)

1. Connect the action to your escalation topic:

   - Open the "Escalate to HR" topic
   - After collecting the employee's concern, add a **Call an action** node
   - Select your "Send HR Notification" action
   - Map the inputs accordingly

   ![](./media/ex6-connect-action.png)

1. Configure the agent settings for Microsoft 365 Copilot integration. Navigate to **Settings** or **Channels**.

   ![](./media/ex6-settings.png)

1. Enable the **Microsoft 365 Copilot** channel to allow the agent to appear in Copilot Chat.

   ![](./media/ex6-m365-channel.png)

### Task 6: Test and Publish the Agent to Microsoft 365 Copilot

In this task, you will test your agent and publish it for use in Microsoft 365 Copilot.

1. Navigate to the **Test** section or click **Test your copilot** button.

   ![](./media/ex6-test-section.png)

1. The test panel will open, allowing you to simulate conversations with your agent.

   ![](./media/ex6-test-panel.png)

1. Test the greeting:

   ```
   Hello
   ```

   ![](./media/ex6-test-greeting.png)

1. Test a leave balance inquiry:

   ```
   How many vacation days do I have?
   ```

   ![](./media/ex6-test-leave.png)

1. Test knowledge-based questions:

   ```
   What is the company's health insurance coverage?
   ```

   ![](./media/ex6-test-knowledge.png)

1. Test the escalation flow:

   ```
   I need to speak with someone from HR about a personal matter
   ```

   ![](./media/ex6-test-escalation.png)

1. Review the test results and make any necessary adjustments to topics or responses.

   ![](./media/ex6-test-results.png)

1. Once satisfied with testing, navigate to **Publish** section.

   ![](./media/ex6-publish-section.png)

1. Click **Publish** to publish the latest version of your agent.

   ![](./media/ex6-publish-button.png)

1. After publishing, configure the deployment to Microsoft 365 Copilot:

   - Go to **Channels** > **Microsoft 365 Copilot**
   - Enable the channel
   - Configure visibility and access settings

   ![](./media/ex6-deploy-m365.png)

1. Wait for the agent to be deployed. This may take several minutes.

   ![](./media/ex6-deployment-progress.png)

1. Once deployed, verify the agent appears in Microsoft 365 Copilot:

   - Navigate to Microsoft 365 Copilot Chat
   - Look for your HR Assistant agent in the agents panel
   - Start a conversation with the agent

   ![](./media/ex6-agent-in-copilot.png)

1. Test the agent within Microsoft 365 Copilot to ensure it functions as expected.

   ![](./media/ex6-final-test.png)

## Summary

In this exercise, you successfully:

- Accessed and explored Microsoft Copilot Studio
- Created a new HR Agent using AI-assisted setup
- Configured multiple conversation topics including leave inquiries and escalation
- Added SharePoint and document knowledge sources to enable grounded responses
- Created actions using Power Automate for HR team notifications
- Tested the agent thoroughly in the Copilot Studio test environment
- Published and deployed the agent to Microsoft 365 Copilot

You now have a functional HR agent that extends Microsoft 365 Copilot capabilities, providing employees with instant access to HR information and intelligent assistance.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
