# Exercise 9: Setup Freshdesk Ticketing and Create IT Support Topics

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will integrate a professional ticketing system (Freshdesk) with your IT Support Copilot. You will set up a Freshdesk free trial account, obtain API credentials, create an agent flow to automatically create tickets in Freshdesk, and then build intelligent topics using generative AI that connect to your Freshdesk flow for ticket escalation.

By the end of this exercise, your IT Support Copilot will be able to automatically create support tickets in Freshdesk when users need escalation—providing a production-ready helpdesk experience.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Setup Freshdesk Free Trial Account
- Task 2: Obtain Freshdesk API Credentials
- Task 3: Create Freshdesk Ticket Flow in Copilot Studio
- Task 4: Create CreateSupportTicket Topic
- Task 5: Create CredentialResetSupport Topic
- Task 6: Create VPNConnectivitySupport Topic
- Task 7: Create HardwareSupportAssistant Topic

### Task 1: Setup Freshdesk Free Trial Account

In this task, you will create a free Freshdesk trial account to use as your ticketing system.

1. Open a new browser tab and navigate to:

   ```
   https://www.freshworks.com/freshdesk/
   ```

   ![](../media/ex9-freshdesk-home.png)

1. Click on **Free trial** or **Try it free** button.

   ![](../media/ex9-freshdesk-trial.png)

1. Fill in the registration form with the following details:

   | Field | Value |
   |-------|-------|
   | First Name | ODL User |
   | Last Name | <inject key="DeploymentID"></inject> |
   | Work Email | <inject key="AzureAdUserEmail"></inject> |
   | Company | Contoso |

   ![](../media/ex9-freshdesk-register.png)

1. Click **Sign up** to create your account.

1. Check your email inbox at **Outlook** for the verification email from Freshdesk:

   - Open a new tab and navigate to: `https://outlook.office.com`
   - Sign in with your lab credentials if prompted
   - Look for an email from Freshdesk with subject like "Activate your account"

   ![](../media/ex9-freshdesk-email.png)

1. Click the activation link in the email to verify your account.

1. You will be redirected to set your password. Enter:

   ```
   Freshdesk@2025
   ```

   ![](../media/ex9-freshdesk-password.png)

1. Complete the setup wizard:
   - Choose your data center region (select the one closest to you)
   - Skip any optional onboarding steps

1. Once setup is complete, you will land on the Freshdesk dashboard.

   ![](../media/ex9-freshdesk-dashboard.png)

   >**Important:** Keep this browser tab open. Note the URL in your browser's address bar—it will look like:
   >```
   >https://your-company-name.freshdesk.com
   >```
   >This is your **Account URL** which you will need in the next task.

### Task 2: Obtain Freshdesk API Credentials

In this task, you will retrieve your Freshdesk API key which is required to connect Copilot Studio to Freshdesk.

1. In the Freshdesk portal, click on your **profile icon** in the top-right corner.

   ![](../media/ex9-freshdesk-profile.png)

1. Select **Profile Settings** from the dropdown menu.

   ![](../media/ex9-freshdesk-settings.png)

1. In your profile page, scroll down to find the **Your API Key** section.

1. Click on **View API Key** to reveal your API key.

   ![](../media/ex9-freshdesk-apikey.png)

1. **Copy the API Key** and save it somewhere safe (e.g., Notepad). You will need this in the next task.

   >**Important:** Keep your API key confidential. This key provides full access to your Freshdesk account.

1. Also note your **Account URL** from the browser address bar:
   ```
   https://your-company-name.freshdesk.com
   ```

   >**Example:** If your URL is `https://contoso-12345.freshdesk.com`, then your Account URL is exactly that.

1. You should now have two values saved:
   - **Account URL:** `https://your-company-name.freshdesk.com`
   - **API Key:** Your copied API key

### Task 3: Create Freshdesk Ticket Flow in Copilot Studio

In this task, you will create an agent flow that connects to Freshdesk and creates support tickets automatically.

1. Return to **Microsoft Copilot Studio** and open your **IT Support Copilot**.

   ![](../media/ex9-open-copilot.png)

1. In the left navigation, click on **Actions** (or **Flows** if displayed).

   ![](../media/ex9-actions-nav.png)

1. Click **+ Add an action** and then select **New agent flow** (or **Create a new flow**).

   ![](../media/ex9-new-flow.png)

   >**Note:** Power Automate flow designer will open in a new pane or tab.

1. You will see a flow template with a Copilot trigger: **When an agent calls the flow**.

   ![](../media/ex9-flow-trigger.png)

1. Click on the trigger **When an agent calls the flow** to expand it.

1. Click **+ Add an input** and add the following two inputs:

   | Input Name | Type |
   |------------|------|
   | Subject | Text |
   | Description | Text |

   ![](../media/ex9-flow-inputs.png)

1. Click **+ New step** (or the **+** button below the trigger).

1. In the search box, type **Freshdesk** and wait for the connector to appear.

   ![](../media/ex9-freshdesk-connector.png)

1. Under the **Freshdesk** connector, select the action **Create a ticket**.

   ![](../media/ex9-create-ticket-action.png)

1. You will be prompted to create a connection to Freshdesk. Fill in the connection details:

   | Field | Value |
   |-------|-------|
   | Connection Name | helpdesk |
   | Account URL | Your Freshdesk account URL (e.g., `https://contoso-12345.freshdesk.com`) |
   | API Key | Your Freshdesk API key (copied in Task 2) |
   | Password | Enter `X` (just the letter X - this is a placeholder) |

   ![](../media/ex9-freshdesk-connection.png)

   >**Note:** The Password field is required by the connector but Freshdesk uses API key authentication. Enter any character like `X`.

1. Click **Create** or **Sign in** to establish the connection.

1. Once connected, configure the **Create a ticket** action with these values:

   | Field | Value |
   |-------|-------|
   | Subject | Click in the field, then click the **lightning bolt (⚡)** icon, select **Subject** from Dynamic content |
   | Description | Click in the field, then click the **lightning bolt (⚡)** icon, select **Description** from Dynamic content |
   | Email | <inject key="AzureAdUserEmail"></inject> |
   | Priority | 2 (Medium) |
   | Status | 2 (Open) |

   ![](../media/ex9-ticket-config.png)

   >**Tip:** For Subject and Description fields, use the Dynamic content panel to map the input variables from the trigger.

1. Click **+ New step** after the Create a ticket action.

1. Search for **Respond to Copilot** and select it.

   ![](../media/ex9-respond-copilot.png)

1. In the **Respond to Copilot** action, click **+ Add an output**:

   | Field | Value |
   |-------|-------|
   | Type | Text |
   | Name | TicketStatus |
   | Value | Ticket created successfully. Our IT team will contact you shortly. |

   ![](../media/ex9-respond-output.png)

1. Click **Save** in the top-right corner to save the flow.

   ![](../media/ex9-save-flow.png)

1. Click **Publish** to publish the flow so it's available to the agent.

   ![](../media/ex9-publish-flow.png)

1. After publishing, click on the flow name at the top and rename it to:

   ```
   Freshdesk
   ```

   ![](../media/ex9-rename-flow.png)

1. **Test the flow manually** (optional but recommended):

   - Click **Test** in the top-right corner
   - Select **Manually**
   - Enter test values:
     - Subject: `Test Ticket from Copilot`
     - Description: `This is a test ticket to verify the Freshdesk integration.`
   - Click **Run flow**

   ![](../media/ex9-test-flow.png)

1. Verify the flow runs successfully (all green checkmarks).

1. **Verify in Freshdesk:**
   - Switch to your Freshdesk browser tab
   - Go to **Tickets** from the left menu
   - You should see the test ticket you just created!

   ![](../media/ex9-freshdesk-ticket.png)

   >**Success!** Your Freshdesk integration is working. Return to Copilot Studio for the next task.

### Task 4: Create CreateSupportTicket Topic

In this task, you will create a simple topic that directly creates support tickets in Freshdesk. This topic accepts a Subject and Description from the user and passes them to the Freshdesk flow.

1. In Copilot Studio, ensure you are in the **IT Support Copilot**.

1. Click on **Topics** in the left navigation panel.

   ![](../media/ex9-topics-nav.png)

1. Click **+ Add a topic** and select **Create from description with Copilot**.

   ![](../media/ex9-add-topic.png)

1. Enter the following details:

   **Name:**
   ```
   CreateSupportTicket
   ```

   **Description:**
   ```
   Create a simple support ticket topic. Ask the user for the ticket subject and save it as a variable. Then ask them to describe their issue in detail and save that as another variable. After collecting both values, call the Freshdesk Power Automate flow and pass the subject variable to the Subject input and the description variable to the Description input. After the ticket is created, display a confirmation message saying the ticket has been created and IT team will contact them shortly.
   ```

   ![](../media/ex9-create-ticket-topic.png)

1. Click **Create** to generate the topic.

1. Wait for the AI to generate the topic (15-30 seconds).

1. Review the generated topic:

   - **Trigger phrases:** Verify it includes phrases like:
     - "Create a ticket"
     - "Open a support ticket"
     - "I need to create a ticket"
     - "Submit a ticket"
     - "Log a ticket"

1. Review the conversation flow and ensure it:
   - Asks for the ticket subject and saves as `Subject` variable
   - Asks for issue description and saves as `Description` variable
   - Calls the Freshdesk flow with these variables

1. **Connect the topic to the Freshdesk flow:**

   - Locate the point after both variables are collected
   - Click the **+** button
   - Select **Add a tool** (or **Call an action**)

   ![](../media/ex9-add-tool.png)

1. In the tool selection pane:
   - Search for **Freshdesk**
   - Select your **Freshdesk** flow from the list

   ![](../media/ex9-select-freshdesk.png)

1. Configure the flow inputs by mapping the variables:

   - For **Subject**: Click the **{x}** icon and select the **Subject** variable
   - For **Description**: Click the **{x}** icon and select the **Description** variable

   ![](../media/ex9-map-ticket-variables.png)

   >**Important:** The variable names must match exactly. If your variables have different names, rename them in the Question nodes to `Subject` and `Description`.

1. Add a **Message** node after the action:
   ```
   I've created your support ticket successfully. Our IT team will contact you shortly.
   ```

1. Click **Save** to save the topic.

   ![](../media/ex9-save-topic.png)

### Task 5: Create CredentialResetSupport Topic

In this task, you will create a topic using generative AI that helps users with password reset issues and escalates to Freshdesk when needed.

1. Click **+ Add a topic** and select **Create from description with Copilot**.

1. Enter the following details:

   **Name:**
   ```
   CredentialResetSupport
   ```

   **Description:**
   ```
   Help users who need password reset assistance when they forget their password or their account becomes locked. Ask the user for their username and save it as a variable. Use generative answers to provide self-service reset instructions by referring to the uploaded knowledge sources whenever possible. After sharing the steps, ask the user whether they were able to reset their password successfully. If not, offer to create a support ticket. When creating the ticket, generate a subject line such as "Password Reset Assistance – <username>" and create a detailed description that includes the username and the reason they were unable to reset the password. Map these values to the Freshdesk Power Automate flow inputs for Subject and Description so the flow receives the correct variables. This topic should act as a guided password-reset helper that uses the knowledge base first, and escalates to ticket creation only when needed.
   ```

   ![](../media/ex9-credential-topic.png)

1. Click **Create** to generate the topic.

1. Wait for the AI to generate the topic (15-30 seconds).

1. Review the generated topic:

   - **Trigger phrases:** Verify it includes phrases like:
     - "I forgot my password"
     - "Reset my password"
     - "Account locked"
     - "Can't log in"
     - "Password reset"

   ![](../media/ex9-credential-triggers.png)

1. Review the conversation flow and ensure it:
   - Asks for username and saves as variable
   - Provides self-service reset instructions using knowledge base
   - Asks if issue is resolved
   - Offers ticket creation if not resolved

1. **Connect the topic to the Freshdesk flow:**

   - Locate the point in the conversation where the user indicates the issue is NOT resolved
   - Click the **+** button at that escalation point
   - Select **Add a tool** (or **Call an action**)
   - Search for **Freshdesk** and select your flow
   - Map the generated Subject and Description variables to the flow inputs

   ![](../media/ex9-add-tool.png)

1. Add a **Message** node after the action:
   ```
   I've created a support ticket for your password reset request. Our IT team will contact you shortly.
   ```

1. Click **Save** to save the topic.

   ![](../media/ex9-save-topic.png)

### Task 6: Create VPNConnectivitySupport Topic

In this task, you will create a topic for VPN and connectivity issues.

1. Click **+ Add a topic** > **Create from description with Copilot**.

1. Enter the following:

   **Name:**
   ```
   VPNConnectivitySupport
   ```

   **Description:**
   ```
   Assist users experiencing VPN or general internet connectivity issues. Ask the user what exact problem or error message they are seeing and save that response as a variable. Ask where the user is working from, such as home, office, or another location, and save that as another variable. Provide basic troubleshooting steps including checking internet connection, verifying Wi-Fi status, restarting the VPN client, checking login credentials, reconnecting to the network, and any other basic connectivity checks. After giving these steps, ask the user whether the issue is resolved. If the user says no, offer to create a support ticket. When creating the ticket, generate a subject line using the location variable, for example "Connectivity Issue – <location>," and generate a detailed description that includes the user's reported error message and the location information. Map these values to the Freshdesk Power Automate flow inputs for Subject and Description so the flow receives the correct variables. This topic should handle all VPN and internet issues but exclude hardware problems, as those are handled in another topic.
   ```

   ![](../media/ex9-vpn-topic.png)

1. Click **Create** to generate the topic.

1. Review and verify trigger phrases include:
   - "VPN not connecting"
   - "VPN authentication failed"
   - "Can't connect to VPN"
   - "Internet not working"
   - "Connectivity issues"
   - "Network problems"

1. Review the conversation flow and ensure it:
   - Asks about error message and saves as variable
   - Asks about location (home/office) and saves as variable
   - Provides troubleshooting steps
   - Asks if issue is resolved
   - Offers ticket creation if not resolved

1. **Connect the topic to the Freshdesk flow:**
   - Find the escalation point where user says issue is NOT resolved
   - Click **+** > **Add a tool** > Select **Freshdesk**
   - Map the Subject and Description variables to the flow inputs

1. Add a confirmation message:
   ```
   I've created a support ticket for your connectivity issue. Our IT team will contact you shortly.
   ```

1. Click **Save**.

### Task 7: Create HardwareSupportAssistant Topic

In this task, you will create a comprehensive topic for hardware issues.

1. Click **+ Add a topic** > **Create from description with Copilot**.

1. Enter the following:

   **Name:**
   ```
   HardwareSupportAssistant
   ```

   **Description:**
   ```
   Create a hardware support topic that handles all common device issues, including laptops, mice, keyboards, monitors, printers, headphones, docking stations, network adapters, and any other device. Begin by asking the user which device they are having trouble with and save this selection as a variable, then ask them to describe the issue in their own words and save that as another variable. Provide troubleshooting steps based on the selected device: for laptops, include steps for slow performance, freezing, overheating, slow boot, high CPU or memory usage, updates, restart, disk cleanup, and malware checks; for printers, include steps for offline issues, paper jams, blank pages, print queue problems, restarting the spooler, reconnecting cables, reloading paper, and power cycling; for mice and keyboards, include USB or Bluetooth checks, battery checks, driver checks, cleaning stuck keys, and re-pairing; for monitors, include steps for no display, flickering, resolution problems, cable or port checks, brightness and power checks; for headphones and microphones, include audio settings, mic testing, Bluetooth reconnecting, resetting, and driver updates; and for docking stations or network adapters, include cable checks, restarting the dock, firmware checks, and adapter resets. For any "other device," provide general troubleshooting such as checking cables, restarting the device, and verifying drivers. After the troubleshooting steps, ask the user whether the issue is resolved. If not, offer to create a support ticket. When creating the ticket, generate a subject like "Hardware Issue – <device>" and a description that includes the user's reported issue details and device type, and map these values to the Freshdesk Power Automate flow as the Subject and Description inputs.
   ```

   ![](../media/ex9-hardware-topic.png)

1. Click **Create** to generate the topic.

1. Review and verify trigger phrases include:
   - "My laptop is slow"
   - "Printer not working"
   - "Mouse not responding"
   - "Keyboard issue"
   - "Monitor problems"
   - "Hardware issue"
   - "Device not working"

1. Review the conversation flow and ensure it:
   - Asks which device and saves as variable
   - Asks to describe the issue and saves as variable
   - Provides device-specific troubleshooting steps
   - Asks if issue is resolved
   - Offers ticket creation if not resolved

1. **Connect the topic to the Freshdesk flow:**
   - Find the escalation point where user says issue is NOT resolved
   - Click **+** > **Add a tool** > Select **Freshdesk**
   - Map the Subject and Description variables to the flow inputs

1. Add a confirmation message:
   ```
   I've created a support ticket for your hardware issue. Our IT team will contact you shortly.
   ```

1. Click **Save**.

1. **Verify all topics are enabled:**
   - In the **Topics** list, ensure all 4 topics show as enabled (toggle is on):
     - CreateSupportTicket
     - CredentialResetSupport
     - VPNConnectivitySupport
     - HardwareSupportAssistant

   ![](../media/ex9-topics-list.png)

## Summary

In this exercise, you successfully integrated Freshdesk as a professional ticketing system with your IT Support Copilot. You learned how to:

- Set up a Freshdesk free trial account for IT ticketing
- Obtain and configure API credentials for secure integration
- Create an agent flow using the Freshdesk connector to automatically create tickets
- Build a dedicated CreateSupportTicket topic for direct ticket creation
- Build intelligent troubleshooting topics using generative AI (CredentialResetSupport, VPNConnectivitySupport, HardwareSupportAssistant)
- Connect topics to the Freshdesk flow for seamless ticket escalation
- Map topic variables to flow inputs (Subject and Description)

Your IT Support Copilot can now provide troubleshooting guidance using the knowledge base, and when users need escalation, automatically create support tickets in Freshdesk with all the relevant details.

In the next exercise, you will test the complete solution end-to-end and deploy it to Microsoft Teams.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
