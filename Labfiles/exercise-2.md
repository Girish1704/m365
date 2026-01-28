# Exercise 2: Create and Configure an Agent in Copilot Chat

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will learn how to create and configure a custom agent within Microsoft 365 Copilot Chat. Agents in Copilot are specialized AI assistants that can be tailored to specific tasks, departments, or workflows. By creating custom agents, you can provide focused assistance that understands specific business contexts and can access relevant data sources.

You will create an agent that helps with HR-related queries, demonstrating how to define agent instructions, configure knowledge sources, and test the agent's capabilities.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Navigate to Copilot Agent Builder
- Task 2: Create a new custom agent
- Task 3: Configure agent instructions and persona
- Task 4: Add knowledge sources to the agent
- Task 5: Test and refine the agent

### Task 1: Navigate to Copilot Agent Builder

In this task, you will access the agent creation interface within Microsoft 365 Copilot.

1. In the Microsoft 365 Copilot Chat interface, click on the **Copilot agents** icon or navigate to the agents section.

   ![](./media/ex2-agents-icon.png)

1. In the agents panel, you will see options to:

   - View existing agents
   - Create new agents
   - Access pre-built agents from the gallery

   ![](./media/ex2-agents-panel.png)

1. Click on **Create agent** or **+ New agent** to start building your custom agent.

   ![](./media/ex2-create-agent.png)

   >**Note:** Agent creation in Copilot Chat allows you to build lightweight agents quickly. For more complex agents with advanced capabilities, you would use Microsoft Copilot Studio.

### Task 2: Create a New Custom Agent

In this task, you will create a new agent and define its basic properties.

1. In the agent creation wizard, provide the following details:

   | Field | Value |
   |-------|-------|
   | Agent name | `HR Assistant-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `An AI assistant that helps employees with HR-related questions including policies, benefits, leave management, and onboarding.` |

   ![](./media/ex2-agent-details.png)

1. For the agent icon, you can either:
   - Select from the available icons
   - Upload a custom image
   - Let Copilot generate an icon based on the description

   ![](./media/ex2-agent-icon.png)

1. Click **Next** or **Continue** to proceed to the instructions configuration.

   >**Note:** The agent name should be descriptive and unique. The description helps users understand what the agent can assist with.

### Task 3: Configure Agent Instructions and Persona

In this task, you will define how the agent should behave and respond to users.

1. In the **Instructions** section, enter the following prompt to define the agent's persona and behavior:

   ```
   You are a helpful HR Assistant for our organization. Your role is to:

   1. Answer questions about company HR policies including leave policies, benefits, compensation, and workplace guidelines
   2. Help employees understand the onboarding process and required documentation
   3. Provide guidance on performance review processes and timelines
   4. Assist with common HR forms and where to find them
   5. Direct employees to the appropriate HR contact for complex issues

   Guidelines for your responses:
   - Be professional, friendly, and empathetic
   - Provide accurate information based on company policies
   - If you're unsure about something, acknowledge it and suggest contacting HR directly
   - Keep responses concise but comprehensive
   - Always maintain confidentiality and remind users not to share sensitive personal information in chat
   - For urgent matters like harassment or safety concerns, always direct users to speak with HR immediately

   You should NOT:
   - Make decisions about individual employee cases
   - Provide legal advice
   - Share confidential information about other employees
   - Process actual HR transactions (leave requests, etc.) - instead guide users to the appropriate systems
   ```

   ![](./media/ex2-agent-instructions.png)

1. Review the instructions to ensure they align with your organization's HR practices.

1. Some agent builders allow you to set additional parameters:

   | Parameter | Recommended Setting |
   |-----------|-------------------|
   | Response style | Professional and friendly |
   | Response length | Balanced |
   | Creativity level | Low to Medium (for accuracy) |

   ![](./media/ex2-agent-parameters.png)

1. Click **Next** to proceed to knowledge configuration.

### Task 4: Add Knowledge Sources to the Agent

In this task, you will connect the agent to relevant data sources so it can provide informed responses.

1. In the **Knowledge** or **Data sources** section, you can add various sources:

   - SharePoint sites
   - Specific documents
   - Web links
   - Microsoft Graph connectors

   ![](./media/ex2-knowledge-sources.png)

1. For this exercise, we'll create a SharePoint site with HR documents. First, open a new browser tab and navigate to SharePoint: `https://<inject key="TenantName" enableCopy="false"/>.sharepoint.com`

   ![](./media/ex2-sharepoint-home.png)

1. Click on **+ Create site** to create a new SharePoint site for HR documents.

   ![](./media/ex2-create-site.png)

1. Select **Team site** and configure:

   | Field | Value |
   |-------|-------|
   | Site name | `HR Policies-<inject key="DeploymentID" enableCopy="false"/>` |
   | Site description | `Repository for HR policies and employee resources` |
   | Privacy settings | Private |

   ![](./media/ex2-site-config.png)

1. Click **Create** and wait for the site to be provisioned.

   ![](./media/ex2-site-created.png)

1. Once the site is created, navigate to **Documents** library and click **+ New** > **Folder** to create the following folders:
   - `Policies`
   - `Benefits`
   - `Onboarding`
   - `Forms`

   ![](./media/ex2-create-folders.png)

1. Let's create sample policy documents. Click on **+ New** > **Word document** in the Policies folder.

   ![](./media/ex2-new-document.png)

1. Create a document named `Leave-Policy.docx` with the following content:

   ```
   COMPANY LEAVE POLICY

   1. Annual Leave
   - All full-time employees are entitled to 20 days of paid annual leave per year
   - Leave must be requested at least 2 weeks in advance
   - Maximum of 5 days can be carried over to the next year

   2. Sick Leave
   - Employees are entitled to 10 days of paid sick leave per year
   - A medical certificate is required for absences of 3 or more consecutive days
   - Unused sick leave cannot be carried over

   3. Parental Leave
   - Primary caregiver: 16 weeks paid leave
   - Secondary caregiver: 4 weeks paid leave
   - Must be taken within 12 months of birth/adoption

   4. Public Holidays
   - The company observes all federal public holidays
   - If a holiday falls on a weekend, a substitute day off will be provided

   5. Leave Request Process
   - Submit requests through the HR Portal
   - Manager approval required for all leave types
   - Emergency leave can be requested retroactively within 24 hours
   ```

   ![](./media/ex2-leave-policy.png)

1. Save and close the document. Create another document named `Benefits-Overview.docx` in the Benefits folder:

   ```
   EMPLOYEE BENEFITS OVERVIEW

   1. Health Insurance
   - Comprehensive medical coverage for employees and dependents
   - Dental and vision coverage included
   - Company covers 80% of premium costs

   2. Retirement Plan
   - 401(k) plan with company match up to 6%
   - Immediate vesting for employee contributions
   - Company match vests over 3 years

   3. Professional Development
   - Annual learning budget of $2,000 per employee
   - Access to online learning platforms
   - Conference attendance support

   4. Wellness Program
   - Gym membership reimbursement up to $50/month
   - Mental health support services
   - Annual wellness stipend of $500

   5. Other Benefits
   - Flexible working arrangements
   - Home office equipment allowance
   - Employee assistance program (EAP)
   ```

   ![](./media/ex2-benefits-doc.png)

1. Now return to the agent configuration tab and add the SharePoint site as a knowledge source:

   - Click **+ Add knowledge source**
   - Select **SharePoint**
   - Browse and select your `HR Policies-<inject key="DeploymentID" enableCopy="false"/>` site
   - Click **Add**

   ![](./media/ex2-add-sharepoint.png)

   >**Note:** It may take a few minutes for the SharePoint content to be indexed and available to the agent.

1. Click **Next** or **Create** to finalize the agent.

### Task 5: Test and Refine the Agent

In this task, you will test your agent and make refinements based on its responses.

1. Once the agent is created, you will see a testing interface or be redirected to Copilot Chat with your agent selected.

   ![](./media/ex2-agent-created.png)

1. Start a conversation with your agent by typing:

   ```
   Hello! What can you help me with?
   ```

   ![](./media/ex2-test-greeting.png)

1. The agent should respond with an introduction based on its configured instructions.

1. Test the agent with HR-related questions:

   **Test 1 - Leave Policy:**
   ```
   How many days of annual leave am I entitled to?
   ```

   ![](./media/ex2-test-leave.png)

1. **Test 2 - Benefits:**
   ```
   What health insurance benefits does the company provide?
   ```

   ![](./media/ex2-test-benefits.png)

1. **Test 3 - Process guidance:**
   ```
   How do I request time off?
   ```

   ![](./media/ex2-test-process.png)

1. **Test 4 - Edge case handling:**
   ```
   Can you approve my leave request for next week?
   ```

   ![](./media/ex2-test-edge-case.png)

   >**Note:** The agent should correctly respond that it cannot approve requests and direct the user to the appropriate system or person.

1. If the agent's responses are not satisfactory, you can edit the agent to:
   - Refine the instructions
   - Add more knowledge sources
   - Adjust response parameters

   ![](./media/ex2-edit-agent.png)

1. Once satisfied with the agent's performance, you can share it with your team by adjusting the sharing settings.

   ![](./media/ex2-share-agent.png)

## Summary

In this exercise, you successfully:

- Navigated to the Copilot Agent Builder interface
- Created a custom HR Assistant agent with descriptive name and icon
- Configured detailed instructions and persona for the agent
- Created a SharePoint site with HR policy documents as a knowledge source
- Connected the knowledge source to the agent
- Tested the agent with various HR-related queries
- Learned how to refine and share the agent

You now understand how custom agents can be created within Copilot Chat to provide specialized assistance for specific business functions.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
