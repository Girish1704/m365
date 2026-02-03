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

In this task, you will configure topics that define how the agent handles different types of conversations. You will use the **Add from description with Copilot** feature to quickly generate topic flows.

1. In the agent editor, click on **Topics** in the left navigation.

   ![](./media/ex6-topics-section.png)

1. You will see some default topics already created. Click **+ Add a topic** to expand the dropdown menu.

   ![](./media/ex6-add-topic-dropdown.png)

1. Select **Add from description with Copilot** option.

   ![](./media/ex6-add-from-description.png)

   >**Note:** This feature uses AI to automatically generate a complete topic flow based on your description, saving significant time compared to building topics manually.

#### Topic 1: General HR Help

1. In the **Add from description with Copilot** dialog, enter the following:

   | Field | Value |
   |-------|-------|
   | **Name your topic** | `General HR Help` |
   | **Create a topic to...** | See description below |

   **Topic Description:**
   ```
   Help employees with general HR questions. First greet them warmly and ask what they need help with. Collect their HR query as a text input. If they ask about "benefits", respond with information about health insurance, retirement plans, wellness programs, and direct them to the HR portal. If they ask about "company policies" or "company rules", tell them to check the employee handbook on SharePoint. If they ask about "onboarding" or "new hire", explain the onboarding process includes orientation, training, and resources. If they ask about "performance review" or "appraisal", explain reviews are conducted annually. For any other query, ask them to clarify. If still unclear, offer to escalate to the HR team by asking if they want to escalate (yes/no). If yes, confirm their query will be forwarded. End by asking if there's anything else to help with.
   ```

   ![](./media/ex6-general-hr-description.png)

1. Click **Create** to generate the topic.

1. Copilot Studio will automatically generate the conversation flow with:
   - Welcome message
   - Question node to collect the HR query
   - Condition branches for benefits, policies, onboarding, and performance reviews
   - Clarification flow for unrecognized queries
   - Escalation option
   - Closing message

   ![](./media/ex6-general-hr-flow.png)

1. Review the generated flow and click **Save** to save the topic.

#### Topic 2: Leave and Time Off

1. Click **+ Add a topic** > **Add from description with Copilot** again.

1. Enter the following details:

   | Field | Value |
   |-------|-------|
   | **Name your topic** | `Leave and Time Off` |
   | **Create a topic to...** | See description below |

   **Topic Description:**
   ```
   Help employees with leave and time off questions. Greet them and ask how you can assist with leave. Present a multiple choice question asking which type of leave they want information about with options: Annual/Vacation, Sick, Personal, or All leave types. For Annual/Vacation, explain it accrues monthly and is for vacations or personal time, direct them to HR portal for balance. For Sick leave, explain it's for health-related absences and accrues per policy. For Personal leave, explain it's for important personal matters with eligibility requirements. For All leave types, provide a summary of all three types. Then explain that leave accrues based on employment status and tenure, and unused leave may carry over. Direct them to the HR portal for exact balances. Ask if they have questions about special leave cases like medical, parental, or emergency leave (yes/no). If yes, explain these require additional documentation and they should contact HR. End by asking if there's anything else about leave.
   ```

   ![](./media/ex6-leave-description.png)

1. Click **Create** to generate the topic.

1. Review the generated flow which should include:
   - Welcome message for leave inquiries
   - Multiple choice question for leave type selection
   - Conditional responses for each leave type
   - Information about leave accrual and HR portal
   - Special cases handling
   - Closing message

   ![](./media/ex6-leave-flow.png)

1. Click **Save** to save the topic.

#### Topic 3: Escalation to HR

1. Click **+ Add a topic** > **Add from description with Copilot** one more time.

1. Enter the following details:

   | Field | Value |
   |-------|-------|
   | **Name your topic** | `Escalation to HR` |
   | **Create a topic to...** | See description below |

   **Topic Description:**
   ```
   Handle escalation requests when employees need to contact HR directly. Start by acknowledging their concern is important and will be handled confidentially. Collect three pieces of information: 1) Ask them to briefly describe their issue or concern as text, 2) Ask for their name or the employee's name if reporting for someone else, 3) Ask for a contact email so HR can reach out. After collecting all information, confirm you will send this to the HR team. Inform them that HR will review their request and contact them at the provided email, and urgent issues will be prioritized. Provide next steps: HR will reach out soon, monitor email for response, and they can contact HR directly by phone for immediate assistance. Emphasize privacy and confidentiality are priorities. End by offering further assistance.
   ```

   ![](./media/ex6-escalation-description.png)

1. Click **Create** to generate the topic.

1. Review the generated flow which should include:
   - Acknowledgment message
   - Question to collect issue description
   - Question to collect employee name
   - Question to collect contact email
   - Confirmation message
   - Next steps information
   - Privacy statement

   ![](./media/ex6-escalation-flow.png)

1. Click **Save** to save the topic.

   >**Note:** The AI-generated topics may vary slightly. You can edit the generated nodes to customize the messages or add additional logic as needed.

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
