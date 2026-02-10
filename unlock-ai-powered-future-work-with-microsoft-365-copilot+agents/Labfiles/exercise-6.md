# Exercise 6: Build an HR Agent with Microsoft Copilot Studio - Part 1

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will begin building a comprehensive HR Agent using Microsoft Copilot Studio that extends Microsoft 365 Copilot Chat capabilities. Microsoft Copilot Studio provides a powerful low-code platform for creating intelligent agents that can handle complex conversations, connect to enterprise data sources, and integrate with Microsoft 365 Copilot.

In Part 1, you will create the foundational HR agent, connect it to SharePoint knowledge sources, and configure conversation topics that define how the agent handles different types of employee inquiries.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Upload HR policy documents to SharePoint
- Task 2: Access Microsoft Copilot Studio and create an HR Agent
- Task 3: Configure agent topics and conversations

### Task 1: Upload HR Policy Documents to SharePoint

In this task, you will download the HR policy documents and upload them to SharePoint. These documents will later be used as knowledge sources for the agent to provide grounded responses.

#### Step 1: Download and Review Policy Documents

1. First, download the HR policy documents. Open a new browser tab and navigate to:

   ```
   https://github.com/CloudLabsAI-Azure/unlock-ai-powered-future-work-with-microsoft-365/archive/refs/heads/Day2-datasets.zip
   ```

1. Once downloaded, extract the **Day2-datasets.zip** file to a location of your choice (e.g., Desktop or Downloads folder).

1. Open **File Explorer** and navigate to the extracted folder. Inside the **policy** folder, you will find the following HR policy documents:

   | Document | Description |
   |----------|-------------|
   | Anti-Harassment-Policy.pdf | Discrimination prevention, reporting |
   | Code-of-Conduct.pdf | Ethics, values, conflicts of interest |
   | Employee-Benefits-Guide.pdf | Medical, dental, 401k, wellness programs |
   | Health-and-Safety-Policy.pdf | Emergency procedures, hazard reporting |
   | Holiday-Calendar-2025.pdf | Official holidays and floating holidays |
   | IT-Security-Policy.pdf | Passwords, devices, data handling |
   | Leave-Policy.pdf | Annual, sick, personal, parental leave entitlements |
   | Onboarding-Guide.pdf | First day through 90-day milestones |
   | Performance-Review-Policy.pdf | Ratings, goals, merit increases |
   | Remote-Work-Policy.pdf | Hybrid/remote work guidelines |
   | Training-and-Development-Policy.pdf | Tuition, certifications, mentoring |
   | Travel-and-Expense-Policy.pdf | Booking, per diem, reimbursement |

   >**Note:** These 12 PDF files contain comprehensive Contoso HR policy information.

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

1. Browse to the location where you extracted the Day2-datasets, navigate to the **policy** folder, select all the policy PDF documents, and click **Open**.

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
   | Name | `HR Assistant` |
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

## Summary

In this exercise, you created the foundation of an HR Agent using Microsoft Copilot Studio. You learned how to:

- Upload HR policy documents to SharePoint as a knowledge base
- Access and navigate Microsoft Copilot Studio
- Create a new agent and configure its basic settings
- Add SharePoint as a knowledge source for grounded responses
- Configure three types of conversation topics:
  - Manual topic creation with conversation flow (Escalation to HR)
  - AI-generated topics using Copilot (General HR Help and Leave and Time Off)

In the next exercise, you will enhance the agent's instructions, configure actions, test its capabilities, and publish it to Microsoft 365 Copilot.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
