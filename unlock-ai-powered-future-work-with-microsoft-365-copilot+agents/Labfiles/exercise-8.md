# Exercise 8: Build an IT Support Copilot Using Microsoft Copilot Studio

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create an AI-powered IT Support Copilot using Microsoft Copilot Studio that helps employees resolve common IT issues automatically. The copilot will leverage a knowledge base to provide intelligent troubleshooting guidance for password resets, VPN connectivity issues, laptop performance problems, and printer support.

This is the first part of building an autonomous IT support solution. In subsequent exercises, you will add automated ticket creation and deploy the agent to Microsoft Teams.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access Microsoft Copilot Studio
- Task 2: Create a new IT Support Copilot
- Task 3: Configure copilot instructions for IT support scenarios
- Task 4: Upload the IT Support knowledge base
- Task 5: Test the copilot with basic IT queries

### Task 1: Access Microsoft Copilot Studio

In this task, you will navigate to Microsoft Copilot Studio and explore its interface.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to Microsoft Copilot Studio:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex8-copilot-studio-url.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex8-studio-signin.png)

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. You will be redirected to the Microsoft Copilot Studio home page. Take a moment to explore the interface:

   - **Home** — Overview and quick actions
   - **Agents** — List of all your created agents
   - **Environments** — Manage different environments

   ![](./media/ex8-studio-home.png)

1. If prompted to select an environment, choose the default environment or your organization's environment.

   ![](./media/ex8-select-environment.png)

### Task 2: Create a New IT Support Copilot

In this task, you will create a new copilot specifically designed for IT support automation.

1. On the Copilot Studio home page, click **+ Create** from the left navigation panel.

   ![](./media/ex8-create-copilot.png)

1. Click on **+ New Agent** option to create a new agent.

   ![](./media/ex8-new-agent.png)

   >**Note:** If you see an error like "There was a problem creating your agent", click **Create a blank agent** instead.

1. Once on the agent overview pane, click **Edit** inside the **Details** card to edit the agent's name and description.

   ![](./media/ex8-edit-details.png)

1. Configure the agent details as follows:

   | Field | Value |
   |-------|-------|
   | Name | `IT Support Copilot` |
   | Description | `AI-powered assistant for IT support automation including password resets, VPN issues, laptop troubleshooting, and printer support.` |

   ![](./media/ex8-agent-details.png)

1. Click **Save** to apply the changes.

### Task 3: Configure Copilot Instructions for IT Support Scenarios

In this task, you will configure detailed instructions that define how the copilot should handle IT support requests.

1. On the agent overview page, scroll down to the **Instructions** card and click **Edit**.

   ![](./media/ex8-edit-instructions.png)

1. Enter the following instructions in the **Instructions** box:

   ```
   You are an IT Support Copilot designed to help employees resolve common IT issues quickly and efficiently.

   Handle inquiries related to:
   - Password resets and account lockouts
   - VPN connectivity issues
   - Slow device performance and laptop problems
   - Printer issues and printing problems

   When answering questions:
   - First, check the uploaded IT support knowledge base for documented solutions
   - Provide clear, step-by-step troubleshooting guidance
   - Use simple, non-technical language when explaining solutions
   - Ask clarifying questions to understand the issue better before providing solutions

   For password reset requests:
   - Provide self-service reset instructions from the knowledge base
   - Guide users through the password reset portal process
   - If unsuccessful, offer to escalate to IT support

   For VPN and connectivity issues:
   - Guide users through common troubleshooting steps
   - Check if the issue is resolved after each step
   - Suggest alternative connection methods if available

   For hardware/performance issues:
   - Gather details about the problem (slow startup, applications, etc.)
   - Suggest troubleshooting steps from the knowledge base
   - Recommend restarting as a first step for most issues

   For printer issues:
   - Ask about the specific problem (offline, jammed, blank pages)
   - Provide targeted troubleshooting steps
   - Guide users to check physical connections and paper

   Always:
   - Be professional, patient, and helpful
   - Acknowledge the user's frustration when appropriate
   - Provide next steps or escalation options when solutions don't work
   ```

   ![](./media/ex8-instructions-content.png)

1. Click **Save** to save the instructions.

   ![](./media/ex8-save-instructions.png)

### Task 4: Add SharePoint Knowledge Source

In this task, you will connect the IT Support SharePoint site as a knowledge source for the copilot. The SharePoint site contains IT support documentation in PDF format that the copilot will use to answer questions.

1. On your IT Support Copilot page, click **+ Add knowledge** in the Knowledge section.

   ![](./media/ex8-add-knowledge.png)

1. Select **SharePoint** from the available knowledge source options.

   ![](./media/ex8-select-sharepoint.png)

1. In the SharePoint URL field, enter the IT Support SharePoint site URL:

   ```
   https://<inject key="Tenant Name" enableCopy="false"/>.sharepoint.com/sites/ITSupport
   ```

   ![](./media/ex8-sharepoint-url.png)

   >**Note:** The IT Support SharePoint site contains the following PDF documents:
   >| File | Description |
   >|------|-------------|
   >| `01-Password-and-Account-Management.pdf` | Password policies, SSPR, MFA, account lockouts |
   >| `02-VPN-and-Network-Troubleshooting.pdf` | VPN setup, connectivity issues, WiFi |
   >| `03-Laptop-and-Performance-Guide.pdf` | Slow computer, hardware issues, optimization |
   >| `04-Printer-and-Peripheral-Support.pdf` | Printer issues, monitors, docks, peripherals |
   >| `05-IT-Support-Quick-Reference.pdf` | Quick reference card with common solutions |

1. Click **Add** to connect the SharePoint site.

   ![](./media/ex8-add-sharepoint.png)

1. If prompted, sign in with your lab credentials to authorize access to SharePoint.

   ![](./media/ex8-sharepoint-auth.png)

1. Click **Add to agent** to attach the SharePoint knowledge source to your copilot.

   ![](./media/ex8-add-to-agent.png)

1. Wait for the SharePoint site to sync. You should see the status change to **Ready** or **Synced**.

   ![](./media/ex8-kb-ready.png)

   >**Note:** The SharePoint knowledge source may take 2-5 minutes to index all documents. You can proceed to the next task while it processes.

### Task 5: Test the Copilot with Basic IT Queries

In this task, you will test the IT Support Copilot with various common IT support questions.

1. Click the **Test** button in the top-right corner or look for the **Test your copilot** panel on the right side.

   ![](./media/ex8-test-button.png)

1. The test chat panel will open. Start with a greeting:

   **Prompt:**
   ```
   Hello, I need IT help
   ```

   ![](./media/ex8-test-greeting.png)

   **Expected Output:**

   The copilot should greet you and offer to help with IT issues, possibly listing the types of problems it can assist with.

   ![](./media/ex8-greeting-response.png)

1. **Test 1 - Password Reset:**

   **Prompt:**
   ```
   I forgot my password and can't log in
   ```

   ![](./media/ex8-test-password.png)

   **Expected Output:**

   The copilot should provide step-by-step instructions for self-service password reset from the knowledge base.

   ![](./media/ex8-password-response.png)

1. **Test 2 - VPN Issues:**

   Click the **Reset** button (trash icon) to start a new conversation.

   **Prompt:**
   ```
   My VPN won't connect
   ```

   ![](./media/ex8-test-vpn.png)

   **Expected Output:**

   The copilot should ask clarifying questions and provide VPN troubleshooting steps.

   ![](./media/ex8-vpn-response.png)

1. **Test 3 - Slow Laptop:**

   Reset the conversation and test:

   **Prompt:**
   ```
   My laptop is running really slow
   ```

   ![](./media/ex8-test-laptop.png)

   **Expected Output:**

   The copilot should provide performance troubleshooting steps such as restarting, checking Task Manager, and running disk cleanup.

   ![](./media/ex8-laptop-response.png)

1. **Test 4 - Printer Problems:**

   Reset and test:

   **Prompt:**
   ```
   My printer shows as offline
   ```

   ![](./media/ex8-test-printer.png)

   **Expected Output:**

   The copilot should provide steps to bring the printer back online.

   ![](./media/ex8-printer-response.png)

1. **Test 5 - Knowledge Base Query:**

   Reset and test a specific knowledge base question:

   **Prompt:**
   ```
   What are the password requirements?
   ```

   ![](./media/ex8-test-requirements.png)

   **Expected Output:**

   The copilot should provide the password policy requirements from the knowledge base (minimum 12 characters, uppercase, lowercase, numbers, special characters).

   ![](./media/ex8-requirements-response.png)

1. **Test 6 - Contact Information:**

   **Prompt:**
   ```
   How do I contact IT support?
   ```

   ![](./media/ex8-test-contact.png)

   **Expected Output:**

   The copilot should provide IT Help Desk contact information from the knowledge base.

   ![](./media/ex8-contact-response.png)

1. Review your test results. The copilot should be providing helpful, knowledge-based responses for common IT issues.

   >**Note:** If responses are generic or don't reference the knowledge base, wait a few minutes for indexing to complete and try again.

## Summary

In this exercise, you created an IT Support Copilot using Microsoft Copilot Studio. You learned how to:

- Access and navigate Microsoft Copilot Studio
- Create a new copilot agent for IT support automation
- Configure detailed instructions for handling IT support scenarios
- Upload a knowledge base document for AI-powered responses
- Test the copilot with various IT support queries

In the next exercise, you will enhance this copilot by creating agent flows that automatically create support tickets when issues cannot be resolved through self-service.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
