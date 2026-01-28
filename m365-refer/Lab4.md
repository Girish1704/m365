# Exercise 4: HR Onboarding Crisis

#### Estimated Duration: 30 Minutes

### Overview: 

This hands-on lab invites participants, acting as Transformation Leads, to proactively streamline HR onboarding using Microsoft Word, Visual Creator, and Copilot Studio. While onboarding 50 new hires in just two weeks may seem high-pressure, the exercise highlights how Copilot technologies don’t just solve for “chaos” and “crisis” they also empower teams to optimize everyday business operations. Participants will craft personalized onboarding modules, summarize critical checklists for quick reference, and enhance document layouts to improve employee engagement. Additionally, they’ll build and deploy an HR FAQ agent that automates common inquiries and gathers feedback, significantly reducing repetitive workload. By the end of the session, participants will demonstrate how strategic automation and intelligent design with Copilot can accelerate onboarding timelines by 30% and elevate HR operational efficiency across both routine and complex workflows.

>**Note:** `Copilot may generate outputs that differ slightly from the screenshots provided please proceed with the workflow as expected`.

### Objectives: 

+ **Task 1:** Introducing the HR Onboarding Challenge 
+ **Task 2:** Drafting a Personalized Onboarding Guide in Word 
+ **Task 3:** Deploying an HR FAQ Agent with Copilot Studio 

### Task 1: Introducing the HR Onboarding Challenge

This task will clearly introduce the HR onboarding challenge by highlighting the urgent need to scale onboarding for 50 new hires within a short timeframe. Emphasize key pain points, limited time for sessions, repetitive queries, and lack of personalized content to set the stage for implementing AI-driven solutions that streamline the process and enhance the employee experience.

1. In the virtual machine (VM) desktop, type **PowerPoint (1)** in the search bar and select **PowerPoint (2)** from the results to open.

   ![img](../media/7-10-lab1-3.png)

1. Select the **Blank Presentation**. Once the presentation opens, click on the **Copilot icon** from the top right corner and then provide the **below prompt (2)** to display the slide titled “HR Onboarding Crisis” with the explanation of the challenge and discuss key pain points.

   **Prompt:**
    ```
    Create a slide titled ‘HR Onboarding Crisis.’ Provide a brief overview of the current challenge faced by the HR department: onboarding 50 new hires in just two weeks with limited resources. Emphasize the key pain points—insufficient time for individualized sessions, high volume of repetitive questions from new hires, and the lack of personalization in current onboarding materials. Highlight the urgency to streamline the process and reduce HR overhead while maintaining a high-quality onboarding experience.
    ```
   **Expected Outcome**
   
   ![img](../media/30-9-l4-1.png)

   > **Note:** <span style="color:red;">If Copilot does not create the presentation as expected, it may take additional time due to <b>indexing delay</b>. In such cases, follow the alternative approach below.</span>

      1. In the **Home** tab, select **New Slide with Copilot**.

         ![img](../media/7-10-lab2-4.png)

         >**Note:** If **New Slide with Copilot** is not visible under the **Home** tab, switch to the **Insert** tab and select **New Slide with Copilot**. If it still does not appear, close PowerPoint and reopen it by selecting **Create with Copilot** from the start screen.

      1. In the **Add a slide with Copilot** window, paste the following prompt in the text box **(1)**, and then click the **Send (2)** button.

         ![img](../media/7-10-lab4-1.png)

      1. Review the generated slide. If satisfied with the output, click **Keep it** to insert the slide into the presentation, then press **Ctrl + S** and click **Save**.
    
         ![img](../media/7-10-lab4-2.png)

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="2d2dd696-f7e1-48e3-b8cd-ad387e4c6abc" />

### Task 2: Drafting a Personalized Onboarding Guide in Word

This task will empower HR teams to efficiently create a clear, personalized onboarding guide using Microsoft Word, Copilot, and Visual Creator. The goal is to streamline content generation, enhance clarity through quick-reference summaries, and elevate visual presentation, ensuring new hires receive a cohesive, engaging introduction to company policies, workflows, and expectations.

1. On the Windows taskbar, click the **Search** icon, type **Word (1)**, and select the **Word app (2)** to open it.
   
    ![img](../media/7-10-lab4-3.png)

    >**Note:** If you see a **“Your privacy matters”** pop-up, select **Close** to proceed.

    >**Note:** If prompted, sign-in with the credentials, **Email/Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>.

1. Select the **Blank document**, then enter the below prompt in the **“What do you want Copilot to draft?”** box.

   ![img](../media/7-10-lab4-5.png)

   **Prompt:**
   ```
   Create a comprehensive onboarding module tailored for a cohort of 50 new employees joining the company. Include a personalized welcome message from the CEO, an overview of key company policies, standard workflows, and role-specific expectations. Ensure the content is engaging, easy to navigate, and designed to support consistent onboarding at scale while reflecting the company’s values and culture.
   ```

   **Expected Outcome**

   ![img](../media/7-10-lab4-4.png)

1.  Click **Keep it**, then press **Ctrl + S** to save the document, and click **Save**.

1. Scroll down to the bottom of the Word document and select **Draft with copilot (1)**, then provide the below prompt to update the checklist **(2)**, then select **Generate (3)**.

   **Prompt:**
   ```
   Update the contents of this onboarding checklist into a one-page quick start guide designed for new employees. Ensure the summary highlights essential actions, key policies, and critical setup steps in a clear, easy-to-read format. Use headers and bullet points for readability, and aim to help new hires quickly understand what they need to do in their first days.
   ```
   ![image](../media/additionalex4img4.jpg)

   **Expected Outcome**

   ![image](../media/additionalex4img5.jpg)

1. Enhance Visual Appeal with Visual Creator, provide the below prompt: 

   **Prompt:**
   ```
   Format the onboarding guide using Visual Creator to improve readability and visual appeal. Include structured sections with clear headers, bullet points, and iconography where appropriate. Apply consistent styling aligned with Contoso’s branding—such as logo placement, brand colours, and typography. Ensure the layout is clean, professional, and easy for new employees to navigate.
   ```
   **Expected Outcome**
   
   ![image](../media/additionalex4img6.jpg)    

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="36c58ce3-ee58-4e18-a8da-cd7744aa13b1" />

### Task 3: Deploying an HR FAQ Agent with Copilot Studio 

The objective of this task is to design, build, and deploy an HR FAQ conversational agent using Copilot Studio that addresses common onboarding queries and collects feedback from new hires. This task aims to enhance the onboarding experience by providing real-time, accessible support and enabling continuous improvement through structured feedback mechanisms integrated into Microsoft Teams or internal HR platforms.

1. Follow these steps to obtain the SharePoint site URL required for the upcoming tasks:

    - Navigate to the **Microsoft 365 Copilot** desktop app, select **Apps (1)** from the left navigation pane, and then choose **SharePoint (2)**.

      ![img](../media/Lab3c-12-7.png)  

       - If prompted, sign-in with the credentials, **Email/Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>.   

    - Click on the **My Sites (1)** and then select **ContosoCorp<inject key="DeploymentID" enableCopy="false"/> (2)**

      ![img](../media/sg2.png)     

1. Please select **+ New (1)** and then select **Agent (2)**.

    ![img](../media/12-9-m43.png)

1. On **Create your new agent** apge, select **Edit**.

    ![img](../media/m-l1-19.png)

1. Provide name as **HR FAQ Agent (1)**.

1. On the **Purpose (2)** box, provide the below description:

   ```
   This conversational agent is designed to support new hires by answering frequently asked questions related to the onboarding process. It provides quick, accurate responses based on HR documentation and policies, helping employees navigate their first days with confidence. The agent also collects feedback to continuously improve the onboarding experience.
   ```

   ![img](../media/m-l1-20.png)

1. Select **Sources (3)** tab and please make sure **ContosoCorp<inject key="DeploymentID" enableCopy="false"/> (4)** site is selected and **Sourced from entire site (5)** is selected, then select **Behaviour (6)** tab and scroll down, On **Agent Instructions (7)** box provide the below instruction, then **Save and close (8)**.

   ```
     - Respond only to questions related to onboarding, HR policies, and new hire procedures.
     - Use clear, friendly, and professional language in all responses.
     - Prioritize accuracy by referencing the latest HR documentation and onboarding materials.
     - When asked about topics outside onboarding scope (e.g., payroll, benefits), politely redirect the user to the appropriate HR contact          or resource.
     - If the user requests to provide feedback, offer a link to the onboarding feedback form or present it directly using an embedded form          by using Adaptive card
    -  Ensure responses are inclusive and accessible to users from diverse backgrounds and roles.
    -  Avoid making assumptions—ask clarifying questions if the user query is vague or ambiguous.
   ```
    ![img](../media/12-9-m46.png)
 
    ![img](../media/m-l1-21.png)
    
1. You can pass various prompts to test it out.

   Examples of questions you handle:
   - "Where can I find the onboarding checklist?"
   - "How do I enroll in health benefits?"
   - "What time does my first team meeting start?"
   - "Who do I contact for laptop setup issues?"
   - "How do I share feedback on the onboarding experience?"

> **Congratulations** on completing the task! Now, it's time to validate it.
<validation step="fb23c881-0a35-4c81-82da-5e19a008ab05" />

### Review

In this exercise, participants help HR Manager Sophia address a high-pressure onboarding crisis involving 50 new hires in just two weeks. They create a personalized onboarding guide using Word and Visual Creator, incorporating CEO messages, policy summaries, and visual enhancements. Then, they deploy a conversational HR FAQ agent in Copilot Studio to automate responses and collect new hire feedback. By the end, the team achieves a 30% improvement in onboarding efficiency while easing HR workload and enhancing the new hire experience.

Successfully completed the below tasks for prompting:

- Introducing the HR Onboarding Challenge
- Drafting a Personalized Onboarding Guide in Word 
- Deploying an HR FAQ Agent with Copilot Studio 
    
**You have successfully completed the lab, Click on Next >>**

![Start Your Azure Journey](../media/gci7.png)
