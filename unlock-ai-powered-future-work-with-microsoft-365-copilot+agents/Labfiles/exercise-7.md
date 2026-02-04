# Exercise 7: Build a Poetic Declarative Agent Using Microsoft 365 Agents Toolkit

## Estimated Duration: 90 Minutes

## Overview

In this exercise, you will use the Microsoft 365 Agents Toolkit extension for Visual Studio Code to build a declarative agent. Declarative agents are custom Copilot agents defined through a manifest and configuration files, allowing developers to create specialized agents without extensive coding.

You will create a "Poetic Assistant" - a creative agent that helps users express ideas through poetry, generate creative writing, and explore different poetic styles.

## Prerequisites

- Visual Studio Code installed on your VM
- Microsoft 365 Agents Toolkit extension
- Node.js installed on your VM

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Install and configure Microsoft 365 Agents Toolkit
- Task 2: Create a new declarative agent project
- Task 3: Configure the agent manifest
- Task 4: Define agent instructions and capabilities
- Task 5: Test the declarative agent locally

### Task 1: Install and Configure Microsoft 365 Agents Toolkit

In this task, you will install the Microsoft 365 Agents Toolkit extension in Visual Studio Code.

1. In the VM, open **Visual Studio Code** from the desktop or Start menu.

   ![](./media/ex7-open-vscode.png)

1. Click on the **Extensions** icon in the left sidebar (or press `Ctrl+Shift+X`).

   ![](./media/ex7-extensions-icon.png)

1. In the search box, type `Microsoft 365 Agents Toolkit`.

   ![](./media/ex7-search-toolkit.png)

1. Click **Install** on the **Microsoft 365 Agents Toolkit** extension.

   ![](./media/ex7-install-toolkit.png)

1. Wait for the installation to complete. Once installed, you will see the Microsoft 365 Agents Toolkit icon in the left sidebar.

   ![](./media/ex7-toolkit-icon.png)

1. Click on the **Microsoft 365 Agents Toolkit** icon in the sidebar.

   ![](./media/ex7-toolkit-sidebar.png)

1. In the toolkit panel, click **Sign in to Microsoft 365** to authenticate.

   ![](./media/ex7-signin-button.png)

1. When the browser opens for authentication, sign in with your lab credentials:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex7-browser-signin.png)

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. After successful authentication, close the browser tab and return to VS Code.

   ![](./media/ex7-signin-success.png)

   >**Note:** You should see your account information in the Agents Toolkit panel confirming successful sign-in.

### Task 2: Create a New Declarative Agent Project

In this task, you will create a new declarative agent project using the toolkit.

1. In the Microsoft 365 Agents Toolkit panel, click **Create a New App**.

   ![](./media/ex7-create-new-app.png)

1. Select **Agent** from the project type options.

   ![](./media/ex7-select-agent.png)

1. Select **Declarative Agent** as the agent type.

   ![](./media/ex7-declarative-agent.png)

1. Choose **No plugin** for this exercise (we'll focus on the agent's conversational abilities).

   ![](./media/ex7-no-plugin.png)

1. Select **Default folder** when prompted for the project location.

   ![](./media/ex7-folder-name.png)

1. Enter the application name when prompted:

   ```
   PoeticAssistant
   ```

   ![](./media/ex7-app-name.png)

1. Wait for the project scaffolding to complete. VS Code will open the new project in a new window.

   ![](./media/ex7-project-created.png)

1. If a prompt appears regarding the trustworthiness of the source, click on **Yes, I trust the authors**.

1. Explore the project structure:

   ```
   PoeticAssistant/
   ├── appPackage/
   │   ├── declarativeAgent.json    # Agent configuration
   │   ├── manifest.json            # App manifest
   │   └── color.png / outline.png  # App icons
   ├── .vscode/
   │   └── settings.json / tasks.json
   └── README.md
   ```

   ![](./media/ex7-project-structure.png)

1. Now select the **Microsoft 365 Agents Toolkit** icon on the left sidebar. Under **Accounts**, click **Sign in to Microsoft 365** and log in with your lab credentials.

   ![](./media/ex7-signin-button.png)

1. A browser window will pop up and offer to log into Microsoft 365. Sign in with your lab credentials:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. Once the sign-in is complete, a confirmation message stating "You are signed in now and close this page." will be displayed. After that, return to Visual Studio Code.

1. Verify that the **Copilot Access** checker has a green checkmark in the Agents Toolkit panel.

   ![](./media/ex7-signin-success.png)

   >**Note:** Ensure you are signed in before proceeding to the next tasks.

### Task 3: Configure the Agent Manifest

In this task, you will configure the declarative agent manifest to define the Poetic Assistant.

1. In VS Code, open the `appPackage/manifest.json` file.

   ![](./media/ex7-open-manifest.png)

1. Update the manifest with the following information:

   ```json
   {
     "$schema": "https://developer.microsoft.com/json-schemas/teams/vDevPreview/MicrosoftTeams.schema.json",
     "manifestVersion": "devPreview",
     "version": "1.0.0",
     "id": "${{TEAMS_APP_ID}}",
     "developer": {
       "name": "Contoso Labs",
       "websiteUrl": "https://www.contoso.com",
       "privacyUrl": "https://www.contoso.com/privacy",
       "termsOfUseUrl": "https://www.contoso.com/terms"
     },
     "icons": {
       "color": "color.png",
       "outline": "outline.png"
     },
     "name": {
       "short": "Poetic Assistant",
       "full": "Poetic Assistant - Creative Writing Copilot"
     },
     "description": {
       "short": "A creative writing assistant that helps you express ideas through poetry",
       "full": "The Poetic Assistant is a declarative agent that helps users create poetry, explore different poetic forms, and express their thoughts in creative and artistic ways. It understands various poetic styles including haiku, sonnet, limerick, free verse, and more."
     },
     "accentColor": "#8B4513",
     "copilotAgents": {
       "declarativeAgents": [
         {
           "id": "poeticAssistant",
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

   ![](./media/ex7-manifest-updated.png)

1. Save the file (`Ctrl+S`).

### Task 4: Define Agent Instructions and Capabilities

In this task, you will configure the declarative agent's personality and capabilities.

1. Open the `appPackage/declarativeAgent.json` file.

   ![](./media/ex7-open-declarative.png)

1. Replace the content with the following configuration:

   ```json
   {
     "$schema": "https://developer.microsoft.com/json-schemas/copilot/declarative-agent/v1.2/schema.json",
     "version": "v1.2",
     "name": "Poetic Assistant",
     "description": "A creative writing companion that helps you craft beautiful poetry and explore the art of verse",
     "instructions": "You are the Poetic Assistant, a creative writing companion with a deep love for poetry and artistic expression. Your role is to help users express their thoughts, emotions, and ideas through the beautiful art of poetry.\n\n## Your Personality:\n- You are warm, encouraging, and appreciative of creative efforts\n- You speak with eloquence and occasionally use poetic language yourself\n- You celebrate the beauty in every attempt at creative expression\n- You are patient and supportive with beginners while challenging experienced writers\n\n## Your Expertise:\n- You understand various poetic forms: haiku, sonnet, limerick, free verse, acrostic, villanelle, ode, elegy, and more\n- You can explain meter, rhyme schemes, and literary devices\n- You understand metaphor, simile, personification, alliteration, and other poetic techniques\n- You know poetry from various cultures and time periods\n\n## How You Help:\n1. **Creating Poetry**: Help users write poems based on their themes, emotions, or ideas\n2. **Teaching Forms**: Explain different poetic structures and when to use them\n3. **Improving Work**: Offer constructive feedback on user's poetry\n4. **Finding Inspiration**: Suggest prompts, themes, and creative exercises\n5. **Exploring Styles**: Introduce users to different poetic traditions and famous poets\n\n## Guidelines:\n- Always encourage creative expression, even in imperfect forms\n- Offer multiple variations when creating poetry\n- Explain the 'why' behind your suggestions\n- Respect the user's creative vision while offering improvements\n- Make poetry accessible and fun, not intimidating\n\n## Example Interactions:\n- 'Write a haiku about autumn' -> Create a thoughtful haiku with explanation\n- 'Help me express sadness in a poem' -> Offer multiple approaches and styles\n- 'What is iambic pentameter?' -> Explain with examples and offer to practice\n- 'Review my poem' -> Provide encouraging, constructive feedback",
     "conversation_starters": [
       {
         "title": "Write a Haiku",
         "text": "Help me write a haiku about nature"
       },
       {
         "title": "Learn Poetry Forms",
         "text": "What are different types of poetry I can try?"
       },
       {
         "title": "Get Inspired",
         "text": "Give me a creative writing prompt for poetry"
       },
       {
         "title": "Express an Emotion",
         "text": "Help me write a poem about feeling hopeful"
       },
       {
         "title": "Review My Work",
         "text": "I wrote a poem and would like your feedback"
       }
     ]
   }
   ```

   ![](./media/ex7-declarative-updated.png)

1. Save the file (`Ctrl+S`).

   >**Note:** The `instructions` field defines the agent's personality, expertise, and behavior. This is similar to a detailed system prompt that shapes how the agent responds.

1. You can delete the `instruction.txt` file from the `appPackage` folder as we have included the instructions directly in the JSON file.

1. Optionally, update the agent icons in the `appPackage` folder:

   - `color.png` - 192x192 pixel color icon
   - `outline.png` - 32x32 pixel outline icon

   For this exercise, you can keep the default icons.

### Task 5: Provision and Test the Declarative Agent

In this task, you will provision the agent and test it in Microsoft 365 Copilot.

1. In VS Code, click on the **Microsoft 365 Agents Toolkit** icon in the left sidebar.

   ![](./media/ex7-toolkit-sidebar.png)

1. Under **LIFECYCLE**, click on **Provision**.

   ![](./media/ex7-provision-button.png)

1. Wait for the provisioning to complete. You should see a success message in the output panel:

   ```
   (√) Done: Lifecycle stage provision was executed successfully.
   ```

   ![](./media/ex7-provisioning.png)

   >**Note:** The provisioning process packages your app files, validates them, and installs the declarative agent to your Microsoft 365 tenant.

1. Once provisioning is complete, open a browser and navigate to:

   ```
   https://m365.cloud.microsoft/chat
   ```

1. If prompted, sign in with your lab credentials:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. In the Copilot chat, look for your **Poetic Assistant** in the right pane or agents panel and select it.

   ![](./media/ex7-agent-preview.png)

1. Test the Poetic Assistant with various prompts:

   **Test 1 - Write a Haiku:**

   **Prompt:**
   ```
   Write a haiku about the morning sun
   ```

   **Expected Response:**

   The agent should create a haiku following the 5-7-5 syllable pattern with gentle morning imagery.

1. **Test 2 - Explain a Poetry Form:**

   **Prompt:**
   ```
   What is a sonnet and how do I write one?
   ```

   **Expected Response:**

   The agent should explain the sonnet structure (14 lines, rhyme schemes like ABAB CDCD EFEF GG), iambic pentameter, and provide step-by-step guidance on writing one.

1. **Test 3 - Creative Expression:**

   **Prompt:**
   ```
   Help me write a poem about the feeling of accomplishment after completing a difficult task
   ```

   **Expected Response:**

   The agent should offer multiple poem styles (free verse, rhyming, dramatic) celebrating the feeling of triumph and achievement.

1. **Test 4 - Review Poetry:**

   **Prompt:**
   ```
   Here is my poem, please review it:
   
   The silent moon watches over me
   As stars dance in the velvet sky
   I wonder what they all might see
   As night's soft curtain slowly drifts by
   ```

   **Expected Response:**

   The agent should provide warm, constructive feedback highlighting what works well (imagery, rhythm, mood) and offer gentle suggestions for improvement.

1. **Test 5 - Learn Techniques:**

   **Prompt:**
   ```
   Teach me about alliteration and give me examples
   ```

   **Expected Response:**

   The agent should explain alliteration (repeating consonant sounds at the beginning of words) with examples like "silent stars shimmer" and "soft shadows slip silently."

   >**Note:** Feel free to explore other conversation starters or ask your own creative questions to test the agent's capabilities.

## Summary

In this exercise, you built a declarative agent using the Microsoft 365 Agents Toolkit. You learned how to:

- Install and configure the Microsoft 365 Agents Toolkit in VS Code
- Sign in to Microsoft 365 and verify Copilot access
- Create a new declarative agent project
- Configure the app manifest with agent metadata
- Define detailed agent instructions and conversation starters
- Provision and test the agent in Microsoft 365 Copilot

Declarative agents provide a powerful way to create specialized Copilot experiences without extensive coding, using configuration and natural language instructions.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
