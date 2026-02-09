# Exercise 5: Create and Configure a Copilot Agent in SharePoint to Deliver Contextual Answers

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create a **SharePoint Agent** - an AI-powered assistant that is embedded directly within a SharePoint site. Unlike the M365 Copilot agent you created in Exercise 4, SharePoint Agents are designed to help users discover documents, extract insights, and find specific information within site content.

You will set up a SharePoint site for a law firm (Morrison & Associates) and upload various document types including Word documents and CSV files. The agent will help legal staff:
- Find specific case documents and client information
- Get insights from billing and case tracking data
- Navigate the document library and locate files efficiently

**Key Difference from Exercise 4:**

| Exercise 4 | Exercise 5 |
|------------|------------|
| M365 Copilot Agent | SharePoint Agent |
| Single file upload | Multiple file types (Word + CSV) |
| General assistance focus | Document discovery & data insights |
| Accessed via Copilot Chat | Embedded in SharePoint site |

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create a Law Firm SharePoint site
- Task 2: Upload law firm documents to the site
- Task 3: Create a SharePoint Agent from the site
- Task 4: Configure the agent for document discovery and insights
- Task 5: Test the agent for document search and data analysis

>**Important:** This exercise requires the datasets that were downloaded in Exercise 1. If you haven't completed Exercise 1, please download and extract the datasets from: `https://github.com/CloudLabsAI-Azure/unlock-ai-powered-future-work-with-microsoft-365/archive/refs/heads/Day1-datasets.zip`

### Task 1: Create a Law Firm SharePoint Site

In this task, you will create a SharePoint site to store law firm documents including case files, client information, and billing data.

1. On the Microsoft 365 home page, click on **Apps** from the left navigation panel.

1. Select **SharePoint** from the list of apps.

1. Click on **+ Create site** in the top navigation.

1. Select **Team site** and configure:

   | Field | Value |
   |-------|-------|
   | Site name | `Morrison Law Firm` |
   | Site description | `Document repository for Morrison & Associates Law Firm - case files, client data, and billing information` |
   | Privacy settings | Private |

   ![](../media/m36-copg-ex5-d-g1.png)

1. Click **Create** and wait for the site to be provisioned.

   ![](../media/ex5-site-creating.png)

1. Once created, you will be redirected to your new SharePoint site.

   ![](../media/ex5-site-created.png)

### Task 2: Upload Law Firm Documents to the Site

In this task, you will locate the law firm documents from the datasets you downloaded earlier and upload them to your SharePoint site. These documents include Word documents (contracts, case summaries, policies) and CSV files (client roster, case tracking, billing data).

1. In your SharePoint site, click on **Documents** in the left navigation.

   ![](../media/ex5-documents.png)

1. Click **Documents (1)** in the left navigation, then click **Upload (2)** and select **Folder (3)** to create a new folder.

   | Folder Name | Purpose |
   |-------------|---------|
   | `Templates` | Contract templates and standard forms |
   | `Case Files` | Active case documents and summaries |
   | `Data` | Client rosters, case tracking, and billing data |

   ![](../media/m36-copg-ex5-d-g3.png)

1. Navigate to the folder where you extracted the datasets in Exercise 1. Inside the **law-data** folder, you will find all 7 documents needed for this task:

   **Word Documents (4 files):**
   | Document | Description | Upload To |
   |----------|-------------|-----------|
   | `01-Client-Contract-Template.docx.md` | Standard client engagement agreement | Templates |
   | `02-Case-Summary-Johnson-v-Apex.docx.md` | Active employment discrimination case | Case Files |
   | `03-Legal-Fee-Schedule-2024.docx.md` | Hourly rates and flat fees | Templates |
   | `04-Firm-Policies-Handbook.docx.md` | Employee policies and procedures | Templates |

   **CSV Files (3 files):**
   | Document | Description | Upload To |
   |----------|-------------|-----------|
   | `05-client-roster.csv` | Complete client list with contact info and billing | Data |
   | `06-case-tracking.csv` | Active cases with status and deadlines | Data |
   | `07-billing-summary-2024.csv` | Monthly billing by attorney | Data |

1. Return to your SharePoint site. Navigate to the **Templates** folder.

1. Click **Upload** > **Files**, browse to the **law-data** folder in your extracted datasets, and upload:
   - `01-Client-Contract-Template.docx.md`
   - `03-Legal-Fee-Schedule-2024.docx.md`
   - `04-Firm-Policies-Handbook.docx.md`

1. Navigate to the **Case Files** folder. Click **Upload** > **Files**, browse to the **law-data** folder, and upload:
   - `02-Case-Summary-Johnson-v-Apex.docx.md`

1. Navigate to the **Data** folder. Click **Upload** > **Files**, browse to the **law-data** folder, and upload:
   - `05-client-roster.csv`
   - `06-case-tracking.csv`
   - `07-billing-summary-2024.csv`

### Task 3: Create a SharePoint Agent from the Site

In this task, you will create a SharePoint Agent directly from within the SharePoint site. This agent will help legal staff discover documents and extract insights from both Word documents and CSV data.

1. In your SharePoint site, ensure you are on the **Documents** page or the site home page.

1. Click **+ New (1)**, then select **Create an agent (2)** to start creating a SharePoint agent.

   ![](../media/m36-copg-ex8-e-g21.png)

   >**Note:** The "Create an agent" option allows you to create an AI assistant that is scoped to the current SharePoint site's content.

1. Select **Overview (1)**, enter the agent name in the **Name (2)** field, then enter the purpose in the **Purpose (3)** box.

   | Field | Value |
   |-------|-------|
   | Name | `Legal Document Assistant` |
   | Purpose | `Helps legal staff find case documents, client information, billing data, and provides insights from firm records stored in this SharePoint site.` |

   ![](../media/m36-copg-ex8-e-g22.png)

   >**Note:** A description in the Purpose field is required before you can create the agent.

1. (Optional) To change the agent icon, click **Change** below the icon and select a legal or document-related icon.

1. Select **Sources (1)**, then turn on the **Prioritize sources (2)** toggle.

   ![](../media/m36-copg-ex8-e-g23.png)

1. Verify that the **Morrison Law Firm** site is listed with the **Documents** folder expanded. This means the agent will have access to all documents in your site.

   >**Note:** Up to 20 sources can be chosen for each agent. You can add additional SharePoint sites or OneDrive files if needed.

1. Click on the **Behavior** tab to configure how the agent responds.

### Task 4: Configure the Agent for Document Discovery and Insights

In this task, you will configure the agent's behavior including welcome messaging, starter prompts, and custom instructions.

1. Select **Behavior (1)**, enter a welcome message in the **Welcome messaging (2)** box, enter the agent instructions in the **Agent instructions (3)** field, then click **Create (4)** to finish.

   ```
   Welcome to the Legal Document Assistant! How can I help you?
   ```

1. In the **Agent instructions** field, replace the default text with the following:

   ```
   You are a Legal Document Assistant for Morrison & Associates Law Firm. Your role is to help legal staff find documents, extract information, and provide insights from firm records.

   DOCUMENT DISCOVERY:
   - Help users locate specific documents (contracts, case files, policies)
   - Identify which folder contains the requested document
   - Provide document names and their locations

   CASE INFORMATION:
   - Provide details about active cases from case summaries
   - Look up case status, deadlines, and assigned attorneys
   - Extract key dates and milestones from case documents

   CLIENT DATA:
   - Find client contact information from the client roster
   - Look up client engagement dates and assigned attorneys
   - Provide billing status and outstanding balances

   BILLING & FINANCIAL INSIGHTS:
   - Analyze billing data by attorney or time period
   - Calculate totals and identify trends
   - Provide fee schedule information for different services

   RESPONSE GUIDELINES:
   - Always cite the document and folder where information was found
   - For CSV data, provide specific values and calculations when asked
   - Reply in a professional, formal tone
   - For confidential matters, remind users about attorney-client privilege
   ```

1. Click **Create** at the bottom of the dialog to create the SharePoint Agent.

   ![](../media/m36-copg-ex8-e-g24.png)

1. Click **Chat with agent** to start interacting with your newly created agent.

   ![](../media/m36-copg-ex8-e-g25.png)

1. Use the **Message Copilot** box to enter your prompt and start interacting with the agent in Microsoft 365.

   ![](../media/m36-copg-ex8-e-g26.png)

### Task 5: Test the Agent for Document Search and Data Analysis

In this task, you will test the SharePoint Agent's ability to find documents, locate specific information, and provide insights from the law firm data.

1. Once the agent is created, you will see the chat interface within SharePoint. Start with a document location question:

   **Prompt:**
   ```
   Where can I find the client contract template?
   ```

   ![](../media/ex5-test-location.png)

   **Expected Output:**

   The agent should identify that the **Client Contract Template** is located in the **Templates** folder and provide a brief description of its contents.

   ![](../media/m36-copg-ex8-e-g27.png)

1. Test case information lookup:

   **Prompt:**
   ```
   What is the status of the Johnson v. Apex case? Who is the lead attorney and what are the next steps?
   ```

   ![](../media/m36-copg-ex5-d-g14.png)

   **Expected Output:**

   The agent should provide details from the case summary including:
   - Case status: Discovery Phase
   - Lead Attorney: Sarah Morrison
   - Next deadline: Deposition scheduled
   - Estimated damages: $1,180,000+

1. Test client data lookup:

   **Prompt:**
   ```
   Look up the client TechStart Solutions. Who is their attorney and what is their outstanding balance?
   ```

   ![](../media/m36-copg-ex5-d-g16.png)

   **Expected Output:**

   The agent should find information from the **client-roster.csv**:
   - Client: TechStart Solutions LLC
   - Lead Attorney: David Chen
   - Total Billed: $67,200
   - Outstanding Balance: $12,000

1. Test billing data analysis:

   **Prompt:**
   ```
   How many billable hours did Sarah Morrison have in March 2024? What was her total billed amount?
   ```

   ![](../media/m36-copg-ex5-d-g17.png)

   **Expected Output:**

   The agent should extract from **billing-summary-2024.csv**:
   - Billable Hours: 182
   - Billed Amount: $81,900
   - Collections: $73,700

1. Test fee schedule lookup:

   **Prompt:**
   ```
   What is the hourly rate for a Senior Associate? What about flat fees for an LLC formation?
   ```

   ![](../media/m36-copg-ex5-d-g18.png)

   **Expected Output:**

   The agent should provide from the **Fee Schedule**:
   - Senior Associate hourly rate: $375
   - LLC Formation flat fee: $800

## Summary

In this exercise, you created a **SharePoint Agent** for a law firm that helps legal staff discover documents and extract insights from various file types including Word documents and CSV data files. You learned how to:

- Create a SharePoint site with an organized folder structure
- Upload multiple document types (Word and CSV) to serve as the knowledge base
- Create a SharePoint Agent from within the SharePoint site interface
- Configure agent instructions for document discovery and data analysis
- Test the agent with document location, case lookup, client data, and billing queries

**Key Takeaways:**

| Feature | SharePoint Agent |
|---------|------------------|
| **Access Point** | Embedded in SharePoint site |
| **File Types Supported** | Word documents, CSV files, and more |
| **Primary Use Case** | Document discovery & data insights |
| **Knowledge Scope** | Site-specific content with folder organization |
| **Best For** | Finding documents, analyzing data, extracting specific information |

SharePoint Agents enhance productivity by providing intelligent document and data assistance directly within the context where files are stored, enabling users to quickly find information across multiple document types and data sources.

### You have successfully completed this exercise. Click on Next to proceed to the Day 2 Overview.

SharePoint Agents enhance the user experience by providing intelligent document assistance directly within the context where documents are stored, reducing search time and improving information discovery.

### You have successfully completed this exercise. Click on Next to proceed to the Day 2 Overview.
