# Exercise 4: Automate Knowledge Assistance Through Microsoft 365 Copilot Agents

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create and configure a custom Copilot Agent within Microsoft 365 Copilot Chat to automate knowledge assistance. Custom agents allow you to define specific behaviors, instructions, and knowledge sources to provide focused assistance for particular business scenarios.

You will create an IT Help Desk agent that can answer common IT questions, provide troubleshooting guidance, and direct users to appropriate resources.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Navigate to Copilot Agent Builder
- Task 2: Create an IT Help Desk Agent
- Task 3: Configure agent instructions
- Task 4: Add knowledge sources
- Task 5: Test the agent

### Task 1: Navigate to Copilot Agent Builder

In this task, you will access the agent creation interface within Microsoft 365 Copilot.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to the Microsoft 365 portal:

   ```
   https://www.microsoft365.com
   ```

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. On the Microsoft 365 home page, click on the **Copilot** icon from the left navigation panel.

   ![](./media/ex4-copilot-icon.png)

1. In the Copilot interface, click on the **Agents** button on the right side panel.

   ![](./media/ex4-agents-button.png)

1. In the agents panel, click on **Create agent** or **+ New agent** to start building your custom agent.

   ![](./media/ex4-create-agent.png)

### Task 2: Create an IT Help Desk Agent

In this task, you will create a new agent for IT help desk assistance.

1. In the agent creation wizard, provide the following details:

   | Field | Value |
   |-------|-------|
   | Agent name | `IT Help Desk-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `An AI assistant that helps employees with common IT questions, troubleshooting, and technology guidance.` |

   ![](./media/ex4-agent-details.png)

1. For the agent icon, select an appropriate icon or let Copilot generate one based on the description.

   ![](./media/ex4-agent-icon.png)

1. Click **Next** or **Continue** to proceed to the instructions configuration.

   >**Note:** The agent name should be descriptive and unique. The description helps users understand what the agent can assist with.

### Task 3: Configure Agent Instructions

In this task, you will define how the agent should behave and respond to users.

1. In the **Instructions** section, enter the following to define the agent's persona and behavior:

   **Agent Instructions:**
   ```
   You are a helpful IT Help Desk assistant for our organization. Your role is to:

   1. Answer common IT questions about software, hardware, and systems
   2. Provide step-by-step troubleshooting guidance for technical issues
   3. Help users with password resets and account access issues
   4. Guide users on how to use company applications and tools
   5. Explain IT policies and security best practices
   6. Direct users to submit tickets for complex issues that require IT intervention

   Guidelines for your responses:
   - Be patient and use clear, non-technical language when possible
   - Provide step-by-step instructions for troubleshooting
   - Always prioritize security - never ask for or accept passwords
   - For hardware issues, gather relevant information before suggesting solutions
   - If you cannot resolve an issue, guide users to submit an IT ticket
   - Include relevant links to documentation when available

   Common IT Systems in our organization:
   - Email: Microsoft Outlook (web and desktop)
   - Collaboration: Microsoft Teams
   - File Storage: OneDrive and SharePoint
   - VPN: GlobalProtect for remote access
   - Password Reset: Self-service portal at password.contoso.com

   You should NOT:
   - Attempt to access or modify user accounts directly
   - Provide workarounds that bypass security policies
   - Share confidential IT infrastructure information
   - Make promises about ticket resolution times
   ```

   ![](./media/ex4-agent-instructions.png)

1. Click **Next** to proceed to knowledge configuration.

### Task 4: Add Knowledge Sources

In this task, you will create a knowledge base document and add it as a source for the agent.

1. First, create an IT knowledge base document. Open a new browser tab and navigate to SharePoint:

   - On the Microsoft 365 home page, click **Apps** > **SharePoint**
   - Or navigate to: `https://<inject key="TenantName" enableCopy="false"/>.sharepoint.com`

   ![](./media/ex4-sharepoint.png)

1. Click on **+ Create site** in the top navigation.

   ![](./media/ex4-create-site.png)

1. Select **Team site** and configure:

   | Field | Value |
   |-------|-------|
   | Site name | `IT Knowledge Base-<inject key="DeploymentID" enableCopy="false"/>` |
   | Site description | `IT documentation and troubleshooting guides` |

   ![](./media/ex4-site-settings.png)

1. Click **Create** and wait for the site to be provisioned.

1. Navigate to **Documents** in the new site.

   ![](./media/ex4-documents.png)

1. Click **+ New** > **Word document** to create a new document.

   ![](./media/ex4-new-document.png)

1. Name the document `IT-Troubleshooting-Guide` and add the following content:

   ```
   IT TROUBLESHOOTING GUIDE
   Contoso IT Department

   COMMON ISSUES AND SOLUTIONS

   1. PASSWORD RESET
   
   If you have forgotten your password:
   - Go to password.contoso.com
   - Click "Forgot Password"
   - Enter your email address
   - Follow the verification steps
   - Create a new password meeting these requirements:
     * Minimum 12 characters
     * At least one uppercase letter
     * At least one number
     * At least one special character
   
   If self-service is not working, contact IT Help Desk.

   2. VPN CONNECTION ISSUES
   
   If you cannot connect to VPN:
   - Ensure you have GlobalProtect installed
   - Check your internet connection
   - Try disconnecting and reconnecting
   - Clear VPN cache: Settings > Clear Cache
   - If issues persist, try restarting your computer
   - Contact IT if problems continue

   3. EMAIL NOT SYNCING
   
   For Outlook sync issues:
   - Check internet connection
   - Try Outlook web at outlook.office.com
   - Clear Outlook cache
   - Remove and re-add your account
   - Check if you have exceeded mailbox quota (50GB limit)

   4. TEAMS AUDIO/VIDEO ISSUES
   
   For Microsoft Teams problems:
   - Test audio in Settings > Devices
   - Ensure correct microphone/speaker selected
   - Check if camera is blocked by other apps
   - Update Teams to latest version
   - Try Teams web version as alternative

   5. SLOW COMPUTER PERFORMANCE
   
   To improve performance:
   - Restart your computer
   - Close unused applications
   - Check for Windows updates
   - Run disk cleanup
   - Contact IT if RAM upgrade needed

   IT SUPPORT CONTACT INFORMATION
   
   - Self-service portal: helpdesk.contoso.com
   - Email: itsupport@contoso.com
   - Phone: Extension 4357 (HELP)
   - Hours: Monday-Friday, 8 AM - 6 PM
   - Emergency after-hours: +1-800-555-HELP
   ```

   ![](./media/ex4-kb-content.png)

1. Save and close the document.

1. Copy the SharePoint site URL and save it in **Notepad** for later use.

   ![](./media/ex4-copy-url.png)

1. Return to the agent configuration. In the **Knowledge** section, click **+ Add knowledge source**.

   ![](./media/ex4-add-knowledge.png)

1. Select **SharePoint** and enter your SharePoint site URL.

   ![](./media/ex4-sharepoint-source.png)

   >**Note:** If the site link shows **This item was not found**, this may be due to indexing delays. Select **Add anyway** to continue.

1. Click **Add** to add the knowledge source.

1. Click **Create** to finalize the agent.

   ![](./media/ex4-create-final.png)

### Task 5: Test the Agent

In this task, you will test your IT Help Desk agent with various queries.

1. Once the agent is created, you will see a chat interface. Start testing with a greeting:

   **Prompt:**
   ```
   Hello, I need help with an IT issue.
   ```

   ![](./media/ex4-test-greeting.png)

   **Expected Output:**

   ![](./media/ex4-greeting-response.png)

   The agent should respond with a helpful greeting and ask about your issue.

1. Test password reset guidance:

   **Prompt:**
   ```
   I forgot my password and cannot log in. What should I do?
   ```

   ![](./media/ex4-test-password.png)

   **Expected Output:**

   ![](./media/ex4-password-response.png)

   The agent should provide step-by-step password reset instructions.

1. Test VPN troubleshooting:

   **Prompt:**
   ```
   I am working from home and cannot connect to the VPN. It keeps timing out.
   ```

   ![](./media/ex4-test-vpn.png)

   **Expected Output:**

   ![](./media/ex4-vpn-response.png)

1. Test email issues:

   **Prompt:**
   ```
   My Outlook is not syncing emails. I can see them on my phone but not on my laptop.
   ```

   ![](./media/ex4-test-email.png)

   **Expected Output:**

   ![](./media/ex4-email-response.png)

1. Test escalation handling:

   **Prompt:**
   ```
   My laptop screen is cracked and I need a replacement.
   ```

   ![](./media/ex4-test-hardware.png)

   **Expected Output:**

   ![](./media/ex4-hardware-response.png)

   The agent should recognize this requires IT intervention and guide the user to submit a ticket.

1. Test security awareness:

   **Prompt:**
   ```
   Can you reset my password for me? My email is john@contoso.com and I can tell you my old password.
   ```

   ![](./media/ex4-test-security.png)

   **Expected Output:**

   ![](./media/ex4-security-response.png)

   The agent should refuse to handle passwords directly and redirect to proper channels.

## Summary

In this exercise, you created and configured a custom Copilot Agent for IT Help Desk assistance. You learned how to:

- Access the Copilot Agent Builder
- Create and name a custom agent
- Configure detailed agent instructions and behavior
- Add SharePoint as a knowledge source
- Test the agent with various IT-related queries

Custom agents enable you to automate knowledge assistance for specific business functions, improving efficiency and user satisfaction.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
