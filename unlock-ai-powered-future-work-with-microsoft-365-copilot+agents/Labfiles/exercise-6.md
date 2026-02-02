# Exercise 6: Extend Microsoft 365 Copilot Chat with an HR Agent Built Using Microsoft Copilot Studio

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

   - **Home** - Overview and quick actions
   - **Agents** - List of all your created agents
   - **Environments** - Manage different environments
   - **Solutions** - Package and deploy solutions

   ![](./media/ex6-studio-home.png)

1. If prompted to select an environment, choose the default environment or your organization's environment.

   ![](./media/ex6-select-environment.png)

   >**Note:** Microsoft Copilot Studio uses the Power Platform environment infrastructure. Different environments allow you to separate development, testing, and production workloads.

### Task 2: Create a New HR Agent

In this task, you will create a new agent specifically designed for HR assistance.

1. On the Copilot Studio home page, click **+ Create** from the left navigation panel.

   ![](./media/ex6-create-copilot.png)

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

### Task 3: Configure Agent Topics and Conversations

In this task, you will configure topics that define how the agent handles different types of conversations.

1. In the agent editor, click on **Topics** in the left navigation.

   ![](./media/ex6-topics-section.png)

1. You will see some default topics already created. Click **+ New topic** > **From blank** to create a custom topic.

   ![](./media/ex6-new-topic.png)

1. Name the topic `Leave Request Information` and add trigger phrases:

   ```
   How do I request leave
   I want to take time off
   Vacation request
   How to apply for leave
   Leave application process
   PTO request
   ```

   ![](./media/ex6-topic-triggers.png)

1. In the topic canvas, build the conversation flow:

   - Add a **Message** node with the text:
   ```
   I can help you understand how to request leave. What type of leave are you interested in?
   ```

   ![](./media/ex6-message-node.png)

1. Add a **Question** node to capture the leave type:

   - Question text: `Please select the type of leave:`
   - Identify: Multiple choice options
   - Options:
     - Annual Leave / Vacation
     - Sick Leave
     - Parental Leave
     - Bereavement Leave
     - Other

   ![](./media/ex6-question-node.png)

1. Add **Condition** branches based on the response:

   - For **Annual Leave**: Add message explaining vacation request process
   - For **Sick Leave**: Add message about sick leave policy
   - For **Parental Leave**: Add message about parental leave entitlements

   ![](./media/ex6-condition-branches.png)

1. For the **Annual Leave** branch, add this message:

   ```
   To request annual leave:

   1. Log in to the HR Portal at hrportal.contoso.com
   2. Navigate to "My Leave" section
   3. Click "New Request"
   4. Select your leave dates
   5. Add any notes for your manager
   6. Submit for approval

   Please provide at least 2 weeks notice for planned leave. Your manager will review and approve your request.

   Is there anything else you would like to know about leave requests?
   ```

   ![](./media/ex6-annual-leave-message.png)

1. Click **Save** to save the topic.

1. Create another topic for **Benefits Information**:

   - Name: `Benefits Inquiry`
   - Trigger phrases:
     ```
     What benefits do I have
     Health insurance information
     401k questions
     Retirement benefits
     Benefits enrollment
     Medical coverage
     ```

   ![](./media/ex6-benefits-topic.png)

1. Build a similar conversation flow for benefits inquiries and save.

### Task 4: Add Knowledge Sources to the Agent

In this task, you will connect the agent to knowledge sources for grounded responses.

1. In the agent editor, click on **Knowledge** in the left navigation.

   ![](./media/ex6-knowledge-section.png)

1. Click **+ Add knowledge**.

   ![](./media/ex6-add-knowledge.png)

1. Select **SharePoint** as the knowledge source type.

   ![](./media/ex6-sharepoint-source.png)

1. Enter the URL of the HR Policies SharePoint site you created in Exercise 5:

   ```
   https://<inject key="TenantName" enableCopy="false"/>.sharepoint.com/sites/HRPoliciesHub-<inject key="DeploymentID" enableCopy="false"/>
   ```

   ![](./media/ex6-enter-sharepoint.png)

   >**Note:** If you did not complete Exercise 5, you can skip this step or create a new SharePoint site with HR documents.

1. Click **Add** to add the knowledge source.

   ![](./media/ex6-knowledge-added.png)

1. Configure how the agent uses knowledge:

   - Enable **Use knowledge to answer questions**
   - Set response style to **Professional and helpful**

   ![](./media/ex6-knowledge-config.png)

1. Click **Save** to save the knowledge configuration.

### Task 5: Configure Agent Actions and Integrations

In this task, you will configure actions that the agent can perform.

1. In the agent editor, click on **Actions** in the left navigation.

   ![](./media/ex6-actions-section.png)

1. Click **+ Add an action**.

   ![](./media/ex6-add-action.png)

1. Browse the available action types:

   - **Prebuilt connectors** - Connect to external services
   - **Power Automate flows** - Trigger automated workflows
   - **Custom connectors** - Connect to custom APIs

   ![](./media/ex6-action-types.png)

1. For this exercise, we will create a simple escalation flow. Select **Power Automate** > **Create a new flow**.

   ![](./media/ex6-create-flow.png)

1. If Power Automate opens, create a simple flow:

   - Trigger: When called from Copilot Studio
   - Action: Send an email to HR

   >**Note:** For this lab, you can skip creating the actual flow. The important concept is understanding how actions extend agent capabilities.

1. Return to Copilot Studio and configure the greeting message:

   - Click on **Topics** > **System** > **Greeting**
   - Customize the greeting:

   ```
   Welcome to the HR Assistant! I can help you with:

   - Leave policies and requests
   - Benefits information
   - Onboarding procedures
   - HR policies and guidelines
   - General HR questions

   How can I assist you today?
   ```

   ![](./media/ex6-greeting.png)

1. Click **Save**.

### Task 6: Test and Publish the Agent to Microsoft 365 Copilot

In this task, you will test the agent and prepare it for publishing.

1. Click the **Test** button in the bottom left corner to open the test panel.

   ![](./media/ex6-test-button.png)

1. Test the agent with various queries:

   **Test 1 - Greeting:**
   ```
   Hello
   ```

   ![](./media/ex6-test-greeting.png)

   **Expected Output:**

   ![](./media/ex6-greeting-response.png)

1. **Test 2 - Leave Request:**

   **Prompt:**
   ```
   How do I request vacation time?
   ```

   ![](./media/ex6-test-leave.png)

   **Expected Output:**

   ![](./media/ex6-leave-response.png)

1. **Test 3 - Benefits:**

   **Prompt:**
   ```
   What health insurance options are available?
   ```

   ![](./media/ex6-test-benefits.png)

   **Expected Output:**

   ![](./media/ex6-benefits-response.png)

1. **Test 4 - Knowledge-based question:**

   **Prompt:**
   ```
   How many sick days can I take without a medical certificate?
   ```

   ![](./media/ex6-test-knowledge.png)

   **Expected Output:**

   ![](./media/ex6-knowledge-response.png)

1. Once testing is complete, click **Publish** in the top right corner.

   ![](./media/ex6-publish-button.png)

1. In the publish dialog, select **Microsoft 365 Copilot** as the channel.

   ![](./media/ex6-publish-m365.png)

1. Review the publishing settings and click **Publish**.

   ![](./media/ex6-publish-confirm.png)

1. Wait for the publishing process to complete.

   ![](./media/ex6-publishing.png)

   >**Note:** The agent may take a few minutes to appear in Microsoft 365 Copilot after publishing.

1. Once published, you can access the agent from Microsoft 365 Copilot Chat:

   - Go to `https://www.microsoft365.com`
   - Click on **Copilot**
   - Look for your HR Assistant agent in the agents panel

   ![](./media/ex6-agent-in-copilot.png)

## Summary

In this exercise, you built an HR Agent using Microsoft Copilot Studio. You learned how to:

- Access and navigate Microsoft Copilot Studio
- Create a new agent with AI-assisted setup
- Configure topics and conversation flows
- Add SharePoint as a knowledge source
- Configure actions and integrations
- Test and publish the agent to Microsoft 365 Copilot

Microsoft Copilot Studio provides a powerful platform for creating sophisticated agents that can handle complex business scenarios.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
