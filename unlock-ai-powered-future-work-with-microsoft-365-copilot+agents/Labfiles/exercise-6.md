# Exercise 6: Build an HR Agent with Microsoft Copilot Studio - Part 1

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will begin building a comprehensive HR Agent using Microsoft Copilot Studio that extends Microsoft 365 Copilot Chat capabilities. Microsoft Copilot Studio provides a powerful low-code platform for creating intelligent agents that can handle complex conversations, connect to enterprise data sources, and integrate with Microsoft 365 Copilot.

In Part 1, you will create the foundational HR agent, connect it to SharePoint knowledge sources, configure conversation topics, and build an automated leave application workflow with smart approval logic.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Upload HR policy documents to SharePoint
- Task 2: Access Microsoft Copilot Studio and create an HR Agent
- Task 3: Configure agent topics and conversations
- Task 4: Build leave application flow with auto-approval and Teams integration

### Task 1: Create a SharePoint Site

In this task, you will create a SharePoint site to store law firm documents including case files, client information, and billing data.

1. Open a new browser tab and navigate to the **Microsoft 365** portal:

   ```
   https://m365.cloud.microsoft/chat
   ```

1. In the left navigation pane, select **Apps (1)**, and then choose **SharePoint (2)** to open SharePoint.

   ![](../media/m365-cop-ex2-g5.png)

1. In SharePoint, select **Create (1)**, and then choose **Site (2)** to start creating a new site.

   ![](../media/m365-cop-ex2-g6.png)

1. On the **Create a site** page, select **Team site** to create a collaborative workspace for your team.

   ![](../media/m365-cop-ex2-g7.png)

1. On the **Select a template** page, choose the **Standard team** template to continue creating the team site.

   ![](../media/m365-cop-ex2-g8.png)

1. On the **Preview and use 'Standard team' template** page, review the site details, and then select **Use template** to continue.

   ![](../media/m365-cop-ex2-g9.png)

1. Select **Team site** and configure:

   | Field | Value |
   |-------|-------|
   | Site name | **HRPolicies-<inject key="DeploymentID" enableCopy="false"/>** |

   ![](../media/d2-d2-cor-g4.png)

   > **Note:** If you receive an error stating that the site name is already in use, modify the last few digits with unique numbers and try again.

1. On the **Set language and other options** page, confirm **Private – only members can access this site (1)** under Privacy settings, and then select **Create site (2)**.

   ![](../media/m365-cop-ex2-g11.png)

1. On the **Add site owners and members** page, select **Finish** to complete the site creation.

   ![](../media/m365-cop-ex2-g12.png)

### Task 2: Upload HR Policy Documents to SharePoint

In this task, you will download the HR policy documents and upload them to SharePoint. These documents will later be used as knowledge sources for the agent to provide grounded responses.

#### Step 1: Download and Review Policy Documents

1. First, download the HR policy documents. Open a new browser tab and navigate to:

   ```
   https://github.com/CloudLabsAI-Azure/Safe-Travels-Agent/archive/refs/heads/Day2-datasets.zip
   ```

1. In the **Downloads** pane, select **Safe-Travel-Agent-Day2-datasets.zip** to open the file.

   ![](../media/nd-d2-cor-g-9.png)

1. In **Downloads (1)**, right-click **Safe-Travel-Agent-Day2-datasets (2)**, and then select **Extract All (3)**.

   ![](../media/nd-d2-cor-g-10.png)

1. In the **Extract Compressed (Zipped) Folders** window, keep the default destination, and then choose **Extract**.

   ![](../media/nd-d2-cor-g-11.png)

1. In the **Downloads** pane, select **Safe-Travel-Agent-Day2-datasets.zip** to open the file.

   ![](../media/nd-d2-cor-g-9.png)

1. In the SharePoint site, select **Documents (1)**, click **Upload (2)**, and then choose **Folder (3)** to create a new folder.``

   ![](../media/d2-d2-cor-g5.png)

1. Browse to the location where you extracted the Day2-datasets, navigate to the **policy** folder, select all the policy PDF documents, and click **Open**.

   ![](../media/nd-d2-cor-g-15.png)

   ![](../media/d2-d2-cor-g2.png)

1. Wait for all files to upload successfully. You should see all 12 policy documents in the folder.

   ![](../media/d2-d2-cor-g3.png)

   >**Note:** These policy documents contain comprehensive Contoso HR information that the agent will use to answer employee questions accurately.

1. Copy the site URL from the browser address bar in the following format: `https://<tenant>.sharepoint.com/sites/HRPolicies-<inject key="DeploymentID" enableCopy="false"/>`.

   ![](../media/nd-d2-cor-g-16.png)

   > **Note:** This URL will be used later as a knowledge source while configuring the agent. Copy and save it in Notepad for easy access.

### Task 3: Access Microsoft Copilot Studio and Create an HR Agent

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
   You are an HR Assistant for Contoso Corporation. Help employees with:
   - Company policies and procedures
   - Leave management and applications (collect Employee ID, Name, Days, Reason)
   - Benefits information (health insurance, retirement, wellness)
   - Onboarding information for new employees
   - Performance review processes
   - General HR FAQs
   
   For leave requests, always collect: Employee ID, Employee Name, Number of Days, and Reason.
   Leave requests of 2 days or less are auto-approved; longer requests require manager approval.
   Be professional, empathetic, and helpful. Escalate complex issues to human HR representatives.
   ```

1. Click **+ Add knowledge** to add data and resources to the agent.

   ![](../media/m36-copg-ex6-c-g8.png)

1. Click **SharePoint** to add knowledge from SharePoint sources.

   ![](../media/m36-copg-ex6-c-g9.png)

1. Enter the SharePoint site URL in the **URL field (1)**, then click **Add (2)** to connect the source.

   ![](../media/m36-copg-ex6-c-g10.png)

   > **Note:** Use the SharePoint site URL that you copied earlier and saved in Notepad.  

1. Click **Add to agent** to attach the SharePoint knowledge source.

   ![](../media/m36-copg-ex6-c-g11.png)

1. Verify that the knowledge source shows **Ready** to confirm it is successfully added.

   ![](../media/m36-copg-ex6-c-g12.png)

   >**Note:** The SharePoint knowledge source is now connected and will be used by the agent to answer questions based on the HR policy documents.

## Summary

In this exercise, you created the foundation of an HR Agent using Microsoft Copilot Studio. You learned how to:

- Upload HR policy documents to SharePoint as a knowledge base
- Access and navigate Microsoft Copilot Studio
- Create a new agent and configure its basic settings
- Add SharePoint as a knowledge source for grounded responses
- Configure four types of conversation topics:
  - Manual topic creation with conversation flow (Escalation to HR)
  - AI-generated topics using Copilot (General HR Help and Leave and Time Off)
- Build agent flows with conditional logic for smart approvals
- Integrate email notifications for manager approval workflows
- Implement auto-approval rules for requests of 2 days or less

In the next exercise, you will enhance the agent's instructions, configure actions, test its capabilities, and publish it to Microsoft 365 Copilot.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
