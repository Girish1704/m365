# Exercise 6: Extend Microsoft 365 Copilot Chat with an HR Agent Built Using Microsoft Copilot Studio

## Estimated Duration: 90 Minutes

## Overview

In this exercise, you will build a comprehensive HR Agent using Microsoft Copilot Studio that extends Microsoft 365 Copilot Chat capabilities. Microsoft Copilot Studio provides a powerful low-code platform for creating intelligent agents that can handle complex conversations, connect to enterprise data sources, and integrate with Microsoft 365 Copilot.

You will create an HR agent that can answer employee questions about policies, benefits, leave management, and direct complex queries to appropriate HR personnel.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Upload HR policy documents to SharePoint
- Task 2: Access Microsoft Copilot Studio and create an HR Agent
- Task 3: Add knowledge sources to the agent
- Task 4: Configure agent topics and conversations
- Task 5: Configure agent actions and integrations
- Task 6: Test and publish the agent to Microsoft 365 Copilot

### Task 1: Upload HR Policy Documents to SharePoint

In this task, you will upload HR policy documents to SharePoint that will later be used as knowledge sources for the agent to provide grounded responses.

#### Step 1: Locate and Review Policy Documents

1. First, open **File Explorer** on your lab VM.

1. Navigate to the HR policy documents folder:

   ```
   C:\datasets\policies
   ```

   ![](../media/ex6-policies-folder.png)

1. You will find the following HR policy documents:

   | Document | Description |
   |----------|-------------|
   | 01-Leave-Policy.md | Annual, sick, personal, parental leave entitlements |
   | 02-Holiday-Calendar-2025.md | Official holidays and floating holidays |
   | 03-Employee-Benefits-Guide.md | Medical, dental, 401k, wellness programs |
   | 04-Code-of-Conduct.md | Ethics, values, conflicts of interest |
   | 05-Performance-Review-Policy.md | Ratings, goals, merit increases |
   | 06-Onboarding-Guide.md | First day through 90-day milestones |
   | 07-Remote-Work-Policy.md | Hybrid/remote work guidelines |
   | 08-Health-and-Safety-Policy.md | Emergency procedures, hazard reporting |
   | 09-Travel-and-Expense-Policy.md | Booking, per diem, reimbursement |
   | 10-Anti-Harassment-Policy.md | Discrimination prevention, reporting |
   | 11-IT-Security-Policy.md | Passwords, devices, data handling |
   | 12-Training-and-Development-Policy.md | Tuition, certifications, mentoring |

1. Select all the policy files (Ctrl+A) and copy them (Ctrl+C).

1. Open a new browser tab and navigate to your SharePoint site:

   ```
   https://<inject key="TenantName" enableCopy="false"/>.sharepoint.com/sites/HRPoliciesHub-<inject key="DeploymentID" enableCopy="false"/>
   ```

1. Click on **Documents** in the left navigation.

   ![](../media/ex6-sharepoint-documents.png)

1. Click **+ New** > **Folder** to create a new folder.

1. Name the folder `HR Policies` and click **Create**.

   ![](../media/ex6-create-folder.png)

1. Open the **HR Policies** folder and click **Upload** > **Files**.

   ![](../media/ex6-upload-files.png)

1. Navigate to `C:\datasets\policies`, select all the policy documents, and click **Open**.

   ![](../media/ex6-select-policies.png)

1. Wait for all files to upload successfully. You should see all 12 policy documents in the folder.

   ![](../media/ex6-policies-uploaded.png)

   >**Note:** These policy documents contain comprehensive Contoso HR information that the agent will use to answer employee questions accurately.

### Task 2: Access Microsoft Copilot Studio and Create an HR Agent

In this task, you will navigate to Microsoft Copilot Studio, create a new HR Agent, and configure its basic settings.

1. On the Copilot Studio home page, click **+ Create** from the left navigation.

   ![](../media/m36-copg-ex6-c-g1.png)

1. Click **+ Create blank agent** to start creating a new agent.

   ![](../media/m36-copg-ex6-c-g2.png)

1. Click **Edit** to update the agent details.

   ![](../media/m36-copg-ex6-c-g3.png)

1. Enter the agent name in the **Name (1)** field, add the description in the **Description (2)** box, then click **Save (3)** to apply the changes.

   | Field | Value |
   |-------|-------|
   | Name | `HR Assistant-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `An intelligent HR assistant that helps employees with policies, benefits, and HR-related questions.` |

   ![](../media/m36-copg-ex6-c-g4.png)

1. Click **Edit** to update the agent instructions.

   ![](../media/m36-copg-ex6-c-g5.png)

1. Enter the agent instructions in the **Instructions (1)** box, then click **Save (2)** to apply the changes.

   ```
   HR assistant that helps employees with:
   - Company policies and procedures
   - Leave management (vacation, sick leave, parental leave)
   - Benefits information (health insurance, retirement, wellness)
   - Onboarding information for new employees
   - Performance review processes
   - General HR FAQs
   
   The agent should be professional, empathetic, and helpful. It should escalate complex issues to human HR representatives.
   ```

   ![](../media/m36-copg-ex6-c-g6.png)

1. Click **+ Add knowledge** to add data and resources to the agent.

   ![](../media/m36-copg-ex6-c-g8.png)

1. Click **SharePoint** to add knowledge from SharePoint sources.

   ![](../media/m36-copg-ex6-c-g9.png)

1. Enter the SharePoint site URL in the **URL field (1)**, then click **Add (2)** to connect the source.

   ![](../media/m36-copg-ex6-c-g10.png)

1. Click **Add to agent** to attach the SharePoint knowledge source.

   ![](../media/m36-copg-ex6-c-g11.png)

1. Verify that the knowledge source shows **Ready** to confirm it is successfully added.

   ![](../media/m36-copg-ex6-c-g12.png)

   >**Note:** The SharePoint knowledge source is now connected and will be used by the agent to answer questions based on the HR policy documents.

### Task 3: Configure Agent Topics and Conversations

In this task, you will configure topics that define how the agent handles different types of conversations. You will create an escalation topic and use the **Add from description with Copilot** feature to quickly generate topic flows.

#### Topic 1: Escalation to HR

1. Click **Topics (1)**, then select **+ Add a topic (2)** and choose **From blank (3)** to create a new topic.

   ![](../media/m36-copg-ex6-c-g13.png)

1. Enter the topic description in the **Describe what the topic does** box.

   ```
   This tool can handle queries like these:
   contact HR, escalate to HR, report issue to HR, I need help from HR, talk to human resources
   ```

   ![](../media/m36-copg-ex6-c-g14.png)

1. Click the **+ (Add) (1)** icon to add the next node to the topic flow.

   ![](../media/m36-copg-ex6-c-g15.png)

1. Select **Send a message** to add a message node to the topic flow.

   ![](../media/m36-copg-ex6-c-g16.png)

1. Enter the response text in the **Message** box to define the agent’s reply.

   ![](../media/m36-copg-ex6-c-g17.png)

1. Click the **+ (Add) (1)** icon, then select **Send a message (2)** to add another message node.

   ![](../media/m36-copg-ex6-c-g18.png)

1. Enter the response text in the **Message** box to define the next agent reply.

   ![](../media/m36-copg-ex6-c-g19.png)

1. Select **Add from description with Copilot** option.

   ![](../media/m36-copg-ex6-c-g20.png)

1. Enter the question in the **Question text (1)** field, then select **User’s entire response (2)** under Identify.

   ![](../media/m36-copg-ex6-c-g21.png)

1. Click the **Var1** variable under **Save user response as** to edit the response storage.

   ![](../media/m36-copg-ex6-c-g22.png)

1. Enter the variable name in the **Variable name (1)** field, then click the **Close (X) (2)** button to save the changes.

   ![](../media/m36-copg-ex6-c-g23.png)

1. Click the **+ (Add) (1)** icon, then select **Ask a question (2)** to add another question node.

   ![](../media/m36-copg-ex6-c-g24.png)

1. Enter the name prompt in the **Question text (1)** field, then select **Person name (2)** under Identify.

   ![](../media/m36-copg-ex6-c-g25.png)

1. Click the **Var1** variable under **Save user response as** to rename and configure the name field.

   ![](../media/m36-copg-ex6-c-g26.png)

1. Enter the variable name in the **Variable name (1)** field, then click the **Close (X) (2)** button to save the changes.

   ![](../media/m36-copg-ex6-c-g27.png)

1. Click the **+ (Add) (1)** icon, then select **Ask a question (2)** to add another question node.

   ![](../media/m36-copg-ex6-c-g28.png)

1. Enter the email prompt in the **Question text (1)** field, select **Email (2)** under Identify, then save the response in **ContactEmail (3)**.

   ![](../media/m36-copg-ex6-c-g29.png)

1. Click the **+ (Add) (1)** icon, then select **Send a message (2)** to add a confirmation message.

   ![](../media/m36-copg-ex6-c-g30.png)

1. Enter the confirmation message in the **Message text (1)** box to inform the user.

   ![](../media/m36-copg-ex6-c-g31.png)

1. Click **Untitled** to rename the topic.

   ![](../media/m36-copg-ex6-c-g32.png)

1. Enter **Escalation to HR** as the topic name to save and identify the flow.

   ![](../media/m36-copg-ex6-c-g33.png)

1. Click **Save** to store your changes.

   ![](../media/m36-copg-ex6-c-g34.png)

#### Topic 2: General HR Help

1. Click **Topics** to return to the topics list after saving the topic.

   ![](../media/m36-copg-ex6-c-g35.png)

1. Click **+ Add a topic (1)**, then select **Add from description with Copilot (2)** to create a new topic automatically.

   ![](../media/m36-copg-ex6-c-g36.png)

1. In the **Add from description with Copilot** dialog, enter the following:

   | Field | Value |
   |-------|-------|
   | **Name your topic** | `General HR Help` |
   | **Create a topic to...** | See description below |

   **Topic Description:**
   ```
   Create a topic that helps users with general HR questions.
   Start by greeting the user and asking what HR topic they need help with.
   Let the user explain their question in their own words.
   Identify whether the question is related to:
   - Benefits
   - Company policies or rules
   - Onboarding or new hire process
   - Performance reviews or appraisals
   If the question is about benefits, provide basic information and guide the user to the HR portal.
   If the question is about company policies, explain where official documents can be found.
   If the question is about onboarding, guide new employees through the process.
   If the question is about performance reviews, explain timelines and procedures.
   If the question is unclear, ask the user to clarify.
   If the assistant cannot answer, offer to escalate to HR.
   If the user agrees, confirm that the request will be sent.
   End by asking if the user needs any more help.
   ```

   ![](../media/m36-copg-ex6-c-g37.png)

1. Copilot Studio will automatically generate the conversation flow with:
   - Welcome message
   - Question node to collect the HR query
   - Condition branches for benefits, policies, onboarding, and performance reviews
   - Clarification flow for unrecognized queries
   - Escalation option
   - Closing message

1. Review the generated flow.

1. Click **Topic checker (1)** to verify **Errors (0) (2)**, then click **Save (3)** to store the changes.

   ![](../media/m36-copg-ex6-c-g40.png)

#### Topic 3: Leave and Time Off

1. Click **Topics** to return to the topics list after saving the topic.

   ![](../media/m36-copg-ex6-c-g35.png)

1. Click **+ Add a topic (1)**, then select **Add from description with Copilot (2)** to create a new topic automatically.

   ![](../media/m36-copg-ex6-c-g36.png)

1. Enter the following details:

   | Field | Value |
   |-------|-------|
   | **Name your topic** | `Leave and Time Off` |
   | **Create a topic to...** | See description below |

   **Topic Description:**
   ```
   Create a topic that helps users with leave and time off questions.
   Start by greeting the user and asking what kind of leave they need help with.
   Let the user choose or explain their leave type.
   Support questions related to:
   - Annual or vacation leave
   - Sick leave
   - Personal leave
   - General leave information
   Provide clear information based on the selected leave type.
   Explain how leave is earned, used, and managed.
   Guide users to the HR portal to check their leave balance.
   Ask if the user has questions about special leave cases such as:
   - Medical leave
   - Parental leave
   - Emergency leave
   If needed, recommend contacting HR for special cases.
   End by asking if the user needs further assistance.
   ```

   ![](../media/m36-copg-ex6-c-g41.png)

1. Click **Create** to generate the topic.

1. Review the generated flow which should include:
   - Welcome message for leave inquiries
   - Multiple choice question for leave type selection
   - Conditional responses for each leave type
   - Information about leave accrual and HR portal
   - Special cases handling
   - Closing message

      ![](../media/m36-copg-ex6-c-g42.png)

1. Click **Save** to save the topic.

### Task 4: Enhance Agent Instructions with Policy References

In this task, you will update the agent instructions to ensure it properly references the HR policy documents from the knowledge base.

1. Click on **Overview** in the left navigation to return to the agent overview.

1. Locate the **Instructions** section and click **Edit**.

   ![](../media/ex6-edit-instructions.png)

1. Update the agent instructions to reference the policy documents:

   ```
   You are an HR Assistant for Contoso Corporation. Your role is to help employees with HR-related questions.

   When answering questions:
   - Always refer to the official HR policy documents in the knowledge base
   - For leave questions, reference the Leave Policy and Holiday Calendar
   - For benefits questions, reference the Employee Benefits Guide
   - For conduct or ethics questions, reference the Code of Conduct
   - For performance questions, reference the Performance Review Policy
   - For new employee questions, reference the Onboarding Guide
   - For remote work questions, reference the Remote Work Policy
   - For safety concerns, reference the Health and Safety Policy
   - For travel questions, reference the Travel and Expense Policy
   - For harassment or discrimination concerns, reference the Anti-Harassment Policy
   - For IT or security questions, reference the IT Security Policy
   - For training questions, reference the Training and Development Policy

   Be professional, empathetic, and helpful. Provide accurate information from the policy documents.
   If you cannot find the answer in the policies, offer to escalate to the HR team.
   Always maintain confidentiality and privacy.
   ```

   ![](../media/ex6-updated-instructions.png)

1. Click **Save** to save the updated instructions.

### Task 5: Configure Agent Actions and Integrations

In this task, you will configure actions that the agent can perform.

1. In the agent editor, click on **Actions** in the left navigation.

   ![](../media/ex6-actions-section.png)

1. Click **+ Add an action**.

   ![](../media/ex6-add-action.png)

1. Browse the available action types:

   - **Prebuilt connectors** - Connect to external services
   - **Power Automate flows** - Trigger automated workflows
   - **Custom connectors** - Connect to custom APIs

   ![](../media/ex6-action-types.png)

1. For this exercise, we will create a simple escalation flow. Select **Power Automate** > **Create a new flow**.

   ![](../media/ex6-create-flow.png)

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

   ![](../media/ex6-greeting.png)

1. Click **Save**.

### Task 6: Test and Publish the Agent to Microsoft 365 Copilot

In this task, you will test the agent and prepare it for publishing.

1. Click the **Test** button in the bottom left corner to open the test panel.

   ![](../media/ex6-test-button.png)

1. Test the agent with various queries:

   **Test 1 - Greeting:**
   ```
   Hello
   ```

   ![](../media/ex6-test-greeting.png)

   **Expected Output:**

   ![](../media/ex6-greeting-response.png)

1. **Test 2 - Leave Request:**

   **Prompt:**
   ```
   How do I request vacation time?
   ```

   ![](../media/ex6-test-leave.png)

   **Expected Output:**

   ![](../media/ex6-leave-response.png)

1. **Test 3 - Benefits:**

   **Prompt:**
   ```
   What health insurance options are available?
   ```

   ![](../media/ex6-test-benefits.png)

   **Expected Output:**

   ![](../media/ex6-benefits-response.png)

1. **Test 4 - Knowledge-based question:**

   **Prompt:**
   ```
   How many sick days can I take without a medical certificate?
   ```

   ![](../media/ex6-test-knowledge.png)

   **Expected Output:**

   ![](../media/ex6-knowledge-response.png)

1. Once testing is complete, click **Publish** in the top right corner.

   ![](../media/ex6-publish-button.png)

1. In the publish dialog, select **Microsoft 365 Copilot** as the channel.

   ![](../media/ex6-publish-m365.png)

1. Review the publishing settings and click **Publish**.

   ![](../media/ex6-publish-confirm.png)

1. Wait for the publishing process to complete.

   ![](../media/ex6-publishing.png)

   >**Note:** The agent may take a few minutes to appear in Microsoft 365 Copilot after publishing.

1. Once published, you can access the agent from Microsoft 365 Copilot Chat:

   - Go to `https://www.microsoft365.com`
   - Click on **Copilot**
   - Look for your HR Assistant agent in the agents panel

   ![](../media/ex6-agent-in-copilot.png)

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
