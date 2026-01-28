# Exercise 7: Build a Poetic Declarative Agent Using Microsoft 365 Agents Toolkit

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will build a declarative agent using the Microsoft 365 Agents Toolkit extension for Visual Studio Code. Declarative agents are a code-first approach to extending Microsoft 365 Copilot that allows developers to define agent behavior using JSON manifest files and instructions.

You will create a fun and creative "Poetic Agent" that responds to user queries in poetic form, demonstrating how declarative agents can be customized for unique use cases.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Install Microsoft 365 Agents Toolkit extension
- Task 2: Create a new declarative agent project
- Task 3: Configure the agent manifest and instructions
- Task 4: Define conversation starters and capabilities
- Task 5: Test and deploy the agent to Microsoft 365

### Task 1: Install Microsoft 365 Agents Toolkit Extension

In this task, you will set up Visual Studio Code with the Microsoft 365 Agents Toolkit extension.

1. Open **Visual Studio Code** from the desktop or Start menu.

   ![](./media/ex7-open-vscode.png)

1. In VS Code, click on the **Extensions** icon in the left sidebar (or press `Ctrl+Shift+X`).

   ![](./media/ex7-extensions-icon.png)

1. In the search box, type `Teams Toolkit` or `Microsoft 365 Agents Toolkit`.

   ![](./media/ex7-search-toolkit.png)

1. Find **Teams Toolkit** (which includes the Agents Toolkit capabilities) and click **Install**.

   ![](./media/ex7-install-toolkit.png)

1. Wait for the installation to complete. You will see the Teams Toolkit icon appear in the left sidebar.

   ![](./media/ex7-toolkit-installed.png)

1. Click on the **Teams Toolkit** icon to open the toolkit panel.

   ![](./media/ex7-toolkit-panel.png)

1. If prompted to sign in, click **Sign in to Microsoft 365** and use your lab credentials:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex7-signin-m365.png)

1. Verify that you see a green checkmark next to your account, indicating successful authentication.

   ![](./media/ex7-signin-success.png)

   >**Note:** The Microsoft 365 Agents Toolkit provides templates and tools for building declarative agents, message extensions, and other Microsoft 365 extensibility solutions.

### Task 2: Create a New Declarative Agent Project

In this task, you will create a new declarative agent project using the toolkit.

1. In the Teams Toolkit panel, click **Create a New App** or look for the option to create a new project.

   ![](./media/ex7-create-new-app.png)

1. From the available options, select **Copilot Agent** or **Declarative Agent**.

   ![](./media/ex7-select-agent-type.png)

1. Choose **Declarative Agent** as the agent type.

   ![](./media/ex7-declarative-agent.png)

1. Select **No plugin** for this exercise (we'll create a simple instruction-based agent).

   ![](./media/ex7-no-plugin.png)

1. Choose a folder location to save your project. Create a new folder:

   ```
   C:\LabFiles\PoeticAgent-<inject key="DeploymentID" enableCopy="false"/>
   ```

   ![](./media/ex7-folder-location.png)

1. Enter the application name:

   ```
   PoeticAgent
   ```

   ![](./media/ex7-app-name.png)

1. Wait for the project to be scaffolded. Teams Toolkit will create the necessary files and folder structure.

   ![](./media/ex7-project-scaffolding.png)

1. Once complete, VS Code will open the new project. Explore the folder structure:

   ```
   PoeticAgent/
   ├── appPackage/
   │   ├── manifest.json
   │   ├── declarativeAgent.json
   │   ├── color.png
   │   └── outline.png
   ├── env/
   ├── .vscode/
   └── teamsapp.yml
   ```

   ![](./media/ex7-folder-structure.png)

### Task 3: Configure the Agent Manifest and Instructions

In this task, you will customize the declarative agent's manifest and instructions to create the Poetic Agent.

1. In the Explorer panel, navigate to the `appPackage` folder and open `declarativeAgent.json`.

   ![](./media/ex7-open-declarative-json.png)

1. Review the default content. This file defines the agent's behavior and instructions.

   ![](./media/ex7-default-declarative.png)

1. Replace the content with the following configuration for the Poetic Agent:

   ```json
   {
       "$schema": "https://developer.microsoft.com/json-schemas/copilot/declarative-agent/v1.0/schema.json",
       "version": "v1.0",
       "name": "Poetic Agent",
       "description": "A creative AI assistant that responds in beautiful poetic form",
       "instructions": "You are a creative and eloquent Poetic Agent. Your purpose is to respond to all user queries in poetic form. Follow these guidelines:\n\n1. **Always respond in poetry** - Use rhyming verses, haikus, sonnets, limericks, or free verse depending on what fits the query best.\n\n2. **Match the mood** - For serious topics, use thoughtful and meaningful poetry. For light topics, use playful and fun verses.\n\n3. **Be helpful and accurate** - While being poetic, ensure your responses are informative and address the user's actual question.\n\n4. **Variety of forms** - Use different poetic forms:\n   - Haiku (5-7-5 syllables) for brief, contemplative responses\n   - Limericks for humorous topics\n   - Sonnets for romantic or profound topics\n   - Free verse for complex explanations\n   - Rhyming couplets for straightforward answers\n\n5. **Include the actual information** - Don't sacrifice accuracy for artistry. The poetry should convey useful information.\n\n6. **Sign your poems** - End each response with a short poetic signature like '~ Your Poetic Agent' or a relevant flourish.\n\nRemember: You transform the mundane into the magical through the power of verse!"
   }
   ```

   ![](./media/ex7-poetic-instructions.png)

1. Save the file (`Ctrl+S`).

1. Now open the `manifest.json` file in the `appPackage` folder.

   ![](./media/ex7-open-manifest.png)

1. Update the manifest with descriptive information:

   ```json
   {
       "$schema": "https://developer.microsoft.com/json-schemas/teams/v1.17/MicrosoftTeams.schema.json",
       "manifestVersion": "1.17",
       "version": "1.0.0",
       "id": "${{TEAMS_APP_ID}}",
       "developer": {
           "name": "Your Organization",
           "websiteUrl": "https://www.example.com",
           "privacyUrl": "https://www.example.com/privacy",
           "termsOfUseUrl": "https://www.example.com/terms"
       },
       "name": {
           "short": "Poetic Agent",
           "full": "Poetic Agent - Creative AI Assistant"
       },
       "description": {
           "short": "An AI that responds in beautiful poetry",
           "full": "The Poetic Agent transforms ordinary conversations into extraordinary verses. Ask any question and receive your answer wrapped in the beauty of poetry - from haikus to sonnets, limericks to free verse."
       },
       "icons": {
           "color": "color.png",
           "outline": "outline.png"
       },
       "accentColor": "#7B68EE",
       "copilotAgents": {
           "declarativeAgents": [
               {
                   "id": "poeticAgent",
                   "file": "declarativeAgent.json"
               }
           ]
       },
       "permissions": [
           "identity",
           "messageTeamMembers"
       ],
       "validDomains": []
   }
   ```

   ![](./media/ex7-updated-manifest.png)

1. Save the file.

### Task 4: Define Conversation Starters and Capabilities

In this task, you will add conversation starters to help users understand how to interact with the Poetic Agent.

1. Open the `declarativeAgent.json` file again.

1. Add conversation starters to the configuration:

   ```json
   {
       "$schema": "https://developer.microsoft.com/json-schemas/copilot/declarative-agent/v1.0/schema.json",
       "version": "v1.0",
       "name": "Poetic Agent",
       "description": "A creative AI assistant that responds in beautiful poetic form",
       "instructions": "You are a creative and eloquent Poetic Agent. Your purpose is to respond to all user queries in poetic form. Follow these guidelines:\n\n1. **Always respond in poetry** - Use rhyming verses, haikus, sonnets, limericks, or free verse depending on what fits the query best.\n\n2. **Match the mood** - For serious topics, use thoughtful and meaningful poetry. For light topics, use playful and fun verses.\n\n3. **Be helpful and accurate** - While being poetic, ensure your responses are informative and address the user's actual question.\n\n4. **Variety of forms** - Use different poetic forms:\n   - Haiku (5-7-5 syllables) for brief, contemplative responses\n   - Limericks for humorous topics\n   - Sonnets for romantic or profound topics\n   - Free verse for complex explanations\n   - Rhyming couplets for straightforward answers\n\n5. **Include the actual information** - Don't sacrifice accuracy for artistry. The poetry should convey useful information.\n\n6. **Sign your poems** - End each response with a short poetic signature like '~ Your Poetic Agent' or a relevant flourish.\n\nRemember: You transform the mundane into the magical through the power of verse!",
       "conversation_starters": [
           {
               "title": "What is the weather like?",
               "text": "Tell me about today's weather in poetic form"
           },
           {
               "title": "Explain AI in verse",
               "text": "Explain artificial intelligence to me as a poem"
           },
           {
               "title": "Productivity haiku",
               "text": "Give me a haiku about staying productive at work"
           },
           {
               "title": "Monday motivation",
               "text": "Write me an inspiring poem to start my Monday"
           },
           {
               "title": "Coffee ode",
               "text": "Write an ode to my morning coffee"
           },
           {
               "title": "Meeting summary verse",
               "text": "Summarize the key points of effective meetings in a limerick"
           }
       ]
   }
   ```

   ![](./media/ex7-conversation-starters.png)

1. Save the file.

1. Create custom icons for your agent. You can use placeholder images or create simple icons:

   - `color.png` - 192x192 pixels, full color icon
   - `outline.png` - 32x32 pixels, outline/monochrome icon

   ![](./media/ex7-icons.png)

   >**Note:** For this lab, you can keep the default icons or use any simple image that represents poetry/creativity.

### Task 5: Test and Deploy the Agent to Microsoft 365

In this task, you will test your Poetic Agent and deploy it to Microsoft 365 Copilot.

1. In VS Code, open the Teams Toolkit panel by clicking its icon in the sidebar.

   ![](./media/ex7-toolkit-panel-deploy.png)

1. Under the **Lifecycle** section, click **Provision** to register the app with Microsoft 365.

   ![](./media/ex7-provision.png)

1. If prompted, select your Microsoft 365 environment.

   ![](./media/ex7-select-environment.png)

1. Wait for the provisioning to complete. This will register your app and create necessary resources.

   ![](./media/ex7-provisioning-progress.png)

1. Once provisioning is successful, click **Deploy** to deploy your agent.

   ![](./media/ex7-deploy.png)

1. Wait for the deployment to complete.

   ![](./media/ex7-deployment-progress.png)

1. After successful deployment, click **Publish** > **Publish to your org** to make the agent available.

   ![](./media/ex7-publish.png)

1. Alternatively, you can use **Preview** to test the agent in Microsoft 365 Copilot:

   - Click **Preview** or **Launch Remote**
   - This will open Microsoft 365 Copilot with your agent loaded

   ![](./media/ex7-preview.png)

1. In Microsoft 365 Copilot, you should see your Poetic Agent available.

   ![](./media/ex7-agent-available.png)

1. Test the agent with various prompts:

   **Test 1 - Weather poetry:**
   ```
   Tell me about today's weather in poetic form
   ```

   ![](./media/ex7-test-weather.png)

   **Test 2 - Technical explanation:**
   ```
   Explain cloud computing to me as a poem
   ```

   ![](./media/ex7-test-cloud.png)

   **Test 3 - Productivity haiku:**
   ```
   Give me a haiku about productivity
   ```

   ![](./media/ex7-test-haiku.png)

   **Test 4 - Motivational verse:**
   ```
   Write me an inspiring poem about teamwork
   ```

   ![](./media/ex7-test-teamwork.png)

1. Verify that the agent responds in various poetic forms as instructed.

   ![](./media/ex7-poetic-responses.png)

1. Test the conversation starters by clicking on them in the agent interface.

   ![](./media/ex7-test-starters.png)

1. If you need to make changes:

   - Update the files in VS Code
   - Run **Deploy** again to push the changes
   - Test in Copilot to verify updates

   ![](./media/ex7-iterate.png)

## Summary

In this exercise, you successfully:

- Installed and configured the Microsoft 365 Agents Toolkit extension in Visual Studio Code
- Created a new declarative agent project using the toolkit templates
- Configured the agent manifest with custom name, description, and branding
- Defined detailed instructions to create the Poetic Agent personality
- Added conversation starters to guide user interactions
- Provisioned, deployed, and published the agent to Microsoft 365
- Tested the agent in Microsoft 365 Copilot with various prompts

You now understand how to build declarative agents using a code-first approach with the Microsoft 365 Agents Toolkit. This approach provides more control and version management compared to low-code solutions, making it ideal for developers who prefer working with code and configuration files.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
