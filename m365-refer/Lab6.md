# [Optional] Exercise: Sales & Marketing Fire Drill 

#### Estimated Duration: 30 Minutes

### Overview

This immersive Sales & Marketing Fire Drill guides teams through an accelerated campaign launch scenario, emphasizing rapid alignment and cross-departmental delivery under pressure. Participants, acting as Transformation Leads, will use Microsoft 365 Copilot tools PowerPoint Copilot for structured campaign deck creation, Word Copilot for persuasive sales proposal drafting, and Copilot Studio for workflow automation to execute in real time. Integrated with Dataverse MCP, the exercise leverages historical campaign data for actionable insights, while the optional Analyst Agent supports trend analysis and performance benchmarking. By the end of the activity, participants will demonstrate campaign readiness, strategic decision-making, and increased team efficiency driven by intelligent automation and fast-paced content generation.

>**Note:** `Copilot may generate outputs that differ slightly from the screenshots provided please proceed with the workflow as expected`.

### Objectives

+ **Task 1:** Setting Up the Sales & Marketing Challenge
+ **Task 2:** Creating the Campaign Deck Using PowerPoint Copilot
+ **Task 3:** Drafting the Sales Proposal Using Word Copilot
+ **Task 4:** Automating Follow-Ups Using a Copilot Studio Agent
+ **Task 5:** Integrating Dataverse MCP Server for Campaign Insights
+ **Task 6:** Pre-Built Agent: Analyst (Optional)

### Task 1: Setting Up the Sales & Marketing Challenge

The objective of this task is to simulate a high-pressure sales and marketing scenario, emphasizing the urgency of delivering a campaign within 24 hours despite significant gaps in preparedness. By introducing a "Sales & Marketing Fire Drill," participants are prompted to identify pain points such as missing campaign materials and misaligned sales proposals and collaboratively explore how AI-powered tools can streamline content generation, align messaging, and accelerate turnaround to meet tight deadlines.

1. In the virtual machine (VM) desktop, type **Microsoft 365 Copilot (1)** in the search bar and select **Microsoft 365 Copilot (2)** from the results to open.
   
    ![](../media/7-10-lab1-0.png)

1. On **M365 Copilot**, from the left panel, select **Chat** and switch it to **Work**.

    ![img](../media/lab6-12-0.png)

1. To display the Slide Titled “Sales & Marketing Fire Drill”. Introduce the urgency: A campaign is due tomorrow, but nothing is ready. Also the slide includes the following Key Pain Points:

   - The marketing team lacks a structured campaign deck.
   - The sales team needs a proposal aligned with the campaign strategy.
   - Teams need a streamlined way to generate materials without delays.

1. Provide the following prompt and then Send.   

   **Prompt:**
   ```
   Create a visually engaging slide titled 'Sales & Marketing Fire Drill' to emphasize the urgency of an imminent campaign deadline. The slide should highlight key challenges: marketing lacks a structured campaign deck, sales needs a strategy-aligned proposal, and both teams require a streamlined content generation process to avoid delays.
   ```
   **Expected Output**

   ![image](../media/lab6c-12-1.png)

### Task 2: Creating the Campaign Deck Using PowerPoint Copilot

The objective of this task is to transform the Contoso campaign brief into a compelling, stakeholder-friendly presentation using PowerPoint Copilot. It involves generating a structured deck by extracting key insights, refining messaging to align with brand goals, summarizing the strategy into clear bullet points, and ensuring that each slide enhances clarity and impact for stakeholder review.

1. On the **Lab VM**, click the **Search** icon, type **PowerPoint (1)**, and select the **PowerPoint app (2)** to open it.

    ![img](../media/7-10-lab1-3.png)

1. On **PowerPoint**, select **Create with Copilot (1)** to start a new presentation.

    ![img](../media/7-10-lab6-4.png)

1. In the **Create a presentation with Copilot** window, select **Reference a file (1)**.

    ![img](../media/7-10-lab6-5.png)

    >**Note:** If the **Reference a file** option is not immediately visible, this may be due to **Copilot initialization or indexing latency**. In this case, proceed with the next task without waiting. After completing the remaining lab exercises, you may revisit this step and try again, as the option may take some time to become available.

1. From the list of available files, choose **Contoso_CampaignBrief (2)**.

    ![img](../media/7-10-lab6-6.png)

    >**Note:** If you do not see any documents listed under Reference a file, follow the steps below to attach the file from SharePoint.

    - In the **Create a presentation with Copilot** window, click the **Upload icon (1)** and then select **Attach cloud files (2)**.

      ![img](../media/lab6-12-1.png)

    - From the left navigation pane, select **Contoso Corp (1)**, choose **Contoso_CampaignBrief.docx (2)**, and then click **Select (3)**.

      ![img](../media/lab6-12-2.png)

1. Provide the below prompt **(1)** and then **Send (2)**:

   **Prompt:**
   ```
   Create a presentation from this file.
   ```

    ![img](../media/7-10-lab6-7.png)

1. Select **Generate Slides**
   
     ![img](../media/7-10-lab6-8.png)

1. Review the generated slides, then select(double-click) any slide and click on **Keep it (1)** to insert them into the presentation. Double-click on any slide to open.

   ![img](../media/7-10-lab6-9.png)

1. Select **Copilot (1)**. To Summarize the Campaign Strategy use the prompt **(2)** and then **Send (3)**:

   **Prompt:**
    ```
    Summarize the campaign strategy in 3 key bullet points. 
    ```

    ![img](../media/7-10-lab6-10.png)

    **Expected Outcome**
   
    ![img](../media/9-10-lab1-6.png)

### Task 3: Drafting the Sales Proposal Using Word Copilot

The objective of this task is to create a persuasive and well-structured sales proposal using Word Copilot, leveraging the Contoso campaign brief as the foundational source. The proposal should clearly align with both marketing and sales objectives, emphasize the campaign’s value proposition, and be refined to meet executive-level expectations for clarity, strategic impact, and professional presentation.

1. On the **Lab VM**, click the **Search** icon, type **Word (1)**, and select the **Word app (2)** to open it.

    ![img](../media/7-10-lab4-3.png)

1. Select **Blank document**, then on the document page, select the **Copilot (1)** icon from the ribbon, click the **+ (2)** icon, and choose **Upload images and files (3)**.

    ![img](../media/7-10-lab6-12.png)

1. Navigate to `C:\LabFiles\Documents` **(1)**, then select **Contoso_CampaignBrief.docx (2)** word file and then select **Open (3)**.

    ![image](../media/ci74.png)

1. Provide the below prompt:

   **Prompt:**
   ```
   Write a proposal based on the campaign brief.
   ```
   **Expected Outcome**

   ![img](../media/7-10-lab6-14.png)

### Task 4: Automating Follow-Ups Using a Copilot Studio Agent

The objective of this task is to design and deploy an intelligent follow-up system using a Copilot Studio agent that automates key campaign activities such as tracking deliverables, updating progress, sending approval alerts, and aligning communications between marketing and sales teams. By integrating this agent with Teams or CRM tools, the task aims to eliminate manual delays, enhance workflow transparency, and ensure timely execution across campaign stakeholders.

1. Follow these steps to obtain the SharePoint site URL required for the upcoming tasks:

    - Navigate to the **Microsoft 365 Copilot** desktop app, select **Apps (1)** from the left navigation pane, and then choose **SharePoint (2)**.   

      ![img](../media/m-l1-13.png)  

      - If prompted, sign-in with the credentials, **Email/Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>.     

    - Click on the **My Sites (1)** and then select **ContosoCorp<inject key="DeploymentID" enableCopy="false"/> (2)**

      ![img](../media/sg2.png)     

    - Copy and paste the **SharePoint site URL** into Notepad; you will be using it in the upcoming steps.

      ![img](../media/30-9l3-4.png) 
      
1. In the **Lab VM**, click on the **Microsoft Edge** icon to open the browser.

     ![img](../media/7-10-lab6-15.png)

1. Navigate to **Microsoft Copilot Studio** by pasting the following link in the address bar: **`https://copilotstudio.microsoft.com/`**, and sign in using the same credentials.

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

   - **Password:** <inject key="AzureAdUserPassword"></inject>

1. In the **Copilot Studio** window, from the left navigation pane, click on **Agents**.

    ![image](../media/lab5-e5-2.png)

1. And in the top-right section click on **+ Create blank agent**.

    ![image](../media/lab5-e5-3.png)

1. Enjoy the animation and wait until your very first agent is created! This might take up to a minute and after some time, refresh the browser.

    ![image](../media/lab5-e5-4.png)

1. In the **Details** section, select **Edit**

    ![image](../media/lab5-e5-5.png)

1. Provide the name as **CampaignAutomationTracker Agent (1)**.

1. Provide the below text in the **Description (2)** box and click on **Save (3)**.

     ```
     The Campaign Automation Tracker Agent is designed to streamline marketing and sales operations by automatically managing key campaign workflows, approvals, and communication tasks. This intelligent agent monitors deliverable statuses, sends real-time notifications to relevant teams, tracks stakeholder alignment, and synchronizes updates with platforms like Teams. By leveraging dynamic triggers and structured prompts, it enhances campaign visibility, eliminates delays, and ensures a seamless execution experience across all phases—from ideation to final approval.
     ```

    ![image](../media/lab6-e6-1.png)

1. Scroll down and in the **Instruction** section, select **Edit**

    ![image](../media/lab5-e5-8.png)

1. Provide below instructions on **Instruction box (1)** and click on **Save (2)**.

     ```
     - Always communicate the core values and goals of the campaign clearly and passionately.
     - Use inclusive language that resonates across diverse audiences.
     - Access Contoso Corp SharePoint site and access all the campaign related documents and lists.
     - Engage authentically.
     - Ask open-ended questions to understand supporters’ concerns, interests, and motivations.
     - Practice active listening and respond with empathy and relevance.
     - Offer informative insights tailored to the listener's context.
     - Share real stories, successes, and statistics that highlight the campaign’s purpose.
     - Encourage action—whether it's sharing, volunteering, or attending events.
     - Maintain a warm, respectful tone—even in challenging conversations.
     - Avoid political comparisons or personal opinions on candidates; instead, highlight the campaign’s policy stances and community impact.
     - Modify tone and delivery based on where the conversation is happening (online chat, in-person event, phone call, etc.).
     - Remain concise on digital platforms and expressive in personal interactions.
     - When encountering misinformation, offer verified sources and calmly correct misunderstandings.
     - Stay factual without being confrontational.
     ```

1. Add a Knowledge source by selecting **+ Add Knowledge (3)** from the bottom of the window.

    ![image](../media/lab6-e6-2.png)

1. From the **Add Knowledge** window, please select **SharePoint**.

    ![image](../media/m-l1-24.png)

1. From the **SharePoint** window please add the SharePoint site link **(1)**, then select **Add (2)**.

    ![image](../media/12-9-m51.png)

     >**Note:** If the site link shows **This item was not found in your SharePoint or OneDrive files**, this may occur due to temporary indexing delays. Select **Add anyway** to continue. 

     ![image](../media/lab5-12-1.png)

     >**Note:** Provide the **SharePoint link** that you have copied in **Task 4--> Step 1** which looks similar to (For example: https://copilotimmersionlabs100004.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/>)  

1. Again, select **Add to agent** to add the knowledge to the agent.

    ![image](../media/m-l1-25.png)          

1. Select **Topics (1)**, select **All (2)**, then select **Conversation Start (2)**. 

    ![image](../media/lab6-e6-3.png)  

1. Update the below message by keeping the first sentence as it is **(1)** and then click on **Save (2)**.

    ```
    I’m here to help you discover how this movement can truly make a difference—for you, your community, and the future we’re shaping together. Whether you’ve got questions, ideas, or just want to learn what we stand for, I’m all ears. Let's dive into a conversation that matters.
    ```
    ![image](../media/lab6c-12-2.png)
  
1. Select **Topics (1)** again, then select **+ Add a topic (2)** and select **Add from description with Copilot (3)**.

    ![image](../media/lab6-e6-4.png)

1. On the **Add from description with Copilot** page,

   - For Name your topic, enter **Campaign Submission (1)**

   - For Create a topic to..., enter **User wants to submit a new campaign details. (2)**

   - Then select **Create (3)**.  

     ![image](../media/12-9-m119.png)

1. Review the next nodes by scrolling down the window, and you can see multiple **Question nodes** and finally a **message node** at the end.

1. Please remove all the **question nodes**, by clicking on **ellipsis(...) (1)** button and then select **Delete (2)**.

    ![image](../media/12-9-m120.png)

1. Repeat the above step until deleting all the **question nodes**. 

1. Please delete the last **message node** as well by clicking on **ellipsis(...) (1)** button and then select **Delete (2)** and then **Save (3)**.

   ![image](../media/ci84.png)

1. Select the **+ (1)** button to add new node and select **Ask with adaptive card (2)**.

    ![image](../media/m-l1-41.png)

1. Select **Ellipsis(...) (1)** of the Adaptive card node, then select **Properties (2)**.

   ![image](../media/12-9-m120.1.png)

1. From the Properties window, select **Edit adaptive card**.

   ![image](../media/ci87.png)

1. Delete the existing script and paste the below Adaptive card script into the **Card payload editor** of the Adaptive card designer window.
   ```
   {
  "$schema": "https://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.5",
  "body": [
    {
      "type": "TextBlock",
      "text": "📢 Campaign Submission Form",
      "weight": "Bolder",
      "size": "Medium"
    },
    {
      "type": "Input.Text",
      "id": "campaignName",
      "label": "Campaign Name",
      "placeholder": "Enter campaign title"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "deliverableType",
      "label": "Deliverable Type",
      "choices": [
        { "title": "Deck", "value": "Deck" },
        { "title": "Proposal", "value": "Proposal" },
        { "title": "Email", "value": "Email" },
        { "title": "Summary", "value": "Summary" },
        { "title": "Brief", "value": "Brief" }
      ]
    },
    {
      "type": "Input.Text",
      "id": "taskOwner",
      "label": "Task Owner",
      "placeholder": "Enter responsible team member"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "taskPriority",
      "label": "Task Priority",
      "choices": [
        { "title": "High", "value": "High" },
        { "title": "Medium", "value": "Medium" },
        { "title": "Low", "value": "Low" }
      ]
    },
    {
      "type": "Input.ChoiceSet",
      "id": "completionStatus",
      "label": "Completion Status",
      "choices": [
        { "title": "Not Started", "value": "Not Started" },
        { "title": "In Progress", "value": "In Progress" },
        { "title": "Completed", "value": "Completed" },
        { "title": "Blocked", "value": "Blocked" }
      ]
    },
    {
      "type": "Input.ChoiceSet",
      "id": "urgencyIndicator",
      "label": "Urgency Indicator",
      "choices": [
        { "title": "Critical", "value": "Critical" },
        { "title": "Moderate", "value": "Moderate" },
        { "title": "Low", "value": "Low" }
      ]
    },
    {
      "type": "Input.Text",
      "id": "salesAlignmentNotes",
      "label": "Sales Alignment Notes",
      "placeholder": "Describe how the campaign aligns with sales strategy"
    }
  ],
  "actions": [
    {
      "type": "Action.Submit",
      "title": "Submit Campaign"
    }
  ]
}
    ```

26. After reviewing the form, select **Save (1)** and then select **Close (2)**.

    ![image](../media/12-9-m122.png)

1. Close the **Adaptive card node properties window**, then scroll down and expand **Output(8)** section.

1. Select each variable one by one **(1)** and make it as **Global (2)**.
   
    ![image](../media/12-9-m123.png)

1. After making all the variables as **Global** **(1)** and then select **Save (2)**.

    ![image](../media/12-9-m124.png)

1. Select **+ (1)** to add another node after the **adaptive card node**. Then select **Add a tool (2)** and select **New agent flow (3)**.

   ![image](../media/12-9-m125.png)

1. Select **When an agent calls the flow (1)** action, then select **+ Add input (2)**.

   ![image](../media/lab6c-12-3.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon** on the top-right of the action card to open it for a clearer view and better experience. 

   ![image](../media/30-9-l4-3.png)

1. Then add the below variables one by one.

   | Parameters | Type | 
   |--------------|----- |
   | CampaignName | Text |
   | DeliverableType | Text |
   | TaskOwner | Text |
   | TaskPriority | Text |
   | CompletionStatus | Text |
   | UrgencyIndicator | Text |
   | SalesAlignmentNotes | Text |

   ![image](../media/12-9-m126.png)

1. Select **+ (1)** to add new action, then type **SharePoint (2)** on the search box and select **Create item (3)**.

   ![image](../media/30-9-l5-1.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon**  on the top-right of the action card to open it for a clearer view and better experience. 

1. Under **Parameters** section,

   - Site name: Select **Contoso Corp<inject key="DeploymentID" enableCopy="false"/>** SharePoint site link **(1)**
   - List name: Select **Campaign_Automation_Tracker_List (2)** 
   - Title: Enter **Campaign_Automation_Tracker (3)**
   - Then click **Show all (4)**
   
     ![image](../media/12-9-m128.png)

1. Under Advanced parameters, please select the boxes of **Title, Deliverable Type, Task Owner, Task Priority, Completion Status, Sales Alignment Notes, Urgency Indicator**, then click on the **dynamic content** icon and then select the corresponding value from the Input parameters.

   ![image](../media/12-9-m129.png)
  
1. Select **+ (1)** under **Create item** action, then type **Condition (2)** on the search box and select **Condition (3)**.

   ![image](../media/30-9-l5-2.png)

    > **Note:** If the side panel does not open automatically, click the **panel icon**  on the top-right of the action card to open it for a clearer view and better experience. 

    ![image](../media/30-9-l4-6.png)

1. Select **Completion status (1)** item from the SharePoint list, select **is equal to (2)** and then enter **Completed (3)**.

   ![image](../media/lab6-12-3.png)

1. Select **+ (1)** under **True** section of the condition action, search for **Update item (2)** and select **Update item (2)**.

   ![image](../media/30-9-l6-5.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon**  on the top-right of the action card to open it for a clearer view and better experience. 

    ![image](../media/30-9-l4-7.png)

1. Enter the following details under the parameters section of the side screen:

   | Site Address | List Name | Id | Title |
   |--------------|-------------------|----------------------|----------------------|
   | Contoso Corp<inject key="DeploymentID" enableCopy="false"/> - https://domainname.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/> **(1)** | **Campaign_Automation_Tracker_List (2)**  | Select SharePoint **ID (3)** | Enter **Campaign_Automation_Tracker (4)** |

   - Click on **Show all (5)**

     ![image](../media/12-9-m133.png)

   - Under the **Approval Status** type as **Approved**

     ![image](../media/12-9-m134.png)     

1. Select **+ (1)** under **False** section of the condition action, search for **Update item (2)** and select **Update item (2)**.

   ![image](../media/30-9-l6-6.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon**  on the top-right of the action card to open it for a clearer view and better experience. 

    ![image](../media/30-9-l4-9.png)

1. Enter the following details under the parameters section of the side screen:

   | Site Address | List Name | Id | Title |
   |--------------|-------------------|----------------------|----------------------|
   | Contoso Corp<inject key="DeploymentID" enableCopy="false"/> - https://domainname.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/> **(1)** | **Campaign_Automation_Tracker_List (2)**  | Select SharePoint **ID (3)** | Enter **Campaign_Automation_Tracker (4)** |

   - Click on **Show all (5)**

     ![image](../media/12-9-m137.png)

   - Under the **Approval Status** type as **Rejected**

     ![image](../media/12-9-m138.png)

1. Select **Publish**.

   ![image](../media/lab6c-12-4.png)

1. Select **Go back to agent**.

   ![image](../media/12-9-m140.png)

1. On **Action** node for each Power automate inputs, click on **ellipsis(...) (1)** of each input parameter and select appropriate variables **(2)**.

   ![image](../media/ex6img15.jpg)

1. After selecting all parameters it looks like this **(1)** and then select **Save (2)**:

   ![image](../media/ex6img16.jpg)

1. Add one more node by clicking on **+ (1)**, then select **Send a message (2)**.

   ![image](../media/30-9-l6-8.png)

1. On the message box, please enter **You have successfully submitted the campaign details. (1)** then select **Save (2)**.

   ![image](../media/12-9-m142.png)

1. Publish your agent by selecting **Publish**.

   ![image](../media/lab6c-12-4.1.png)

1. Select **Publish** again.

   ![image](../media/lab5-12-01.png)

**You have successfully completed the deployment of Copilot agent.**

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="15926b03-837e-465b-962d-4f3fd5753b86" />

### Task 5: Integrating Dataverse MCP Server for Campaign Insights

The objective of this task is to integrate Dataverse MCP Server with your campaign tracking system to centralize and analyze data, enabling real-time insights, historical performance comparisons, and trend identification that support strategic decision-making and sales forecasting. Here we are using a table account which is already available in Dataverse tables.

1. Select **Tools (1)**, then select **+ Add a tool (2)**.

   ![image](../media/lab6c-12-5.png)

1. From the **Add tool** window select **Model Context Protocol (1)**, then select **Microsoft Dataverse MCP Server (2)**.
   
   ![image](../media/lab6c-12-6.png)

1. Select **Not connected (1)** dropdown and select **Create new connection (2)**.

   ![image](../media/lab6c-12-7.png)

1. Select **OAuth (1)** as Authentication type, then select **Create (2)**.

   ![image](../media/m-l1-46.png)

1. Sign in using **<inject key="AzureAdUserEmail"></inject>**.

   ![image](../media/ci110.png)

1. Select **Add and configure**.

   ![image](../media/lab6c-12-7.1.png)

   **Note:** If you do not see the **Add to agent** button, click **Add and configure**.

   **You have successfully added the **Dataverse MCP Server**.**

1. Provide the below prompt in the **Test your agent (1)** and select **Allow (2)** if prompted.

   **Prompt:**
   ```
   Analyze past campaigns and suggest improvements.
   ```

    ![image](../media/lab6c-12-7.2.png)  

   **Expected output**:

   ![image](../media/ci113.png)

    >**Note**: If it is asking for Retry please select **Open Connection manager**, you will be redirected to another window, select **Microsoft dataverse** to connect.

     - Go back to **Copilot studio** and Retry again you will get below output

       **Expected Outcome**
   
       ![image](../media/ci113.png)

1. Select **Channels (1)**, select **Teams and Microsoft 365 Copilot (2)**.

   ![image](../media/lab6c-12-8.1.png)  

1. Then select **Add channel**.

   ![image](../media/12-9-m152.png)  

1. Select **See agent in Teams**.

   ![image](../media/12-9-m153.png)  

1. When prompted with the message **“This site is trying to open Microsoft Teams”**, select **Open** to launch the **Teams desktop app**.

    ![image](../media/7-10-lab6-2.png)  

1. Then select **Add**.

   ![image](../media/30-9-l6-9.png)

1. Select **Open**.

   ![image](../media/30-9-l6-10.png)

   **You have successfully added Campaign copilot to teams.**

1. By passing several prompts related to campaign, you can test the copilot.

   **Prompt:**
   ```
   Analyze past campaigns and suggest improvements.
   ```

   ![image](../media/lab6c-12-7.4.png)

### Task 6: Pre-Built Agent: Analyst (Optional)

The objective of this task is to use a pre-built Analyst Agent to interpret structured data, identify performance trends, and generate visual summaries and actionable insights. This helps optimize decision-making by turning analytics into clear, impactful recommendations across sales, support, and KPI datasets.

1. Go to **Microsoft 365 Copilot**, select **All agents (1)**, then select **Analyst (2)** agent.

   ![image](../media/lab6c-12-10.png)   

1. To analyse data and identify trends, please upload the document named **contoso_monthly_sales.csv**. Select **+ (1)** and then **Upload images and files (2)**.

   ![image](../media/30-9-l6-12.png)

1. Navigate to `C:\LabFiles\Documents` **(1)**, then select **contoso_monthly_sales.csv (2)** word file and then select **Open (3)**.

   ![image](../media/ci123.png)

1. Then provide the below prompt:

   **Prompt:**
   ```
   Analyze this CSV containing monthly sales data across regions. Identify which markets show declining sales trends over the past three months, and hypothesize potential causes based on seasonal patterns, product performance, or regional behaviour.
   ```
   **Expected Outcome**
   
   ![image](../media/lab6c-12-8.png)

1. To build a visual summary, provide the below prompt:

   **Prompt:**
   
   ```
   Using this dataset, create a visual summary that includes a line chart showing monthly revenue trends and a pie chart breaking down market share by region. Highlight any notable patterns or shifts that may impact performance decisions.
   ```
   **Expected Outcome**
   
   ![image](../media/lab6c-12-9.png)

1. Select **+ (1)** and then **Upload images and files (2)**.

   ![image](../media/30-9-l6-12.png)

1. Navigate to `C:\LabFiles\Documents` **(1)**, then select **Contoso_Ticket_Handling_List.xlsx (2)** word file and then select **Open (3)**.

   ![image](../media/ci124.png)   
   
1. Provide the below prompt to recommend a course of action.

   **Prompt:**
   ```
   Review the Excel sheet containing support tickets and performance metrics. Based on patterns in response times, resolution rates, and ticket categories, recommend the top two actions that would most effectively reduce average response time. Justify your suggestions using the available data.
   ```
   **Expected Outcome**
   
   ![image](../media/30-9-l6-13.png)

1. Select **+ (1)** and then **Upload images and files (2)**.

   ![image](../media/30-9-l6-12.png)

1. Navigate to `C:\LabFiles\Documents` **(1)**, then select **kpi_benchmark_analysis.xlsx (2)** word file and then select **Open (3)**.

   ![image](../media/ci125.png)   

1. Please provide the below prompt:

   ```
   Analyze this dataset containing quarterly KPIs alongside benchmark targets. Assess how closely each team is performing relative to these benchmarks, and flag any significant gaps or anomalies. Include confidence indicators and suggest where immediate attention may be required.
   ```
   **Expected Outcome**
   
   ![image](../media/30-9-l6-14.png)

### Review

The Sales & Marketing Fire Drill empowers teams to respond rapidly under pressure by leveraging M365 Copilot tools. PowerPoint and Word Copilot streamline campaign deck and proposal creation from existing briefs, while Copilot Studio agents automate execution and approvals. By integrating Dataverse MCP and the Analyst agent, teams gain deep insights, optimize decisions, and boost sales forecasting all in record time.

Successfully completed the below tasks for prompting:

+ Setting Up the Sales & Marketing Challenge
+ Creating the Campaign Deck Using PowerPoint Copilot
+ Drafting the Sales Proposal Using Word Copilot
+ Automating Follow-Ups Using a Copilot Studio Agent
+ Integrating Dataverse MCP Server for Campaign Insights
+ Pre-Built Agent: Analyst (Optional)

    
## Congratulations !!! You have successfully completed the all labs.
