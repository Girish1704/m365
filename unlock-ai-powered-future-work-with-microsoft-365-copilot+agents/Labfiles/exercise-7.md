# Exercise 7: Build an HR Agent with Microsoft Copilot Studio - Part 2

## Estimated Duration: 90 Minutes

## Overview

In this exercise, you will complete the HR Agent you started building in Exercise 6. You will configure agent topics and conversations, build leave application flows with smart approval logic, enhance agent instructions, and publish the agent to Microsoft 365 Copilot.

## Prerequisites

- Completed Exercise 6: Build an HR Agent with Microsoft Copilot Studio - Part 1
- HR Agent created in Copilot Studio with SharePoint knowledge configured

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Configure agent topics and conversations
- Task 2: Build leave application flow with auto-approval and email integration
- Task 3: Enhance agent instructions with policy references
- Task 4: Configure agent greeting message
- Task 5: Test and publish the agent to Microsoft 365 Copilot

### Task 1: Configure Agent Topics and Conversations

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
   Create a topic that helps users apply for leave and handles leave requests.
   Start by greeting the user and saying you can help them apply for leave.
   Collect the following information from the user:
   1. Ask for their Employee ID (number)
   2. Ask for their full name
   3. Ask how many days of leave they need (number)
   4. Ask for the reason for their leave request
   After collecting all information, display a summary showing:
   - Employee ID
   - Employee Name
   - Number of days
   - Reason
   ```

   ![](../media/m36-copg-ex6-c-g41.png)

1. Click **Create** to generate the topic.

1. Review the generated flow which should include:
   - Welcome message for leave applications
   - Question nodes to collect Employee ID, Name, Days, and Reason
   - Leave summary message with collected information
   - Action node calling the Leave-Flow
   - Approval status message
   - Closing message

      ![](../media/m36-copg-ex6-c-g42.png)

1. Click **Save** to save the topic.

### Task 2: Build Leave Application Flow with Smart Approval

In this task, you will create an automated leave application flow that automatically approves requests for 2 days or less, and routes longer requests to a manager via email for approval.

1. In Microsoft 365 Copilot, select **Apps (1)**, and then choose **Teams (2)**.

   ![](../media/d2-d2-cor-g8.png)

1. Navigate to **Microsoft Teams** and go to the **Chat (1)** section, click the **New (2)** dropdown, and select **New team (3)** to create a dedicated workspace for leave notifications.

   ![](../media/ex2-travel-g1.png)

1. Configure your new team with the following details:
   - **Team name:** Enter **HR Approvals Team-<inject key="DeploymentID" enableCopy="false"/>**
   - **First channel:** Type **Leave Approvals-<inject key="DeploymentID" enableCopy="false"/>**
   - Click **Create** to establish the team structure.

      ![](../media/d2-d2-cor-g9.png)

1. In the **Add members to HR Approvals Team** window, select **Skip** to continue without adding members for this demonstration.

   ![](../media/ex2-travel-g3.png)


1. In Copilot Studio, go to the **Flows (1)** section and click **New agent flow (2)** to create a new automated workflow.

   ![](../media/ex2-travel-g4.png)

1. Under **AI capabilities**, select **When an agent calls the flow** as the trigger mechanism to enable agent-initiated workflows.

   ![](../media/ex2-travel-g5.png)

1. Click **Add an input** under the trigger node to define the data parameters that your agent will pass to the workflow.

   ![](../media/ex2-travel-g6.png)

1. Choose **Number** as the data type for the first input parameter.

   ![](../media/ex2-travel-g7.png)

1. In the **When an agent calls the flow** trigger, rename the input to **Employee ID**.

   ![](../media/d2-d2-cor-g11.png)

1. Select **Add an input** to add a new input parameter.

   ![](../media/d2-d2-cor-g12.png)

1. Select **Text** to set the input type.

   ![](../media/ex2-travel-g13.png)

1. Rename the input to **EmployeeName (1)**, and then select **Add an input (2)** to continue adding parameters.

   ![](../media/ex2-travel-g14.png)

1. Add the remaining required input parameters.

   | Input Type | Name |
   |------------|------| 
   | Number | `LeaveDays` |
   | Text | `LeaveReason` |

   ![](../media/d2-d2-cor-g15.png)

1. Select the **+** icon to add the next step in the flow.

   ![](../media/d2-d2-cor-g16.png)

1. In the **Add an action** pane, search for **Condition (1)**, and then select **Condition (2)** under Control.

   ![](../media/d2-d2-cor-g17.png)

1. In the **Condition** action, select the **Choose a value (1)** field, and then use the **Dynamic content (2)** picker to insert.

   ![](../media/d2-d2-cor-g18.png)

1. And then choose **LeaveDays** from the dynamic content list.

   ![](../media/d2-d2-cor-g19.png)

1. Configure the condition to check if leave days is less than or equal to 2:
   - **Operator:** Select **is less than or equal to**
   - **Value:** Enter `2`

   ![](../media/d2-d2-cor-g20.png)

   >**Smart Approval Logic:** This condition enables automatic approval for short leave requests (2 days or less), reducing administrative overhead while ensuring longer requests receive proper manager review.

1. In the **True** branch, select the **+** icon to add an action.

   ![](../media/d2-d2-cor-g24.png)

1. Search for **Post message in a chat or channel (1)** and **select (2)** it from the available Microsoft Teams actions.

   ![](../media/d2-d2-cor-g22.png)

1. Establish the Microsoft Teams connection by selecting **Sign in** to authenticate and authorize the workflow integration.

   ![](../media/ex2-travel-g13.png)

1. Choose your **ODL_User (1)** account credentials to authenticate and establish the Microsoft Teams connection.

   ![](../media/ex2-travel-g14.png)

1. In the confirmation dialog, select **Allow access** to grant Microsoft Teams permissions.

   ![](../media/d2-d2-cor-g23.png)

1. Configure the Teams message for auto-approved requests:
   - **Post as (1):** Flow bot
   - **Post in (2):** Channel
   - **Team (3):** HR Approvals Team
   - **Channel (4):** Leave Approvals  
   - **Message (5):** 
     ```
     **LEAVE AUTO-APPROVED**
     
     **Employee ID:** [EmployeeID]
     **Employee:** [EmployeeName]
     **Duration:** [LeaveDays] day(s)
     **Reason:** [LeaveReason]
     
     _This request was automatically approved as it is for 2 days or less._
     ```

   ![](../media/d2-d2-cor-g26.png)

1. Highlight **[EmployeeID] (1)** in the message box and click the **Dynamic content (2)** icon to insert the variable.

   ![](../media/d2-d2-cor-g27.png)

1. From the **Dynamic content** pane, select **Employee ID** to insert it into the message.

   ![](../media/d2-d2-cor-g28.png)

1. In the **Message** box, select **[EmployeeName] (1)**, and then use the **Dynamic content (2)** picker to insert the value.

   ![](../media/d2-d2-cor-g29.png)

1. From the **Dynamic content** pane, select **EmployeeName** to insert it into the message.

   ![](../media/d2-d2-cor-g30.png)

1. In the **Message** box, repeat the same action to insert dynamic content for the remaining placeholders.

   | Field     | Dynamic content |
   |-----------|------------------|
   | Duration  | `LeaveDays`     |
   | Reason    | `LeaveReason`   |

   ![](../media/d2-d2-cor-g31.png)

1. In the **Add an action** pane, search for **Respond to the agent (1)**, and then select **Respond to the agent (2)**.

   ![](../media/d2-d2-cor-g33.png)

1. Click **Add an output** under the **Respond to the agent** action to define the return message.

   ![](../media/d2-d2-cor-g34.png)

1. In the **Respond to the agent** action, select **Text** as the output type

   ![](../media/d2-d2-cor-g35.png)

1. Add the output:
   - **Name (1):** `ApprovalStatus`
   - **Value (2):** `Your leave request for  has been automatically approved!

   ![](../media/d2-d2-cor-g36.png)

1. In the **False** branch, select the **+** icon to add an action.

   ![](../media/d2-d2-cor-g21.png)

1. In the **Add an action** pane, search for **Send an Email (V2) (1)**, and then select **Send an email (V2) (2)** under Office 365 Outlook.

   ![](../media/d2-d2-cor-g37.png)

1. In the **Send an email (V2)** action, select **Sign in** to create the Office 365 Outlook connection.

   ![](../media/d2-d2-cor-g38.png)

1. In the confirmation dialog, select **Allow access** to grant Office 365 Outlook permissions.

   ![](../media/d2-d2-cor-g39.png)

1. Configure the email for manager approval requests:
   - **To:** Enter your email address: - Email/Username: **<inject key="AzureAdUserEmail"></inject>**
   - **Subject:** `Leave Approval`
   - **Body:** Enter the following:

      ```
      Leave Approval Request

      Employee ID: [EmployeeID]
      Employee Name: [EmployeeName]
      Duration: [LeaveDays] day(s)
      Reason: [LeaveReason]

      This request requires manager approval as it exceeds 2 days.
      Please review and respond to the employee accordingly.
      ```

      ![](../media/d2-d2-cor-g40.png)

1. In the **Body** box, select **[EmployeeID] (1)**, and then use the **Dynamic content (2)** picker to insert the value.

   ![](../media/d2-d2-cor-g41.png)

1. From the **Dynamic content** pane, select **Employee ID** to insert it into the message.

   ![](../media/d2-d2-cor-g42.png)

1. Replace all bracketed values[EmployeeName], [LeaveDays], and [LeaveReason] with Dynamic content from the trigger.

   ![](../media/d2-d2-cor-g44.png)

1. Click **Add an action** after the email action.

   ![](../media/d2-d2-cor-g45.png)

1. Search for **Respond to agent (1)** and select **Respond to the agent (2)** under the Skills section.

   ![](../media/d2-d2-cor-g46.png)

1. In the **Respond to the agent** action, select **Add an output** to define a response for the agent.

   ![](../media/d2-d2-cor-g47.png)

1. In the **Respond to the agent** action, select **Text** as the output type.

   ![](../media/d2-d2-cor-g48.png)

1. Add the output:

   - **Name:** `ApprovalStatus`
   - **Value:** `Your leave request has been sent!`

      ![](../media/d2-d2-cor-g49.png)

1. Click **Save draft (1)** to save the current flow configuration before publishing.

   ![](../media/d2-d2-cor-g50.png)

1. Verify the confirmation message **"We saved your draft flow. You can test and run it after you publish."** appears at the top of the page.

   ![](../media/ex2-travel-g25.png)

1. Click **Publish** to make the agent flow available for use.

   ![](../media/d2-d2-cor-g51.png)

1. Select **Overview (1)**, and then click **Edit (2)** to update the flow details.

   ![](../media/d2-d2-cor-g52.png)

1. In the **Details** pane, enter **Leave-Flow** in the **Flow name (1)** field, and then select **Save (2)**.

   ![](../media/d2-d2-cor-g53.png)

1. Return to **Copilot Studio** and navigate to your **HR Assistant** agent.

1. Select **Topics (1)**, and then choose **Leave and Time Off (2)** to open the topic.

   ![](../media/d2-d2-cor-g62.png)

1. On the **Message** node, select the **More options (1)** menu, and then choose **Delete (2)**.

   ![](../media/d2-d2-cor-g54.png)

1. Select the **+** icon to add the next step in the topic flow.

   ![](../media/d2-d2-cor-g55.png)

1. Select **Add a tool (1)**, switch to **Basic tools (2)**, and then choose **Leave-Flow (3)** to add the flow to the topic.```

   ![](../media/d2-d2-cor-g56.png)

1. For each **Power Automate input (1)**, select the corresponding variable from the **Custom** list, such as **EmployeeID (2)**, to map the values.

   ![](../media/d2-d2-cor-g57.png)

1. For **EmployeeName (1)**, select the **More options** menu, and then choose **EmployeeName (2)** from the variable list.

   ![](../media/d2-d2-cor-g58.png)

1. Repeat the same mapping process for the remaining ** inputs**.

   - **LeaveDays:** Select `LeaveDays`
   - **LeaveReason:** Select `LeaveReason`

1. Once all variables are mapped correctly, verify the configuration.

      ![](../media/d2-d2-cor-g59.png)
   
1. Select **Save** to store the topic changes.

   ![](../media/d2-d2-cor-g60.png)

1. Navigate to the **Overview (1)** tab and click **Publish (2)** to make the agent updates live.

   ![](../media/d2-d2-cor-g63.png)

1. In the **Publish this agent** dialog box, click **Publish** to confirm and deploy the agent.

   ![](../media/ex2-travel-g58.png)

1. Once the agent is successfully published, click **Test** to verify and interact with your HR Agent.

   ![](../media/ex2-travel-g59.png)

1. **Test 1 - Short Leave (Auto-Approval):**

   In the **Test your agent** panel, type **I want to apply for leave (1)** and click the **Send (2)** icon to initiate the leave application flow.

   ![](../media/cor-g-g23.png)

   When prompted, provide:
   - **Employee ID:** 121
   - **Name:** John Smith
   - **Days:** 1
   - **Reason:** Personal appointment

      ![](../media/ex2-travel-g61.png)

   **Expected Result:** The leave should be automatically approved since it's 2 days or less.

   ![](../media/ex2-travel-g64.png)

1. **Test 2 - Long Leave (Manager Approval Required):**

   Type: `I need to request time off`

   When prompted, provide:
   - **Employee ID:** 1002
   - **Name:** Jane Doe
   - **Days:** 5
   - **Reason:** Family vacation

1. When prompted for Office 365 Outlook connection access, click **Allow** to authorize the integration and enable the flow to send approval emails.

   ![](../media/ex2-travel-g63.png)

   **Expected Result:** An email notification should be sent to the manager for approval.

1. Navigate to **Outlook** to verify the leave approval email was received.

   Verify the email contains:
   - Employee ID and name
   - Leave duration (5 days)
   - Reason for leave
   - Request for manager review

   ![](../media/ex6-email-received.png)

   >**Smart Workflow Benefits:** This automated approval system reduces HR workload by auto-approving routine short leave requests while ensuring proper oversight for extended absences through email notifications to managers.

### Task 3: Enhance Agent Instructions with Policy References

In this task, you will update the agent instructions to ensure it properly references the HR policy documents from the knowledge base.

1. Return to your HR Assistant agent in Microsoft Copilot Studio.

1. Click on **Overview** in the left navigation to return to the agent overview.

1. Locate the **Instructions** section and click **Edit**.

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

1. Click **Save** to save the updated instructions.

### Task 4: Configure Agent Greeting Message

In this task, you will configure the greeting message that the agent displays when users start a conversation.

1. From the **menu**, select **Topics** to access the topics list.

   ![](../media/ex2-travel-g75.png)

1. Click on **System** > **Greeting** to customize the welcome message.

1. Update the greeting message:

   ```
   Welcome to the HR Assistant! I can help you with:

   - Leave policies and requests
   - Benefits information
   - Onboarding procedures
   - HR policies and guidelines
   - General HR questions

   How can I assist you today?
   ```

1. Click on the **Save** button to save the topic configuration.

   ![](../media/ex2-travel-g56.png)

### Task 5: Test and Publish the Agent to Microsoft 365 Copilot

In this task, you will test the agent and prepare it for publishing.

1. Click the **Test** button in the bottom left corner to open the test panel.

1. Test the agent with various queries:

   **Test 1 - Greeting:**

   In the **Test your agent** panel, type **Hello (1)** and click the **Send (2)** icon.

   ![](../media/cor-g-g23.png)

   **Expected Output:** The agent should respond with a welcome greeting.

1. **Test 2 - Leave Request:**

   **Prompt:**
   ```
   How do I request vacation time?
   ```

   **Expected Output:** The agent should provide information about leave policies and how to request time off.

1. **Test 3 - Benefits:**

   **Prompt:**
   ```
   What health insurance options are available?
   ```

   **Expected Output:** The agent should reference the Employee Benefits Guide and provide health insurance information.

1. **Test 4 - Knowledge-based question:**

   **Prompt:**
   ```
   How many sick days can I take without a medical certificate?
   ```

   **Expected Output:** The agent should reference the Leave Policy document and provide accurate information.

1. Once testing is complete, navigate to the **Overview (1)** tab and click **Publish (2)** to make the agent live.

   ![](../media/ex2-travel-g57.png)

1. In the **Publish this agent** dialog box, click **Publish** to confirm and deploy the agent.

   ![](../media/ex2-travel-g58.png)

1. Wait for the publishing process to complete.

   >**Note:** The agent may take a few minutes to appear in Microsoft 365 Copilot after publishing.

1. Once published, you can access the agent from Microsoft 365 Copilot Chat:

   - Go to `https://www.microsoft365.com`
   - Click on **Copilot**
   - Look for your HR Assistant agent in the agents panel

## Summary

In this exercise, you completed building the HR Agent using Microsoft Copilot Studio. You learned how to:

- Configure agent topics including Escalation to HR, General HR Help, and Leave and Time Off
- Build agent flows with smart approval logic for leave requests
- Integrate Teams notifications for auto-approved requests and email for manager approvals
- Enhance agent instructions with specific policy references
- Configure the agent greeting message
- Test the agent with various scenarios to validate functionality
- Publish the agent to Microsoft 365 Copilot for end-user access

The HR Agent is now live and can help employees with policies, benefits, leave management, and general HR questions while maintaining professional and empathetic interactions.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
