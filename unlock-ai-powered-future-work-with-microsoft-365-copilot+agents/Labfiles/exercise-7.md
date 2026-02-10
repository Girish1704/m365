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

### Task 2: Configure Agent Actions and Integrations

In this task, you will configure actions that the agent can perform.

1. In the agent editor, click on **Actions** in the left navigation.

1. Click **+ Add an action**.

1. Browse the available action types:

   - **Prebuilt connectors** - Connect to external services
   - **Agent flows** - Trigger automated workflows
   - **Custom connectors** - Connect to custom APIs

1. For this exercise, we will create a simple escalation flow. Select **Flows** > **Create a new flow**.

   ![](../media/ex2-travel-g4.png)

1. If the flow editor opens, create a simple flow:

   - Trigger: When called from Copilot Studio
   - Action: Send an email to HR

   >**Note:** For this lab, you can skip creating the actual flow. The important concept is understanding how actions extend agent capabilities.

1. Return to Copilot Studio and configure the greeting message:

   - From the **menu**, select **Topics** to access the topics list.

   ![](../media/ex2-travel-g75.png)

   - Click on **System** > **Greeting**
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

1. Click on the **Save** button to save the topic configuration.

   ![](../media/ex2-travel-g56.png)

### Task 3: Test and Publish the Agent to Microsoft 365 Copilot

In this task, you will test the agent and prepare it for publishing.

1. Click the **Test** button in the bottom left corner to open the test panel.

   ![](../media/ex2-travel-g59.png)

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

- Enhance agent instructions with specific policy references for accurate responses
- Explore actions and integrations with agent flows
- Configure system topics like the greeting message
- Test the agent with various scenarios to validate functionality
- Publish the agent to Microsoft 365 Copilot for end-user access

The HR Agent is now live and can help employees with policies, benefits, leave management, and general HR questions while maintaining professional and empathetic interactions.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
