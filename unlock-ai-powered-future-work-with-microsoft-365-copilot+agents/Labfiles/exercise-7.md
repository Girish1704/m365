# Exercise 7: Build an HR Agent with Microsoft Copilot Studio - Part 2

## Estimated Duration: 30 Minutes

## Overview

In this exercise, you will complete the HR Agent you started building in Exercise 6. You will enhance the agent's instructions to properly reference policy documents, configure actions and integrations, thoroughly test the agent's capabilities, and publish it to Microsoft 365 Copilot.

## Prerequisites

- Completed Exercise 6: Build an HR Agent with Microsoft Copilot Studio - Part 1
- HR Agent created in Copilot Studio with topics configured

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Enhance agent instructions with policy references
- Task 2: Configure agent actions and integrations
- Task 3: Test and publish the agent to Microsoft 365 Copilot

### Task 1: Enhance Agent Instructions with Policy References

In this task, you will update the agent instructions to ensure it properly references the HR policy documents from the knowledge base.

1. Return to your HR Assistant agent in Microsoft Copilot Studio.

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

### Task 2: Configure Agent Actions and Integrations

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

### Task 3: Test and Publish the Agent to Microsoft 365 Copilot

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

In this exercise, you completed building the HR Agent using Microsoft Copilot Studio. You learned how to:

- Enhance agent instructions with specific policy references for accurate responses
- Explore actions and integrations with Power Automate
- Configure system topics like the greeting message
- Test the agent with various scenarios to validate functionality
- Publish the agent to Microsoft 365 Copilot for end-user access

The HR Agent is now live and can help employees with policies, benefits, leave management, and general HR questions while maintaining professional and empathetic interactions.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
