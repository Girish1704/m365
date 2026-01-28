# Exercise 1: The Spark – Identifying Chaos 

#### Estimated Duration: 30 Minutes

### Overview

In this immersive experience, you will step into the role of a Transformation Lead at Contoso Corp. a rapidly growing organization facing operational chaos due to disconnected reporting, inconsistent policies, and siloed data. Your mission is to leverage both the free version of Copilot Chat and Microsoft 365 Copilot Chat to uncover inefficiencies, analyze organizational data, and drive strategic transformation.

Through a series of guided tasks, you will explore how AI-powered tools can:
- Analyze documents and policies for inconsistencies.
- Surface insights from internal communications and business data.
- Prioritize operational challenges and propose actionable solutions.
- Collaborate across teams using Copilot to align stakeholders and define KPIs.

**Copilot Chat vs. Microsoft 365 Copilot:**<br>
At the start of this lab, it's important to understand the distinction between: 
 - **Copilot Chat (Free, Web-Based) →** A publicly accessible AI-powered chat tool that allows users to upload documents, ask questions, and receive general guidance. It operates using publicly available information. 
 - **Microsoft 365 Copilot (Work, Enterprise-Level) →** An AI-powered assistant deeply integrated with Microsoft 365 tools (Word, PowerPoint, Outlook, Excel, and Teams). It can access internal files, emails, calendars, and chats to provide organization-specific insights based on a company’s existing data. 

This lab simulates a real-world transformation journey, empowering you to apply AI-driven diagnostics and decision-making in a corporate setting.

>**Note:** `Copilot may generate outputs that differ slightly from the screenshots provided—please proceed with the workflow as expected`.

>**Note:** If Copilot chat is not responding, or the document upload fails, please sign out and sign in again, then retry the action.

### Objectives

+ **Task 1:** Understanding Contoso Corp’s Chaos (Exploring the free Version of Copilot Chat) 
+ **Task 2:** Leveraging Organizational Data for Insights (Exploring M365 Copilot Chat) 
+ **Task 3:** Prioritizing and Structuring Key Findings  

### Task 1: Understanding Contoso Corp’s Chaos (Exploring the Free Version of Copilot Chat) 

In this task, you will simulate a real-world scenario where you analyze internal documentation by using the Free version of Copilot chat. We're using Copilot Chat (Free) with Enterprise Data protection, using our user's organizational identity (Entra ID). 

1. In the virtual machine (VM) desktop, type **Microsoft 365 Copilot (1)** in the search bar and select **Microsoft 365 Copilot (2)** from the results to open.

   >**Note:** You can also open the **Microsoft 365 Copilot** by clicking on the ![](../media/cop.png) icon in the taskbar.
   
   ![](../media/7-10-lab1-0.png)

1. On **Choose a Microsoft account** pop-up, click **Create or Sign in with a different account**.

   ![](../media/m365-g1.png)

   - On the **Sign in** page enter **Email/Username:** **<inject key="AzureAdUserEmail"></inject>** **(1)** and click on **Next (2)**.
 
      ![](../media/m365-g2.png)
 
   - Enter **Temporary Access Pass:** **<inject key="AzureAdUserPassword"></inject>** **(1)** and click on **Sign in (2)**. 

      ![](../media/m365-g3.png)

   - On **Sign in to all apps, websites, and services on this device?** page, select **Yes**.

      ![](../media/m365-g4.png)

      >**Note:** If you encounter any error, click **OK** and wait a few seconds for the page to load.

1. From the left panel, select **Chat (1)**, switch it to **Web (2)**, and then provide the following prompt:

    ![](../media/lab1-12-1.png) 

   **Prompt:**
   ```
   Create a case study for Contoso Corp that highlights their struggle with operational inefficiencies due to siloed reporting and inconsistent policies, and position the Transformation Lead as the key driver of organizational change.
   ```

   **Expected Output:**

   ![image](../media/Lab1c-12-1.png)

   >**Note:** If you encounter an error message such as **"Something went wrong,"** click on **Try again** repeatedly until the page loads successfully.

   This slide highlights Contoso Corp’s operational inefficiencies caused by siloed reporting and inconsistent policies, visually represented through a disorganized dashboard. As Transformation Lead, you're tasked with bringing structure and alignment to this fragmented landscape.

1. To upload the document please select the **+ (1)** symbol and select **Upload images and files (2)**.

   ![image](../media/12-9-m2.png)
   
1. Navigate to the `C:\LabFiles\Documents` **(1)** path, then select the document named `Contoso_Support_Policy.docx` **(2)**,  and then **Open (3)**.

   ![image](../media/mc57.png)

   >**Note:** If Copilot chat is not responding, or the document upload fails, please sign out and sign in again, then retry the action.

1. Once the files are uploaded, provide the following prompt **(1)** and then click on **Send (2)**:

   **Prompt:**
   ```
   Summarize this document.
   ```
   ![image](../media/Lab1c-12-2.png)

   **Expected Output:**

   ![image](../media/Lab1c-12-3.png)

   A concise summary of the policy’s purpose, scope, and key sections (e.g., **Support Channels, Escalation Procedures, SLAs**).

1. Provide another prompt to create the top 5 FAQs. 

   **Prompt:**
   ```
   What are the top 5 FAQs based on this document?
   ```

   **Expected Output:** 

   ![image](../media/Lab1c-12-4.png)

   A list of frequently asked questions, such as:
   - What are the response and resolution times for critical support issues?
   - Who do I escalate to if my issue isn’t resolved promptly?
   - When is support available for different teams?
   - How are requests like new user setups, course creation, or workspace moves handled?
   - What’s the protocol for dealing with cybersecurity threats or policy violations?

1. To identify policy inconsistencies, provide another prompt that will find out the gaps or contradictions in the policy that may vary across departments.
 
    **Prompt:**
    ```
    Are there any inconsistencies or unclear sections in this document?
    ```

    **Alternative Prompt (if needed):**
    ```
    Do any support procedures differ across departments?
    ```

    **Expected Output:** 

   ![image](../media/Lab1c-12-5.png)

   Copilot may highlight:
     - Conflicting escalation paths
     - Department-specific exceptions are not clearly defined
     - Ambiguities in SLA definitions

    **Note:** This helps participants practice iterative prompting and critical thinking.
   
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.

<validation step="0bcec3dd-e5c4-4fc6-8620-628e14933f91" />

### Task 2: Leveraging Organizational Data for Insights (Exploring M365 Copilot Chat)

We’re now switching to Microsoft 365 Copilot, the paid add-on powered by organizational data and protected within the secure Microsoft 365 ecosystem. The objective of this task is to demonstrate how M365 Copilot Chat can analyze an organization's internal data, like emails, meetings, and documents to uncover operational inefficiencies, detect critical issues across departments, and generate contextual insights for strategic decision-making. It emphasizes real-time, data-driven diagnostics using natural language prompts within the secure M365 ecosystem.

>**Note:** `Copilot may generate outputs that differ slightly from the screenshots provided, please proceed with the workflow as expected`.

1. In the virtual machine (VM) desktop, type **Microsoft 365 Copilot (1)** in the search bar and select **Microsoft 365 Copilot (2)** from the results to open.
   
   ![](../media/7-10-lab1-0.png)

   - **Purpose:** Enables secure access to your org’s structured and unstructured data emails, OneDrive files, Teams chats, SharePoint pages, calendar items, and more.

1. Select the **Chat (1)** from the left panel, and then switch it from **Web** to **Work (licensed version) (2)**.

   ![](../media/lab1-12-2.png)

   **Prompt:**
   ```
   Explore the Contoso Corp<inject key="DeploymentID" enableCopy="false"/> SharePoint site and identify the various categories of business data available on the platform.
   ```

   **Expected Output:**

    ![image](../media/lab1-1-1.png)

   >**Note:** If the expected output is not displayed, proceed with the subsequent steps without waiting. After completing all lab exercises, you may revisit this step and run the prompts again, as the expected output may take several hours to appear due to SharePoint indexing latency, which affects Copilot’s ability to surface results.
   
1. Analyze Business Performance Using Prompts. Use a high-level prompt to trigger pattern detection and summarization across organizational content.

   **Prompt:**
   ```
   Access Contoso_business_performance_report.xlsx you can see the rapid growth has outpaced its current processes. What are some immediate actions we can take to restore structure and improve operational control?
   ```
   **Expected Output:**

    ![image](../media/lab1-1-2.png)    
  
   >**Note:** It will scan relevant reports, internal audits, org charts, and conversations to detect fragmentation points, proposing action items like standardization, documentation gaps, or automation needs.

1. To demonstrate Copilot’s contextual reasoning by referencing actual internal data sources, open the **Microsoft Teams desktop app**.

1. On the Windows taskbar, click the **Search** icon and type **Microsoft Teams (1)**. From the search results, select the **Microsoft Teams app (2)** to open it.

    ![](../media/7-10-lab1-2.png)

1. Once Teams opens, select the **Contoso executive group (1)** and then access **Copilot (2)** from the top-right corner. Provide the below prompt.

   ![image](../media/lab1-1-2n.png)

   > **Note:** <span style="color:red">If you don’t see **Copilot icon** in Teams, it might take additional time due to **Copilot indexing** or **Graph connection** not being fully synced yet. In that case, open **Microsoft Edge** and access Microsoft Teams by visiting **https://teams.microsoft.com/**</span>.

   > If prompted, sign-in with the credentials, **Email/Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>. 

   >**Note:** Once signed in using the credentials, select the **Contoso executive group (1)** and then access **Copilot (2)** from the top-right corner to continue.  

   **Prompt:**
   ```
   Summarize Q2 strategy discussions from this Teams chat.
   ```

   **Expected Output**

    ![image](../media/lab1-teams1.png)

1. On the Microsoft Teams Copilot, try out the below prompt:

   ```
   What’s the sentiment in recent leadership discussions in this Teams chat?
   ```

   **Expected Output**

   ![image](../media/lab1-teams2.png)

1. Switch back to **M365 Copilot** and select **Work** tab from top, then enter the below prompt:
   ```
   Draft a concise FAQ based on the onboarding materials available on the ContosoCorp site, specifically referencing the Leadership Feedback Forms, HR Handbook, and Support Policy documents.
   ```

   **Expected Output**

   ![image](../media/lab1-1-3.png) 

1. Open the **Edge browser (1)** from the desktop, copy the url **<inject key="sharepointsite"></inject> (2)** and paste it into a new browser tab to directly navigate to the **Contoso Corp<inject key="DeploymentID" enableCopy="false" />** SharePoint site.

   ![image](../media/edg.png) 

   ![image](../media/url.png) 

1. On the **Contoso Corp<inject key="DeploymentID" enableCopy="false" />** SharePoint site, navigate to **Documents (1)** from the left panel, click on the **Open Agents (2)** icon from the top-right corner, and enter the prompt provided below.

    ![image](../media/upp30-9-l1-2.png)

   ```
   What are the top 3 issues facing Contoso in Q3?
   ```

   **Expected Output**

   ![image](../media/9-10-lab1-3.png)      

   **Note:** If the expected output is not displayed, proceed with the subsequent steps without waiting. After completing all lab exercises, you may revisit this step and run the prompts again, as the expected output may take several hours to appear due to SharePoint indexing latency, which affects Copilot’s ability to surface results. 

1. Ask What’s Going Wrong at Contoso Corp? This diagnostic-style prompt activates pattern-matching against operational signals and anomalies. Go to **M365 Copilot** and provide the below prompt.

   **Prompt:**
   ```
   Review the Contoso_Employee_Pulse_Survey available on the ContosoCorp site and highlight the most commonly reported concerns reflected in recent HR complaints.
   ```
   
   **Expected Output**

   ![image](../media/lab1-1-4.png) 

1. To detect the top 5 urgent problems across key departments. Please enter the below prompts.

   **Prompt:**
   ```
   Access Contoso_Corp_Business_Performance_Report document and identify recurring escalation themes within the Support team over the past 60 days.
   ```

   ![image](../media/l1-5.png)

1. Use @ Mentions and Slash (/) Commands for Precision. Please provide the below prompt.

    **Prompt:**
    ```
     Analyze the Q2 strategic priorities using @Lee Gu’s comments from /Contoso_Meeting_Transcripts.docx and /Contoso_ExecSync_Transcript.docx, insights from /June_Operational_Challenges_Summary_Report.docx, and strategic plan 2025 from /Executive_Action_Plan.docx, and identify key themes and potential risks.
    ```

    **Expected Output**

    ![image](../media/lab1-1-6.png)   

     >**Note:** This enhances Copilot’s accuracy by grounding context in specific assets.

1. On **M365 Copilot chat** please provide the below prompt.

    **Prompt:**
    ```
    Create a slide summary of the most critical operational issues at Contoso and rank them by urgency and display it in table format
    ```

    **Expected Output**
      
     ![](../media/lab1-1-7.png)

1. Cross-check the most frequently mentioned issues across emails and meeting notes for validation. Please provide the below prompt.

    **Prompt:**
    ```
    Access the leadership alignment reports and customer feedback summaries stored in our ContosoCorp SharePoint site. Review the available documents in those categories, identify recurring operational issues that appear in both sets, and summarize them to validate common concerns impacting strategic execution and customer trust.  
    ```

    **Expected Output**

    ![image](../media/lab1-1-8.png)    
     
1. Identify any trends or recurring bottlenecks causing operational inefficiencies. Please provide the below prompts.

    **Prompt:**
    ```
    Highlight the top five operational inefficiencies that have persisted since the last quarter.
    ```
    
    **Expected Output**
   
    ![image](../media/lab1-1-9.png)

    ```
    Identify departments with consistent SLA violations over the past reporting period.
    ```

    **Expected Output**
   
    ![image](../media/lab1-1-10.png)
      
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.

<validation step="60912412-86ad-4de9-8281-0a01a15abd4e" />

### Task 3: Prioritizing and Structuring Key Findings

In this task, we're leveraging Microsoft Teams Copilot to turn scattered conversations and meeting insights into a structured executive plan. By analyzing chats and documents in the Contoso Executive Group channel, Copilot helps extract key operational challenges, such as budget misalignment and communication gaps, and transforms them into prioritized actions, ownership assignments, and measurable outcomes.

1. On the **Lab VM**, click the **Search** icon and type **Microsoft Teams (1)**. From the search results, select the **Microsoft Teams app (2)** to open it.

    ![](../media/7-10-lab1-2.png)

    >**Note: When you log in to Teams, you can see a channel, Contoso Executive Group, with some chats already available. You are summarizing those contents in that group.**

     ![image](../media/30-9-l1-5.png)   

1. Once Teams opens, select the **Contoso executive group (1)** and then access the **Copilot icon (2)** from the top-right corner. Provide the below prompt.

   ![image](../media/lab1-1-2n.png)

   > **Note:** <span style="color:red">If you don’t see **Copilot icon** in Teams, it might take additional time due to **Copilot indexing** or **Graph connection** not being fully synced yet. In that case, open **Microsoft Edge** and access Microsoft Teams by visiting **https://teams.microsoft.com/**</span>.

   >**Note:** If prompted, sign-in with the credentials, **Email/Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>. 

   >**Note:** Once signed in using the credentials, select the **Contoso executive group (1)** and then access **Copilot icon (2)** from the top-right corner to continue.       

   **Prompt:**
   
   ```
   Based on the messages in this Teams chat, summarize the cross-functional discussion highlighting issues with budget coordination, ownership gaps, communication breakdowns affecting hiring and customer trust, and the decision to assign initiative owners and implement a centralized tracking system by the end of the day.
   ```
   
   **Expected Output**
   
   ![image](../media/lab1-1-11.png)

1. Extract Key Operational Issues. Use natural prompts to identify pain points across communication channels. Please enter the below prompt.

   **Prompt:**
   ```
   Provide an overview of the key operational challenges discussed in recent meetings and communications in a bulleted list.
   ```

   **Expected Output**
   
   ![image](../media/lab1-1-12.png)

1. Segment Issues into Short-Term Fixes vs. Long-Term Transformations. Clarify urgency and effort level for each issue to prioritize accordingly.

   **Prompt:**
   ```
   Organize the identified issues into short-term solutions and long-term transformation initiatives based on the Teams chat.
   ```
   
   **Expected Output**
   
   ![image](../media/lab1-1-13.png)
   
1. Prioritize Actionable Solutions. Bring structure to the recovery roadmap.

   **Prompt**
   ```
   Suggest immediate steps to address short-term issues.
   ```
   
   **Expected Output**

   ![image](../media/lab1-1-14.png)

   **Prompt**
   
   ```
   Develop a phased roadmap focused on long-term operational improvements based on the Teams chat, including key initiatives, timelines, and measurable outcomes that support sustainable growth.
   ```
   
   **Expected Output**

   ![image](../media/lab1-1-15.png)
 
1. Draft a High-Priority Executive Action Plan. Create a leadership-facing summary outlining core issues and resolutions.

   **Prompt:**
   ```
   Draft a concise executive action plan based on our findings, outlining key problem areas, recommended solutions, and implementation timelines.
   ```

   **Expected Output**
   
   ![image](../media/lab1-1-16.png)

1. Define Implementation Ownership. Assign team leads and approvers for each resolution stream. Please provide the below prompt.

   **Prompt:**
   ```
   Assign responsible teams or individuals to each action item, and assess the feasibility of execution based on current capacity and expertise.
   ```
   
   **Expected Output**

   ![image](../media/lab1-1-17.png)

1. Refine the Final Plan. Polish Copilot’s initial draft to ensure readiness for executive review. Please provide the below prompt.

   **Prompt:**
   ```
   Review the proposed action plan for completeness and ensure it aligns with our strategic objectives based on the Teams chat before preparing it for executive presentation.
   ```

   **Expected Output**

   ![image](../media/lab1-1-18.png)

1. Set Measurable KPIs to Track Progress. Shift focus from strategy to measurable success. Please provide the below prompt.

    **Prompt**
    ```
    Based on the messages in this Teams chat, define measurable KPIs to monitor the effectiveness of implemented solutions, focusing on metrics that reflect operational impact, efficiency gains, and goal alignment.
    ```

    **Expected Output**

    ![image](../media/lab1-1-19.png)

1. Validate KPI Relevance. Ensure metrics are aligned to outcomes, not just activity. Please provide the below prompt

    **Prompt**
    ```
    Infer KPIs from the chat discussion and map them to efficiency, customer satisfaction, revenue growth, or employee engagement.
    ```

    **Expected Output**

    ![image](../media/lab1-1-20.png)

This guided workflow enables leaders to shift from reactive coordination to data-informed decision-making, aligning quick fixes with long-term transformation strategies all directly within the secure Microsoft 365 ecosystem.

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="54f2ed5a-819f-46c2-99b4-87568b2d93ba" />

### Review

Microsoft Copilot simplifies the content creation process by identifying top SEO keywords to effectively reach the audience, generating tailored content based on those keywords, and proofreading drafts to meet precise grammar rules. It enhances the work with AI-generated images, turns keywords into compelling headlines and structured section headings, and repurposes the drafts into engaging social media posts optimized for different platforms. 

Successfully completed the following  tasks for prompting:

- Understanding Contoso Corp’s Chaos
- Leveraging Organizational Data for Insights
- Prioritizing and Structuring Key Findings  
    
**You have successfully completed the lab. Click on Next >>**

![Start Your Azure Journey](../media/gci7.png)
