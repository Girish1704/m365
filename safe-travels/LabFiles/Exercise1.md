# Exercise 1: Create Safe Travels Agent and Deploy to Microsoft Teams

### Estimated Duration: 30 Minutes

## Overview

In this foundational exercise, you'll create your first AI agent using Microsoft Copilot Studio's Safe Travels template. This is a practical, hands-on introduction to conversational AI that will give you a working travel assistant agent deployed to Microsoft Teams by the end of 30 minutes.

The Safe Travels agent will help employees with travel-related questions, policy information, and guidance. You'll see how easy it is to create powerful AI agents using templates, test them thoroughly, and deploy them to your organization's collaboration platform. This exercise focuses on getting you comfortable with the core agent development workflow that applies to any business scenario.

## Objectives

You will be able to complete the following tasks:

- Task 1: Set up Power Platform environment and navigate to Copilot Studio
- Task 2: Create Safe Travels agent from template  
- Task 3: Test and validate agent functionality
- Task 4: Publish and deploy agent to Microsoft Teams

## Prerequisites

- Access to **Microsoft Copilot Studio** with agent creation permissions
- **Microsoft Teams** access for testing deployed agents
- **Admin tenant credentials** for publishing to enterprise channels
- Basic understanding of conversational AI and Microsoft 365 collaboration tools

## Task 1: Set Up Power Platform Environment

In this task, you will set up the Power Platform environment that will support your Copilot Studio agents with the necessary data sources and knowledge files.

1. Inside the **Power Apps** portal, select **Tables (1)** from the left navigation menu and click **Create with Excel or .CSV file (2)** to begin importing the lab dataset.

   ![](../media/ex1-travel-g1.png)

   > **Environment Foundation:** This step creates the foundational environment that will support your agents with company-specific data and knowledge sources.

1. In the **Create in new environment?** dialog, click **Create** to provision a environment.

   ![](../media/ex1-travel-g2.png)

1. When the upload screen appears, click **Select from device**.

   ![](../media/cor-g-g2.png)

1. In the file picker dialog:
   - Navigate to **`C:\datasets\Safe-Travels-Agent-Automate`(1)**.
   - Select **Leave balance Tracker.xlsx (2)**.
   - Click **Open (3)** to add the file.

      ![](../media/cor-g-g1.png)

1. Check the preview: columns **Employee ID**, **Firstname**, **Lastname**, **Leave Balance** are correct and header toggle is ON, then click **Create**.

   ![](../media/ex1-travel-g3.png)

1. Still in Power Platform, click the **environment (1)** name in the top bar , expand **Build apps with Dataverse (2)**, and select your newly created **ODL_User (3)** to switch context to the new environment you just provisioned.

   ![](../media/ex1-travel-g5.png)

1. After provisioning completes, open **Tables (1)** and confirm the **Employee (2)** table is listed; note the logical **prefix (3)** which uniquely identifies the table for future automation (not used further in this lab).

   ![](../media/ex1-travel-g4.png)

   > **Tip:** If the **Employee** table isn't visible, verify you've switched to **ODL_User <inject key="Deployment ID" enableCopy="false"></inject>'s Environment**.

1. Navigate to **Microsoft Copilot Studio** by opening a new browser tab and using the link below:

   ```
   https://copilotstudio.microsoft.com
   ```

1. On the **Welcome to Microsoft Copilot Studio** screen, keep the default **country/region** selection and click **Get Started** to continue.

   ![](../media/gs-travel-g2.png)

1. If the **Welcome to Copilot Studio!** pop-up appears, click **Skip** to continue to the main dashboard.

   ![](../media/gs-travel-g3.png)

1. If you are directly taken to the **agent creation** screen, click the **ellipsis (1)** icon beside the **Create** button, then select **Cancel agent creation (2)** to return to the main dashboard.

   ![](../media/gs-travel-g4.png)

1. In Copilot Studio, open the environment picker **(1)**, expand **Supported environments (2)**, and select **ODL_User <inject key="Deployment ID" enableCopy="false"></inject>'s Environment (3)** to switch.

   ![](../media/ex1-travel-g6.png)

1. If you are not able to see the environment under **Supported environments**, follow the below steps.

   ![](../media/cor2-gs-g4.png)

   1. Go back to the **Power Apps** portal, on your **ODL_User <inject key="Deployment ID" enableCopy="false"></inject>’s Environment** copy the **Environment ID** from the browser URL as highlighted.

      ![](../media/cor2-gs-g5.png)
   
   1. Open a **new browser tab**, and paste the copied **Environment ID** at the end of the following URL to verify access:

      ```
      https://copilotstudio.microsoft.com/environments/(Environment ID)
      ```

      ![](../media/cor2-gs-g6.png)

      > **Note:** Replace **(Environment ID)** with the ID you copied in the previous step.
   
   1. You will be navigated to the **Copilot Studio** portal. Verify that **ODL_User <inject key="Deployment ID" enableCopy="false"></inject>’s Environment** is visible and selected under **Supported environments**.

      ![](../media/cor2-gs-g7.png)

## Task 2: Create Safe Travels & Leave Manager Agents

In this task, you will create two AI agents the **Safe Travels Agent** to assist with travel-related queries and the **Leave Manager Agent** to manage employee leave information and approvals. This helps you understand how to quickly build and customize multiple agents for different business scenarios.

1. In Copilot Studio, click **Create (1)** and select the **Safe Travels (2)** template card.

   ![](../media/ex1-travel-g7.png)

   > **Note:** If the template isn’t visible, use the search box.
   
1. Configure your Safe Travels agent with the following details:

   - Enter **Name (1):** `Safe Travels Agent`
   - Enter **Description (2):** `A travel assistant agent that helps employees with travel planning, policies, and guidance`
   - Click **Create (3)** to generate the agent.

      ![](../media/ex1-travel-g8.png)

1. After clicking **Create**, verify the green success banner **"Your agent has been provisioned."** appears and the **Overview** tab loads.

   ![](../media/ex1-travel-g9.png)

   > **Template Benefits:** Safe Travels ships with pre-configured travel flows and knowledge, reducing setup time.

1. On **Overview (1)** click **+ Add knowledge (2)** to begin attaching internal travel policy content.

   ![](../media/ex1-travel-g10.png)

   > **Note** Adding knowledge sources improves grounded responses; keep policy files updated for accuracy.

1. On the **Add knowledge** screen, click **select to browse** to upload a knowledge file.  

   ![](../media/cor-g-g3.png)

1. In the file picker window, navigate to the folder **C:\datasets\Safe-Travels-Agent-Automate (1)**, select the **Travel Policy (2)** Word document file, and then click **Open (3)**.

   ![](../media/cor-g-g4.png)

1. After the file is uploaded successfully, click **Add to agent** to include the document as a knowledge source for your agent.

      ![](../media/ex1-travel-g11.png)

1. The system will process your agent creation. **Provisioning may take 10–15 minutes, please proceed to the next step while it completes.

   ![](../media/ex1-travel-g12.png)

   ![](../media/ex1-travel-g13.png)

1. Navigate to **Copilot Studio**, click **Agents (1)** and then select **+ New agent (2)** to create the specialized Leave Manager agent.

   ![](../media/ex2-travel-g68.png)

1. Create the **Leave Manager Agent** as follows:  
   - **Configure (1):** Click the **Configure** tab to set up your agent details.  
   - **Name (2):** Enter **Leave Manager Agent**.  
   - **Description (3):** Type `This agent is to track the leaves of all the employees, their leave balance and leave history to approve or reject any new leave requests.`  
   - **Instructions (4):** Type `Track the leaves of employees. Track their leave balance. Apply/Reject leaves based on their balance.`  
   - **Create (5):** Click **Create** to build the agent.  

      ![](../media/cor-g-g9.png)

      > **Agent Specialization:** Creating domain-specific agents allows for better accuracy, focused training, and more relevant responses for specific business functions.

1. Navigate to the **Overview (1)** tab and click **Add knowledge (2)** to include organizational data sources that will enhance your agent's leave management capabilities.

   ![](../media/ex2-travel-g70.png)

1. Click **select to browse** to upload the leave management documentation that will serve as the knowledge foundation for your agent.

   ![](../media/ex2-travel-g71.png)

1. In the file picker window, navigate to the folder **C:\datasets\Safe-Travels-Agent-Automate (1)**, select the files **Leave balance Tracker.xlsx (2)**, and then click **Open (3)**.

   ![](../media/cor-g-g7.png)

1. Upload the required leave policy and tracking files, then click **Add to agent** to integrate them as authoritative knowledge sources.

   ![](../media/cor-g-g8.png)

1. Verify that all uploaded knowledge sources display **Ready** status, confirming successful integration and availability for agent responses.

   ![](../media/cor-g-g10.png)

   ![](../media/cor-g-g24.png)

   > **Note:** It may take 10–15 minutes for all knowledge sources to show the **Ready** status. You can proceed with the next task while the processing completes.

   > **Knowledge Integration:** Successfully uploaded knowledge sources enable your agent to provide accurate, policy-compliant responses based on your organization's actual leave management data.

## Task 3: Test and Validate Agent Functionality

In this task, you'll test your Safe Travels agent to validate its functionality and responses to travel-related queries.

1. From the left navigation menu, click **Agents (1)**, and then select **Safe Travels Agent (2)** from the list to open it.

   ![](../media/ex2-travel-g111.png)

1. Verify that the uploaded knowledge source shows the **Ready** status as highlighted.

   ![](../media/ex1-travel-g13.png)

   > **Note:** If the status is not yet **Ready**, you can continue with the next steps. However, the agent's responses may not reflect the latest data until the knowledge source is fully processed.

   > **Note:** It is recommended that you proceed to the next tasks and perform them. Once the knowledge source is fully processed, you can return later to retest the agent for improved and accurate responses during future interactions.

1. Click **Test** to open the test panel and verify your agent’s responses.

   ![](../media/ex1-travel-g14.png)

1. In the test chat window, start by testing the agent's passport information capabilities. Type the following query:

   ```
   How to apply for passport?
   ```

   ![](../media/ex1-travel-g16.png)

   > **Expected Response:** The agent should provide comprehensive passport application information from its built-in travel knowledge base.
   
   ![](../media/ex1-travel-g17.png)

   > **Note:** The output may vary if the knowledge source (Word file) is still processing. This is expected behavior. You can continue with the next task you’ll be interacting with the agent again in the upcoming tasks once the knowledge source is fully ready.

1. Test another travel-related query to validate the agent's knowledge. Ask about travel Policy and review the output.

   ```
   What is our company travel policy?
   ```
   ![](../media/ex1-travel-g18.png)
   
1. Continue testing with additional travel scenarios to ensure the agent responds appropriately to various travel-related questions.

   > **Knowledge Integration:** The agent leverages its built-in travel knowledge to provide helpful responses across various travel scenarios.

## Task 4: Publish and Deploy Agent to Microsoft Teams

In this task, you will publish your Safe Travels agent and deploy it to Microsoft Teams, making it accessible to your organization's employees.

1. After testing, click the **Publish** button in the top-right corner of the agent interface to begin the publishing process.

   ![](../media/ex1-travel-g21.png)

1. In the publish dialog, review the publishing details and click **Publish** to confirm and publish your agent.

   ![](../media/ex1-travel-g27.png)

   > **Publishing Process:** The agent will be packaged and made available for channel deployment. This process may take a few moments to complete.

1. Open a new browser tab and navigate to Microsoft Teams using the link below:

   ```
   https://teams.microsoft.com/v2/
   ``` 

1. If you see a "Get to know Teams" welcome screen, click **Get Started** to proceed.

   ![](../media/ex1-travel-g22.png)

1. If prompted with a Teams mobile app QR code popup, click the **X** button to close it and continue.

   ![](../media/ex1-travel-g23.png)

1. If prompted to sign in, enter your **email address (1)** and click **Next (2)**.

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

      ![](../media/ex1-travel-g24.png)

1. Enter the **Temporary Access Pass (1)** and click **Sign in (2)**.

   - **Temporary Access Pass:** <inject key="AzureAdUserPassword"></inject>

      ![](../media/ex1-travel-g25.png)

1. When prompted to stay signed in, click **Yes** to continue.

   ![](../media/ex1-travel-g26.png)

1. Once published successfully, navigate to the **Channels** section to configure deployment channels for your agent.

   ![](../media/ex1-travel-g28.png)

1. In the Channels interface, you'll see available deployment options. Select **Microsoft Teams** to deploy your agent to Teams.

   ![](../media/ex1-travel-g29.png)

   > **Channel Benefits:** Deploying to Microsoft Teams provides users access through their familiar collaboration environment, increasing adoption and usage.

1. In the **Teams and Microsoft 365 Copilot** window, select the checkbox **Make agent available in Microsoft 365 Copilot (1)**, and then click **Add channel (2)**.

   ![](../media/ex1-travel-g30.png)

1. Once the channel is added successfully, click **See agent in Teams** to open and test the agent within Microsoft Teams.

   ![](../media/cor2-gs-g2.png)

1. If prompted to download the Teams desktop app, click **Use the web app instead** to continue using Teams in your browser.

   ![](../media/ex1-travel-g34.png)

1. In the Safe Travels Agent dialog, review the agent information and click **Add** to install the agent in your Teams environment.

   ![](../media/ex1-travel-g35.png)

1. After successful installation, you'll see a confirmation message. Click **Open** to start using your Safe Travels Agent immediately.

   ![](../media/ex1-travel-g36.png)

1. The Safe Travels Agent chat interface will open. Type your first message in the text box (1) and click the **Send** button (2) to test the agent.

   ![](../media/ex1-travel-g39.png)

1. The **Safe Travels Agent** chat interface will open. Type your first message in the text box **(1)** and click the **Send** button **(2)**.

   ![](../media/ex1-travel-g40.png)

1. To start interacting with the agent. Ask a few travel-related questions and review the agent’s responses.

## Summary

you've successfully:

- Set up a Power Platform environment for agent development
- Created a working Safe Travels agent using Microsoft's template
- Tested the agent's travel assistance capabilities with real queries
- Published and deployed the agent to Microsoft Teams for your organization

Your Safe Travels agent is now live and ready to help employees with travel questions, passport information, and destination guidance. You've experienced the power of low-code AI development - creating enterprise-ready conversational agents without any programming.

### You have successfully completed Exercise 1. Click **Next >>** to continue to Exercise 2.
