# Exercise 3: Support Chaos – AI-Powered Customer Issue Resolution 

#### Estimated Duration: 30 Minutes

### Overview

This Immersion experience guides Transformation Leads in streamlining support operations using Copilot Chat, Agent Builder, and the Pre-Built Researcher Agent. Participants start by extracting FAQs and improvement opportunities from support policy documents. They then create clear knowledge base articles and use Agent Builder to automate ticket triage from a SharePoint list, enabling smart routing and real-time FAQ generation. The Researcher agent is a pre-built agent by Microsoft, exclusive to M365 Copilot subscribers. The Researcher Agent enhances analysis by synthesizing enterprise data to uncover recurring issues and suggest strategic fixes.  A final hands-on assessment highlights measurable results, including a 40% drop in ticket volume and faster resolution times.


>**Note:** `Copilot may generate outputs that differ slightly from the screenshots provided please proceed with the workflow as expected`.

### Objectives

+ **Task 1:** Upload and Summarize the Support Policy 
+ **Task 2:** Refining Support Documentation 
+ **Task 3:** Automating Ticket Triage with Agent builder
+ **Task 4:** Pre-Built Agent- Researcher

### Task 1: Upload and Summarize the Support Policy

In this task, you will summarize the Contoso Support Policy for customer support reps, identify operational impacts, generate FAQs from top issues, and recommend policy changes to reduce ticket backlog, increase self-help capability, and standardize responses to minimize repetitive inquiries.

1. In the virtual machine (VM) desktop, type **PowerPoint (1)** in the search bar and select **PowerPoint (2)** from the results to open.

   ![img](../media/7-10-lab1-3.png)

1. Select the **Blank Presentation**. Once the presentation opens, click on the **Copilot icon**, enter the prompt provided below.

   **Prompt:**

    ```
    Create a slide titled ‘Support Chaos’ that highlights the current challenges in customer support. Emphasize that support reps are buried in tickets, response times are increasing, and customer frustration is growing. Include a short, impactful statement and 2–3 bullet points summarizing the situation.
    ```

     ![img](../media/additionalex2img3.jpg)

     >**Note:** <span style="color:red"> If Copilot does not create the presentation as expected, it may take additional time due to **indexing delay** in such cases, follow the alternative approach below.</span>

      1. In the **Home** tab, select **New Slide with Copilot**.

         ![img](../media/7-10-lab2-4.png)

          >**Note:** If **New Slide with Copilot** is not visible under the **Home** tab, switch to the **Insert** tab and select **New Slide with Copilot**. If it still does not appear, close PowerPoint and reopen it by selecting **Create with Copilot** from the start screen.

      1. In the **Add a slide with Copilot** window, paste the following prompt in the text box **(1)**, and then click the **Send (2)** button.

         ![img](../media/7-10-lab3-1.png)

      1. Review the generated slide. If satisfied with the output, click **Keep it** to insert the slide into the presentation, then press **Ctrl + S** and click **Save**.
    
         ![img](../media/7-10-lab3-2.png)

1. Go to **Microsoft 365 Copilot** and provide the below prompt.

   **Prompt:**

    ```
    Summarize Contoso_Support_Policy.docx document for customer support reps.
    ```

    **Expected Outcome**

    ![img](../media/Lab2c-12-4.png)
  
1. Generate FAQs for Customers. Please provide the below prompt.

   **Prompt:**

    ```
    We have a lack of capacity to meet the current demand for support, and our ticket backlog is growing. Can you generate an FAQ from top issues and recommend policy changes to drive down demand and increase self-help capability.
    ```

    **Expected Outcome**
  
     ![img](../media/lab3-1-1.png)

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="910c14fe-bd21-4d3f-b6e9-6088f68cf980" />

### Task 2: Refining Support Documentation 

In this task, you’ll use Copilot Pages, a collaborative workspace within Microsoft Copilot to identify gaps in the Contoso Support Policy and craft a concise knowledge base article that enhances customer service, improves support rep efficiency, and strengthens self-service resources and can share with colleagues.

1. On the **Microsoft 365 Copilot** app, identify policy gaps by entering the prompt provided below.

   **Prompt:**

    ```
    Identify any policies that affect customer support operations, highlight any missing elements that could improve customer service, and suggest enhancements to better meet customer needs.
    ```

   **Expected Outcome**

   ![img](../media/lab3-1-2.png)

1. Create a Knowledge Base Article in Copilot pages so it can be shared with colleagues. On **Microsoft 365 Copilot**, select **Start a new chat** from the top-right corner.

   ![img](../media/Lab3c-12-5.png)

1. In the page copilot, enter the below prompt:
   
   **Prompt:**

    ```
    Draft a support knowledge base article based on the Contoso_Support_Policy.docx available in ContosoCorp SharePoint site. Ensure the article is clear, concise, and practical for customer support representatives. Focus on summarizing key procedures, service entitlements, escalation steps, and include bullet points or step-by-step guidance where appropriate. The tone should be instructional and support ready.
    ```

    **Expected Outcome**

    ![img](../media/Lab3c-12-6.png)

1. Select the **More options (1)** button and choose **Edit in Pages (2)** to open the content in Copilot Pages, then remove the unwanted statements **(4)**, Provide the name as **Policy_Knowledgebase (3)** by clicking on **Untitled**. If you want to share this page with your colleagues, you can use the **Share (5)** button.

    ![img](../media/lab3-12--2.png)

    **Note:** This step demonstrates the **Edit in Pages** capability in Microsoft 365 Copilot. It allows you to open the generated response in **Copilot Pages** to refine, edit, or remove content as needed. Sharing the page using the **Share** option is **optional** and can be done only if collaboration or review is required. For this lab, sharing the page with other users is **not mandatory**.

The Copilot page containing the Policy knowledge base has been successfully created.
   
> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="9306ed79-4396-4277-b430-2a2a2872dc62" />

### Task 3: Automating Ticket Triage with Agent builder

In this task, you will automate ticket triage using Agent builder integrated with a SharePoint site to categorize, route, and analyze support tickets, enabling smarter FAQ generation and improved workload distribution. Microsoft 365 Agent Builder is a low-code tool within Copilot that lets users create personalized AI agents using natural language or templates no coding required.


1. Follow these steps to obtain the SharePoint site URL required for the upcoming tasks:

    - Navigate to the **Microsoft 365 Copilot** desktop app, select **Apps (1)** from the left navigation pane, and then choose **SharePoint (2)**.

      ![img](../media/Lab3c-12-7.png)  

      - If prompted, sign-in with the credentials, **Email/Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>.   

    - Click on the **My Sites (1)** and then select **ContosoCorp<inject key="DeploymentID" enableCopy="false"/> (2)**

      ![img](../media/sg2.png)     

    - Copy and paste the **SharePoint site URL** into Notepad; you will be using it in the upcoming steps.

      ![img](../media/30-9l3-4.png)     

1. Go back to **Microsoft 365 Copilot** (licensed version) then select **Create agent (2)** under **Agents (1)** section.

   ![img](../media/additionalex3img4.jpg)

1. Select **Configure** tab and then provide the name as **Ticket_Triage_Agent (1)**.
    
1. Provide the below description under the **Description (2)** box.

    ```
    This intelligent Copilot agent streamlines support operations by categorizing and routing incoming tickets, conducting topic-based research from documents or structured data, and delivering insightful summaries, recommendations, and knowledge base content. It empowers users to act on real-time patterns, improve service delivery, and make data-informed decisions while following responsible AI practices around fairness, transparency, and data privacy.
    ```
1. Provide the below instruction under the **Instruction (3)** box.

    ```
    You are an agent, designed to enhance operational efficiency through automation, insights, and informed action.

      - Ticket Triage: Analyze incoming support tickets from SharePoint or connected sources, categorize by priority and topic, and recommend appropriate routing based on support roles.

      - Research: Summarize policies or documents for customer service use. Generate FAQs, compare procedures, and highlight missing or unclear areas that may affect operations.

      - Analytics: Analyze structured data (SharePoint Lists, Excel files) to detect recurring issues, suggest improvements, evaluate KPIs, and recommend content updates that reduce ticket volume.

      - Generate knowledge base articles using context-aware language, bullet points, and clear instructions that align with real customer needs.

      - Responsible AI: Ensure that all responses are transparent, respectful of user data, grounded in provided content, and free of bias. Acknowledge limitations when input is unclear or context is missing. Never fabricate answers, and always prioritize clarity, accuracy, and integrity.
    ```     

    ![img](../media/Lab3c-12-8.png)

1. On the **Knowledge** section, paste the **ContosoCorp<inject key="DeploymentID" enableCopy="false"/> SharePoint site URL** into the **Add specific websites** box **(1)** you have copied on the previous step, then from the **Suggested** results, select the **ContosoCorp<inject key="DeploymentID" enableCopy="false"/> SharePoint site URL (2)**.

   ![img](../media/l3-t3-6.png)

   - Verify that the selected SharePoint site appears under the **SharePoint** section **(4)**, confirming that the knowledge source has been successfully added.
     
     ![img](../media/Lab3c-12-9.png) 

1. On the **Copilot Studio** page, review the agent details and then click **Create** on the top-right corner.

   ![img](../media/Lab3c-12-10.png)  

1. A dialogue box will appear, select **Go to agent**.

    ![img](../media/Lab3c-12-11.png)

1. Now the **Ticket_Triage_Agent** is ready to use. We can provide prompts now.
   
1. To see how the agent classifies incoming tickets based on urgency and topic, please provide the below prompt:

    **Prompt:**
    ```
    You are an AI support agent tasked with categorizing incoming customer tickets based on their content. Respond in a structured table format with the ticket ID, priority, and category.    
    ```

    **Expected Outcome**

     ![img](../media/30-9-l3-7.png) 

      > **Note:** Sometimes the output may not appear on the first attempt. Please try resending the prompt to get the expected result. If the expected output is still not displayed, proceed with the subsequent steps without waiting. After completing all lab exercises, you may revisit this step and run the prompt again, as the expected output may take several hours to appear due to **SharePoint knowledge indexing latency**, which can temporarily prevent the custom agent from referencing site information.

1. Ask the agent to define the logic for classifying tickets into categories, please provide the below prompt:

    **Prompt:**
    ```
    How should tickets be categorized based on priority? 
    ```
    **Expected Outcome**

     ![img](../media/lab3c-12-s11.png)

1. Ask the agent to generate FAQs, please provide the below prompt:

    **Prompt:**
    ```
    Generate FAQs based on ticket trends and common customer inquiries.
    ```
    **Expected Outcome**

     ![img](../media/lab3-1-3.png)
    
1. Please provide the below prompt for the recommendation about the knowledge base.

    **Prompt:**
    ```
    Recommend updates to the knowledge base to reduce ticket volume.
    ```
    **Expected Outcome**

     ![img](../media/lab3-1-4.png)

1. Please use the below prompt to draft a knowledge base article:

    **Prompt:**
    ```
    Draft a knowledge base article that resolves frequently occurring support ticket issues, using historical ticket data to identify patterns and include relevant insights that make the FAQ more impactful.
    ```
    **Expected Outcome**

     ![img](../media/lab3-1-5.png)

1. Please use the below prompt to compare pre-triage backlog vs. optimized workload distribution.

    **Prompt:**
    ```
    Compare the volume and average handling time of tickets in the pre-triage backlog period versus the post-implementation phase of optimized workload distribution. Analyze improvements in resolution time, first response SLAs, and customer satisfaction scores. Highlight any reduction in ticket aging and workload imbalance across support teams. Provide data-driven insights to support continuous optimization.
    ```
    **Expected Outcome**

     ![img](../media/lab3-1-6.png)

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="c37b7e87-cbde-4659-9aaa-f7c4d5af0645" />

### Task 4: Pre-Built Agent- Researcher

This task focuses on utilizing the pre-built Researcher Agent to extract, synthesize, and communicate insights from a variety of data sources to support strategic research and informed decision-making. Additionally, Microsoft 365 Copilot will be used to handle general research queries. Through structured prompts, the agent will identify emerging trends, deliver executive-level summaries, extract key data points, curate credible resources, and compare insights across multiple sources.

1. Go to **Microsoft 365 Copilot** then select **Research agent** from the Agent Store.

   ![img](../media/m-l1-16.png) 

1. By selecting **Research agent**, please provide the below prompt to find out the industry benchmarking of similar kinds of organizations. If the agent is asking more questions, select the report length by clicking Short or Long based on your requirement, and then provide **Go ahead**:

    **Prompt:**
    ```
    Retrieve industry benchmarks from the past year for consulting services firms in the U.S. with 500–1000 employees, focusing on revenue growth, employee productivity, and client satisfaction.
    ```
    **Expected Outcome**

     ![img](../media/Lab3c-12-14.png) 

     ![img](../media/m-l1-17.png)      

      >**Note:** `Please proceed with the next step as this step takes time to complete`.

      - After `10-15 minutes`, you can come back and check again. By selecting **Researcher (1)** and then selecting the provided prompt in the History section **(2)** to view the expected output as shown in the above screenshot

        ![img](../media/lab3-1-8n.png)   
   
1. Select **Chat (1)** from the **Microsoft 365 Copilot**,  prompted to investigate the top trends in the renewable energy market for 2025 and summarize key insights in bullet points. Please provide the below prompt **(2)** and then **Send (3)**:

    **Prompt:**
    ```
    Research and summarize the top trends shaping the renewable energy market in 2025. Provide a concise bullet-point list highlighting emerging technologies, key market players, and notable innovations. Include citation links to credible sources for each insight to support further exploration.
    ```

    ![img](../media/Lab3c-12-15.png) 

    **Expected Outcome**

     ![img](../media/lab3-1-7.png) 

1. Go to **Researcher Agent** again and see the previous prompt result, then ask What technologies are shaping the future of remote work? Please provide the below prompt. If the agent is asking more questions, select the report length by clicking Short or Long based on your requirement, and then provide **Go ahead**:

    **Prompt:**
    ```
    What technologies are shaping the future of remote work?
    ```

    ![img](../media/Lab3c-12-17.png) 

    **Expected Outcome** 

     ![img](../media/12-9-m38.png)

      >**Note:** Please proceed with the next step, as this step takes time to complete.

1. Go to **Chat** in **Microsoft 365 Copilot**, then request the agent to curate the five best publicly available guides or whitepapers on AI governance. Please provide the below prompt: 

    **Prompt:**
    ```
    Create a list of the most authoritative and publicly available guides or whitepapers on AI governance. For each resource, include the title, a direct URL, a brief description of its contents, and a short explanation of why it is relevant or valuable for understanding responsible AI practices.
    ```
    **Expected Outcome**

     ![img](../media/lab3-1-8.png) 
   
1. Access two policy briefs (e.g., from WHO and CDC) on pandemic response, and ask the agent to summarize areas of alignment and divergence. Please provide the below prompt:

   **Prompt:**
    
   ```
   Compare the two provided policy briefs on pandemic response—one from the World Health Organization (WHO) and the other from the Centers for Disease Control and Prevention (CDC). Summarize the key areas of alignment and divergence in a side-by-side format. Focus on response strategies, communication approaches, public health measures, and long-term preparedness. Include synthesized commentary to highlight implications or notable differences in global versus national perspectives.
   ```
1. If the agent is asking more questions, please provide **Go ahead**.
    
   **Expected Outcome**

    ![img](../media/Lab3c-12-19.png)

After completing this step, you can go back to the Researcher agent and check the response there.

In this task, you have explored how the Researcher Agent and the Microsoft 365 Copilot Agent differ in their capabilities, data sources, and use cases.

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="5710aaad-68c3-46e0-a232-004c0f33e5c6" />

### Review

This interactive exercise empowers support teams to resolve customer issues more efficiently by leveraging Copilot Chat and Copilot Studio. Participants walk through real-world tasks such as summarizing policy documents, generating FAQs, and automating triage workflows with SharePoint integration. The exercise culminates in hands-on research using a pre-built agent to explore trends, extract facts, and compare policy briefs demonstrating a measurable impact on reducing ticket volume and enhancing operational clarity.

Successfully completed the below tasks:

 - Upload and Summarize the Support Policy
 - Refining Support Documentation
 - Automating Ticket Triage with Copilot Studio
 - Pre-Built Agent- Researcher
    
**You have successfully completed the lab. Click on Next >>**

![Start Your Azure Journey](../media/gci7.png)
