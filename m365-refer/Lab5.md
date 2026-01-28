# [Optional] Exercise 5: Scaling with Procurement Agent – AI-Powered Procurement

#### Estimated Duration: 45 Minutes

### Overview

In this exercise, participants will act as transformation leads tasked with revolutionizing procurement operations through AI automation. Using Copilot Studio, they will design and deploy a smart Procurement Agent that automates contract review, ensures policy compliance, and flags risks through SharePoint-integrated document analysis. In parallel, they’ll leverage Copilot Chat to examine vendor pricing trends, suggest cost-saving strategies, and streamline vendor selection and approval workflows. By the end of the exercise, participants will demonstrate how AI-powered tools significantly enhance procurement efficiency, reducing manual approvals, accelerating contract turnaround, and enabling more strategic, data-informed decision-making across the procurement lifecycle.

### Objectives

+ **Task 1:** Building a Procurement Agent in Copilot Studio 
+ **Task 2:** Automating Vendor Selection & Cost Optimization with Copilot Chat 

 ### Task 1: Building a Procurement Agent in Copilot Studio

The objective of this task is to design and deploy an AI-powered Procurement Agent in Copilot Studio that automates contract review, ensures compliance with procurement policies, and delivers intelligent recommendations. By integrating with SharePoint and leveraging smart prompts, the agent streamlines document analysis and enhances procurement decision-making.

1. Follow these steps to obtain the SharePoint site URL required for the upcoming tasks:

    - Navigate to the **Microsoft 365 Copilot** desktop app, select **Apps (1)** from the left navigation pane, and then choose **SharePoint (2)**.   

      ![img](../media/Lab3c-12-7.png)  

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

1. Provide the name as: **Procurement Agent (1)**.

1. Enter the below text in the **Description (2)** box and click on **Save (3)**.

   ```
   This agent is designed to streamline procurement operations by automating contract review, policy compliance checks, and vendor analysis. Integrated with SharePoint, it retrieves and analyzes Statements of Work (SOWs), flags non-compliant clauses using AI-powered keyword detection, and provides smart recommendations for legal review and risk mitigation. This agent empowers procurement teams to accelerate decision-making, reduce manual workload, and ensure consistent adherence to organizational policies—all within a secure, low-code environment.
   ```

   ![image](../media/lab5-e5-7.png)

1. Scroll down and in the **Instruction** section, select **Edit**

    ![image](../media/lab5-e5-8.png)

1. Provide the following instructions on the **Instruction (1)** box and click on **Save (2)**.

   ```
   - Respond only to queries related to Statements of Work (SOWs), contract compliance, procurement policy, and vendor evaluation.
   - Retrieve documents and data from the connected SharePoint list containing procurement records.
   - When analyzing a document, review for:
     - Non-compliant terms (e.g., missing clauses, conflicting conditions)
     - Risks related to pricing, legal gaps, or ambiguous commitments
     - Clauses needing legal review based on organizational guidelines
   - Use clear, formal language and provide structured summaries with bullet points or highlights.
   - When prompted, generate insights using the following smart instructions:
     - Highlight contract terms that don’t align with procurement policies.
     - Summarize key clauses that need legal review.
     - Identify potential risks in this SOW.
   - If unable to determine compliance, suggest escalation to a procurement or legal reviewer.
   - Maintain a professional and concise tone; avoid speculation or recommending unverified actions.
   ```
   
1. Scroll down and select **+ Add knowledge (3)** to provide the SharePoint list and the documents knowledge to the agent.

   ![image](../media/lab5-e5-9.png)
   
1. Select **SharePoint** from the **Add Knowledge** window.

   ![image](../media/m-l1-24.png)

1. Enter the SharePoint site Contoso Corp link **(1)** and select **Add (2)**.

   ![image](../media/12-9-m51.png)
   
    >**Note:** If the site link shows **This item was not found in your SharePoint or OneDrive files**, this may occur due to temporary indexing delays. Select **Add anyway** to continue. 

     ![image](../media/lab5-12-1.png)

    >**Note:** Provide the **SharePoint link** that you have copied in **Task 1--> Step 1** which looks similar to (For example: https://copilotimmersionlabs100004.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/>)     

1. Select **Add to agent** to add the knowledge to the agent.

    ![image](../media/m-l1-25.png)

1. Select **Topics (1)**, select **All (2)**, then select **Conversation Start (3)**.

   ![image](../media/lab5-e5-10.png)

1. Keep the first sentence in the message box and update the message by entering the following text **(1)**. Now, select **Save (2)**:

   ```
   I’m here to help you review contracts, check compliance with procurement policies, and identify potential risks in Statements of Work (SOWs).
   You can ask me to summarize key clauses, flag deviations, or recommend the next steps based on best practices.
   Let’s streamline your procurement process—what would you like to review today?
   ```

   ![image](../media/30-9-l4-2.png)

1. Select **Topics (1)** again, choose **+ Add a topic (1)** and then select **Add from description with Copilot (3)**.

    ![image](../media/lab5-e5-11.png)

1. On the **Add from description with Copilot** page,

   - For **Name your topic**, enter **Procurement Entry (1)**
   
   - For **Create a topic to...**, enter **User want to submit procurement entry (2)**
   
   - Then select **Create (3)**.

     ![image](../media/12-9-m56.png)

1. On the newly created **Procurement Entry** topic, you can see the **Trigger node**, the **Describe what topic does** box, and its content. Just review the content.

   ![image](../media/m-l1-27.png)

1. Continue to the **message node**, and please update the message with the below text **(1)** and click **Save (2)**:

   ```
   Please provide the details for the procurement entry by using the below form.
   ```
   
   ![image](../media/m-l1-28.png)

1. Review the next nodes by scrolling down the window, and you can see multiple **question nodes** and finally a **message node** at the end.

   > **Note:** If you only see a **Trigger node** and a **Message node**, you can skip the deletion steps below and continue to the next step.

1. Please remove all the **question nodes** by clicking on the **ellipsis (...) (1)** button, and then selecting **Delete (2)**. Repeat this step until you delete all the question nodes, including the last message node.

   ![image](../media/m-l1-29.png)

1. Delete the last **message node** as well, by clicking on **ellipsis(...) (1)** button and then select **Delete (2)**.

   ![image](../media/amc59.png)

1. Now you have the **Trigger node** and a **message node** only in Procurement Entry topic.
   
   ![image](../media/m-l1-30.png)

1. Select **Add node (1)** after the message node and then click on **Ask with adaptive card (2)**.

   ![image](../media/12-9-m60.png)

1. Select **Ellipsis(...) (1)** of the Adaptive card node, then select **Properties (2)**.

   ![image](../media/12-9-m61.png)

1. Select **Edit adaptive card**.
   
   ![image](../media/ex5img25.jpg)

1. Enter the following Adaptive Card Script into the **Card payload editor** of the Adaptive card designer window after removing the existing script.

   ```
   {
  "$schema": "https://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.5",
  "body": [
    {
      "type": "TextBlock",
      "text": "📝 Procurement Contract Entry",
      "weight": "Bolder",
      "size": "Medium"
    },
    {
      "type": "Input.Text",
      "id": "sowTitle",
      "placeholder": "Enter Statement of Work Title",
      "label": "SOW Title"
    },
    {
      "type": "Input.Text",
      "id": "vendorName",
      "placeholder": "Enter Vendor Name",
      "label": "Vendor Name"
    },
    {
      "type": "Input.Number",
      "id": "contractValue",
      "label": "Contract Value",
      "min": 0
    },
    {
      "type": "Input.ChoiceSet",
      "id": "complianceStatus",
      "label": "Compliance Status",
      "choices": [
        {
          "title": "Compliant",
          "value": "Compliant"
        },
        {
          "title": "Needs Review",
          "value": "Needs Review"
        },
        {
          "title": "Non-Compliant",
          "value": "Non-Compliant"
        }
      ]
    },
    {
      "type": "Input.ChoiceSet",
      "id": "pastExperience",
      "label": "Past Experience in Similar Projects",
      "choices": [
        {
          "title": "Yes",
          "value": "Yes"
        },
        {
          "title": "No",
          "value": "No"
        }
      ],
      "style": "expanded"
    },
    {
      "type": "Input.Number",
      "id": "totalExperienceYears",
      "label": "Total Experience (Years)",
      "min": 0
    }
  ],
  "actions": [
    {
      "type": "Action.Submit",
      "title": "Submit Contract Entry"
    }
  ]
}  
      ```

27. After entering the script, you can see the form design at the top. Now, select **Save (1)** and then click **Close (2)**.

    ![image](../media/12-9-m62.png)

1. **Close** the **Adaptive card node properties** window. You can now see that the adaptive card has been added successfully.

   ![image](../media/amc62.png)

1. Now, expand the **Output** section of the Adaptive card and make all the variables global for accessing them on a Power Automate flow. To do so, please select the variable **(1)**, and from the properties window select **Global (2)**. `Repeat it for all variables in that section`.

   ![image](../media/12-9-m63.png)

1. Then select **Save**.   

   ![image](../media/12-9-m64.png)

1. Select **Add node (1)** after the Adaptive card node, choose **Add a tool (2)** and then select **New Agent flow (3)**.

   ![image](../media/12-9-m65.png)

1. Select the **When an agent calls the flow (1)** action and click on **+ Add input (3)** under the **Parameters (2)** section from the side screen.

   ![image](../media/30-9-l4-4.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon** on the top-right of the action card to open it for a clearer view and better experience.

   ![image](../media/30-9-l4-3.png)

1. Select **Text**.

   ![image](../media/lab5-e5-12.png)

1. Provide the input name as **SOWTitle**.

   ![image](../media/12-9-m67.png)

1. Select **+ Add an input**.

1. Select **Text** and then provide the input as **VendorName (1)**.

    ![image](../media/12-9-m68.png)

1. Select **+ Add an input (2)**.

1. Select **Number**.

   ![image](../media/12-9-m69.png)

1. Then provide the input as **ContractValue**.

1. Continue adding the following variables:

   - **ComplianceStatus** Type is `Text`.
   - **PastExperience** Type is `Text`.
   - **TotalExperience** Type is `Number`.

     ![image](../media/12-9-m70.png)

1. Select the **+ (1)** button to add an action and type **SharePoint (2)** on the search box of the side screen and then select **Create item (3)**.

   ![image](../media/30-9-l5-1.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon** on the top-right of the action card to open it for a clearer view and better experience. 

    ![image](../media/30-9-l4-5.png)

1. Select **Sign in**.

   ![image](../media/12-9-m72.png)

1. Sign in with the credential **<inject key="AzureAdUserEmail"></inject>**.

1. If prompted, select **Allow access**.

   ![image](../media/12-9-m73.png)

1. On the **Create item** action, from the side screen, under the Parameters section,
 
   - Site Address: Contoso Corp<inject key="DeploymentID" enableCopy="false"/> - https://domainname.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/> SharePoint site link **(1)**
   
   - List name: Select **Procurement_Contracts_Repository_List (2)** list
   
   - Title: Enter **Procurement_Contracts_Repository (3)**

   - Then click **Show all (4)**
   
     ![image](../media/12-9-m74.png)

1. Under **Advanced parameters**, please select the boxes of **Title, Vendor Name, Proposed Contract Value, Compliance Status, Past Experience in Similar Projects, Total Experience (Years)**, then click on the **dynamic content** icon and then select the corresponding value from the Input parameters.

   ![image](../media/12-9-m75.png)
   
   ![image](../media/12-9-m76.png)

1. Select the **+ (1)** button to add an action and type **Condition (2)** in the search box of the side screen, and then select **Condition (3)** from the control section.

   ![image](../media/30-9-l5-2.png)

1. On the side screen of the **Condition** control, click on choose a value box and select the **dynamic content** icon to choose the value.

   ![image](../media/12-9-m78.png)

   > **Note:** If the side panel does not open automatically, click the **panel icon** on the top-right of the action card to open it for a clearer view and better experience.

   ![image](../media/30-9-l4-6.png)

1. Search and select the **Proposed Contract Value (1)** of SharePoint list and select **is less than (2)** then enter **500000 (3)** as the value.

   ![image](../media/12-9-m79.png)

1. Under the **True** section, select the **+ (1)**, then type **Update item (2)** in the search box of the side screen and then select **Update item (3)**.  

   ![image](../media/lab5c-12-1.png)

1. Enter the following details under the parameters section of the side screen:

   | Site Address | List Name | Id | Title |
   |--------------|-------------------|----------------------|----------------------|
   | Contoso Corp<inject key="DeploymentID" enableCopy="false"/> - https://domainname.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/> **(1)** | **Procurement_Contracts_Repository_List (2)**  | Select SharePoint **ID (3)** | Enter **Procurement_Contracts_Repository (4)** |

   - Click on **Show all**

     ![image](../media/12-9-m80.png)

     > **Note:** When the **Change connection** window appears, select the **existing SharePoint connection** 

   - Under the **Approval Status** type as **Rejected**

     ![image](../media/12-9-m81.png) 

     > **Note:** If the side panel does not open automatically, click the **panel icon** on the top-right of the action card to open it for a clearer view and better experience.

     ![image](../media/30-9-l4-7.png)
      
1. Under **False** select **+ (1)** button to add an action and type **Condition (2)** in the search box of the side screen and then select **Condition (3)** from the control section.

   ![image](../media/30-9-l5-4.png)

1. On the Condition side screen under **Parameters** in the formula box, 

   - Search for **Past experience on similar projects (1)** and select **Past experience on similar projects (2)** field from the SharePoint list,
   
     ![image](../media/lab5-12-4.png)
   
    - Then select **is equal to (1)**, 
    - Then provide the value as **Yes (2)**
    - Then in the formula box select **Total experience (Years) (3)** from the SharePoint list, then select **is greater than (4)** , then provide the value as `2` **(5)**. Finally, the conditions look like the image below:

       ![image](../media/lab5-12-5.png)
 
1. Under the **True** node of the sub condition flow, select the **+ (1)** button to add another action, then type **Update item (2)** in the search box of the side screen, and then select **Update item (3)**.

   ![image](../media/lab5c-12-2.png)

1. Provide the following details on the **Parameters** tab:

   | Site Address | List Name | Id | Title |
   |--------------|-----------|----|------|
   | Contoso Corp<inject key="DeploymentID" enableCopy="false"/> - https://domainname.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/> **(1)** | **Procurement_Contracts_Repository_List (2)**  | Select SharePoint List **ID (3)** | Enter **Procurement_Contracts_Repository (4)** |

   - Click on **Show all (5)**

     ![image](../media/12-9-m85.png)

   - Set the **Approval status** as  `Approved`

     ![image](../media/12-9-m86.png)

1. Under the **False** node of the sub condition flow, select the **+ (1)** button to add another action, then type **Update item (2)** in the search box of the side screen, and then select **Update item (3)**.

   ![image](../media/30-9-l5--7.png)

1. Provide the following details on the **Parameters** tab:   

   | Site Address | List Name | Id | Title |
   |--------------|-----------|----|----|
   | Contoso Corp<inject key="DeploymentID" enableCopy="false"/> - https://domainname.sharepoint.com/sites/ContosoCorp<inject key="DeploymentID" enableCopy="false"/> **(1)** | **Procurement_Contracts_Repository_List (2)**  | Select SharePoint List **ID (3)** | Enter **Procurement_Contracts_Repository (4)** |

   - Click on **Show all (5)**

     ![image](../media/12-9-m88.png)

   - Set the **Approval Status** as `Pending for review`

     ![image](../media/12-9-m89.png)  

1. Your conditional flow looks like this:

   ![image](../media/lab5c-12-3.png)

1. Select **Publish**.

   ![image](../media/30-9-l5-8.png)

1. Then select **Go back to the agent**.

   ![image](../media/12-9-m90.png)

1. From the Procurement entry topic, select the Power automate input variable by clicking on **... (1)**, search for each variable **(2)** and select each variable accordingly from the properties window **(3)**.

   ![image](../media/12-9-m91.png)

1. Select **+ (1)** to add the final node, then select **Send a message (2)**.

   ![image](../media/ci52.png)

1. Enter the below message in the newly added message box **(1)** and then select **Save (2)**:

   ```
   You have successfully submitted the Procurement details.
   ```

   ![image](../media/a21.png)

1. Click on **Save** and then select **Publish**.

   ![image](../media/lab5c-12-4.png)

1. Click on **Publish** again.

   ![image](../media/lab5-12-01.png)

1. Select **Channels (1)**, then select **Teams and Microsoft 365 Copilot (2)**.

   ![image](../media/m-l1-31.png)

1. Please make sure the check box of **Make agent available in Microsoft 365 Copilot (1)** enabled and then select **Add Channel (2)**.

   ![image](../media/a25.png)

1. **Close** the page.

   ![image](../media/12-9-m94.png)

1. After adding it, please **Publish** the agent again. This step is crucial for deploying the agent in Microsoft 365 Copilot.

   ![image](../media/lab5c-12-5.png)

1. Click on **Publish** again.   

   ![image](../media/lab5-12-01.png)   

1. Select **Channels (1)**, then select **Teams and Microsoft 365 Copilot (2)**.

   ![image](../media/m-l1-31.png)

1. Select the **See agent in Microsoft 365** option from the side screen

   ![image](../media/m-l1-32.png)

1. Select **Add** to deploy it in Microsoft 365 Copilot.

   ![image](../media/12-9-m97.png)

1. **Your procurement agent is now available in Microsoft 365 Copilot.** Open the **Microsoft 365 desktop app**, and from the left panel, select **Procurement Agent** under **Agents** to access it.

   ![image](../media/lab5c-12-6.png)

   > **Note:** After adding the agent, if it opens in a browser, **open the Microsoft 365 desktop app** to access the deployed agent.  If you don’t see the newly created agent in the app, **sign out** and then **sign back in** using credentials. 

    ![image](../media/7-10-lab5-2.png)

1. Please provide the below prompt to understand any gaps in policies:

   **Prompt:**
   ```
   Highlight any missing or ambiguous payment terms in Contoso_Procurement_Data_With_Policies document.
   ```
   **Expected Outcome:**

   ![image](../media/30-9-l4-11.png)
   
1. To identify any risk and deviation flagging, please provide the following prompt:

   **Prompt:**
   ```
   List any clauses that deviate from our procurement policy template.
   ```
   **Expected Outcome**

   ![image](../media/m-l1-33.png)

1. To summarize the critical points in a table format, please provide the following prompt:

   **Prompt:**
   ```
   Provide a table format summary of compliance-critical sections in Contoso_Procurement_Data_With_Policies document.
   ```
   **Expected Outcome**

   ![image](../media/m-l1-34.png)

1. To policy alignments and recommendations, please provide below prompt:

   **Prompt:**
   ```
   Suggest revisions to align this contract with our standard procurement terms.
   ```
   **Expected Outcome**

   ![image](../media/lab5c-12-7.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="1d627e21-2ec7-4af2-b616-ae18d0e73e8d" />

### Task 2: Automating Vendor Selection & Cost Optimization with Copilot Chat 

This task involves leveraging Microsoft 365 Copilot to automate vendor evaluation and procurement strategy by analyzing historical pricing trends, identifying cost-effective suppliers, and recommending opportunities for savings. This enables procurement teams to streamline decision-making, reduce manual approvals, and optimize costs through data-driven insights and AI-powered recommendations.

1. On **M365 Copilot** navigate to the **Chat (1)**, provide the below prompt **(2)** and then **Send (3)**:

   **Prompt:**
   ```
   Access Contoso_Procurement_Data_with_policies document and procurement_contract_repositroy_list and then analyze vendor pricing trends over the past 12 months. Identify any significant fluctuations, seasonal patterns, or anomalies. Highlight vendors with consistent pricing and flag those with frequent or steep increases. Based on this analysis, recommend potential cost-saving opportunities or alternative vendors.
   ```

   ![image](../media/lab5c-12-8.png)

   **Expected Outcome**

   ![image](../media/lab5c-12-9.png)

1. To identify the best value vendors, please provide the following prompt:

   **Prompt:**

    ```
   Access Contoso_Procurement_Data_with_policies document and procurement_contract_repositroy_list and find out which vendors have consistently offered the best value for money over the past year.
   ```

   **Expected Outcome**
   
   ![image](../media/lab5c-12-10.png)

1. To generate a summary report with vendor comparison please provide the following prompt:

   **Prompt:**
   ```
   Calculate the potential percentage savings we could achieve by switching to alternative vendors based on historical pricing and contract data. Generate a summary report with vendor comparisons and projected cost reductions for leadership review.
   ```
   **Expected Output**

   ![image](../media/lab5c-12-11.png)

1. Navigate back to the **Procurement agent (1)** in **Microsoft 365 Copilot**.

1. Enter **Procurement entry (2)** and then **Submit (3)**.

     ![image](../media/m-l1-35.png)

1. A **Procurement entry** agent form will appear.

    ![image](../media/m-l1-36.png)

1. Provide the following different cases to test the agent.

1. On the **Procurement contract entry** form, submit the details of the form with **proposed contract value** less than `500000`. You can see the approval status is **Rejected**.

   - SOW Title: **Finance audit 1 (1)**
   - Vendor name: **Contoso (2)**
   - Contract Value: **400000 (3)**
   - Compliance Status: Choose **Compliant (4)**
   - Past Experience in Similar projects: **Yes (5)**
   - Total experience (Years): **1 (6)**
   - Select **Submit Contract entry (7)**

     ![image](../media/12-9-m104.png)   

1. If prompted, select **Allow** to connect.

   ![image](../media/12-9-m105.png)

1. To see the approval status, navigate to the **Contoso corp<inject key="DeploymentID" enableCopy="false"/>** sharePoint site and follow the following steps.

    ![image](../media/ci55.png)   

1. Select **Site contents** from left panel.

    ![image](../media/12-9-m106.png)

1. Select the **procurement_Contract_Repositroy_List**.
    
    ![image](../media/m-l1-51.png)

1. Scroll down the locate **Finance audit 1**, you can see the approval status is **Rejected**.    

    ![image](../media/12-9-m108.png)

1. Navigate back to the **Procurement agent (1)** in **Microsoft 365 Copilot**.

1. Enter **Procurement entry (2)** and then Submit **(3)**.    

    ![image](../media/m-l1-52.png)

1. Now test for greater than 500000 and also test for Past experience in similar projects with Yes/No and Total experience (Years) with greater than 2 or not.   

1. Lets test for the entry where **proposed contract value** greater than `500000`. for Total experience (Years) with is equal to 2y , you can see the **Approval status** as `Pending for review`.

   - SOW Title: **Finance audit 2 (1)**
   - Vendor name: **Contoso (2)**
   - Contract Value: **600000 (3)**
   - Compliance Status: Choose **Compliant (4)**
   - Past Experience in Similar projects: **Yes (5)**
   - Total experience (Years): **2 (6)**
   - Select **Submit Contract entry (7)**

     ![image](../media/m-l1-37.png) 

1. To see the approval status, navigate to the **Contoso corp<inject key="DeploymentID" enableCopy="false"/>** sharePoint. Scroll down and  you can see the **Approval status** as `Pending for review`.

    ![image](../media/30-9-l4-16.png)

1. Lets test for the entry where **proposed contract value** greater than `500000`. for Total experience (Years) with is greater than 2y , you can see the **Approval status** as `Approved`.

   - SOW Title: **Finanace audit 3 (1)**
   - Vendor name: **Contoso (2)**
   - Contract Value: **600000 (3)**
   - Compliance Status: Choose **Compliant (4)**
   - Past Experience in Similar projects: **Yes (5)**
   - Total experience (Years): **3 (6)**
   - Select **Submit Cotract entry (7)**

     ![image](../media/12-9-m111.png) 

1. To see the approval status, navigate to the **Contoso corp<inject key="DeploymentID" enableCopy="false"/>** sharePoint. Scroll down and  you can see the **Approval status** as `Approved`.

    ![image](../media/30-9-l4-17.png) 

   >**Note:** If you are not able to see Approval status item then refresh the page.


### Review

Microsoft Copilot simplifies the content creation process by identifying top SEO keywords to effectively reach your audience, generating tailored content based on those keywords, and proofreading drafts to meet precise grammar rules. It enhances your work with AI-generated images, turns keywords into compelling headlines and structured section headings, and repurposes your drafts into engaging social media posts optimized for different platforms. 

Successfully completed the below tasks for prompting:

- Building a Procurement Agent in Copilot Studio 
- Automating Vendor Selection & Cost Optimization with Copilot Chat 

    
**You have successfully completed the lab. Click on Next >>**

![Start Your Azure Journey](../media/gci7.png)
