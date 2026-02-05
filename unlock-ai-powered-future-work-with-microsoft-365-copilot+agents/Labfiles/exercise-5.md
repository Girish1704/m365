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

### Task 1: Create a Law Firm SharePoint Site

In this task, you will create a SharePoint site to store law firm documents including case files, client information, and billing data.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to the Microsoft 365 portal:

   ```
   https://www.microsoft365.com
   ```

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. On the Microsoft 365 home page, click on **Apps** from the left navigation panel.

   ![](./media/ex5-apps-panel.png)

1. Select **SharePoint** from the list of apps.

   ![](./media/ex5-sharepoint-app.png)

1. Click on **+ Create site** in the top navigation.

   ![](./media/ex5-create-site.png)

1. Select **Team site** and configure:

   | Field | Value |
   |-------|-------|
   | Site name | `Morrison Law Firm-<inject key="DeploymentID" enableCopy="false"/>` |
   | Site description | `Document repository for Morrison & Associates Law Firm - case files, client data, and billing information` |
   | Privacy settings | Private |

   ![](./media/ex5-site-settings.png)

1. Click **Create** and wait for the site to be provisioned.

   ![](./media/ex5-site-creating.png)

1. Once created, you will be redirected to your new SharePoint site.

   ![](./media/ex5-site-created.png)

### Task 2: Upload Law Firm Documents to the Site

In this task, you will download law firm documents from GitHub and upload them to your SharePoint site. These documents include Word documents (contracts, case summaries, policies) and CSV files (client roster, case tracking, billing data).

1. In your SharePoint site, click on **Documents** in the left navigation.

   ![](./media/ex5-documents.png)

1. Click **+ New** > **Folder** to create an organized structure. Create the following folders:

   | Folder Name | Purpose |
   |-------------|---------|
   | `Templates` | Contract templates and standard forms |
   | `Case Files` | Active case documents and summaries |
   | `Data` | Client rosters, case tracking, and billing data |

   ![](./media/ex5-create-folders.png)

1. Open a new browser tab and navigate to the GitHub repository containing the law firm documents:

   ```
   https://github.com/CloudLabsAI-Azure/m365/tree/main/unlock-ai-powered-future-work-with-microsoft-365-copilot%2Bagents/Labfiles/ex5-dataset
   ```

   ![](./media/ex5-github-lawfirm.png)

1. Download all 7 documents (click on each file, then click the **Download raw file** button):

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

   ![](./media/ex5-download-files.png)

   >**Tip:** Save all files to your **Downloads** folder for easy access.

1. Return to your SharePoint site. Navigate to the **Templates** folder.

1. Click **Upload** > **Files** and upload:
   - `01-Client-Contract-Template.docx.md`
   - `03-Legal-Fee-Schedule-2024.docx.md`
   - `04-Firm-Policies-Handbook.docx.md`

   ![](./media/ex5-upload-templates.png)

1. Navigate to the **Case Files** folder and upload:
   - `02-Case-Summary-Johnson-v-Apex.docx.md`

   ![](./media/ex5-upload-casefiles.png)

1. Navigate to the **Data** folder and upload:
   - `05-client-roster.csv`
   - `06-case-tracking.csv`
   - `07-billing-summary-2024.csv`

   ![](./media/ex5-upload-data.png)

1. Verify all 7 documents are uploaded across the three folders.

   ![](./media/ex5-all-uploaded.png)

1. Click on one of the CSV files to preview and verify the data is accessible.

   ![](./media/ex5-preview-csv.png)

### Task 3: Create a SharePoint Agent from the Site

In this task, you will create a SharePoint Agent directly from within the SharePoint site. This agent will help legal staff discover documents and extract insights from both Word documents and CSV data.

1. In your SharePoint site, ensure you are on the site home page by clicking on **Home** in the left navigation.

   ![](./media/ex5-site-home.png)

1. Look for the **Copilot** icon in the top command bar or right side panel.

   ![](./media/ex5-copilot-icon.png)

1. Click on the **Copilot** icon to open the Copilot panel within SharePoint.

   ![](./media/ex5-copilot-panel.png)

1. In the Copilot panel, click on **Create an agent** or look for the **Agents** tab.

   ![](./media/ex5-create-agent-button.png)

   >**Note:** The SharePoint Copilot panel allows you to create agents that are scoped to the current site's content.

1. In the agent creation interface, configure the following:

   | Field | Value |
   |-------|-------|
   | Agent name | `Legal Document Assistant` |
   | Description | `Helps legal staff find case documents, client information, billing data, and provides insights from firm records.` |

   ![](./media/ex5-agent-name.png)

1. For the agent icon, select a legal or document-related icon, or let Copilot generate one.

   ![](./media/ex5-agent-icon.png)

1. Click **Next** to proceed to instructions configuration.

### Task 4: Configure the Agent for Document Discovery and Insights

In this task, you will configure the agent with instructions focused on legal document discovery and data analysis.

1. In the **Instructions** section, enter the following to define the agent's behavior:

   **Agent Instructions:**
   ```
   You are a Legal Document Assistant for Morrison & Associates Law Firm. Your role is to help legal staff find documents, extract information, and provide insights from firm records.

   1. DOCUMENT DISCOVERY
   - Help users locate specific documents (contracts, case files, policies)
   - Identify which folder contains the requested document
   - Provide document names and their locations

   2. CASE INFORMATION
   - Provide details about active cases from case summaries
   - Look up case status, deadlines, and assigned attorneys
   - Extract key dates and milestones from case documents

   3. CLIENT DATA
   - Find client contact information from the client roster
   - Look up client engagement dates and assigned attorneys
   - Provide billing status and outstanding balances

   4. BILLING & FINANCIAL INSIGHTS
   - Analyze billing data by attorney or time period
   - Calculate totals and identify trends
   - Provide fee schedule information for different services

   5. FIRM POLICIES
   - Answer questions about firm policies and procedures
   - Explain billable hour requirements and compensation
   - Provide information about office locations and contacts

   Available Documents:
   TEMPLATES FOLDER:
   - Client Contract Template: Standard engagement agreement
   - Legal Fee Schedule 2024: Hourly rates, flat fees, retainers
   - Firm Policies Handbook: Employee policies, procedures, contacts

   CASE FILES FOLDER:
   - Johnson v. Apex Manufacturing: Employment discrimination case summary

   DATA FOLDER:
   - Client Roster (CSV): 12 clients with contact info, attorneys, billing
   - Case Tracking (CSV): 10 active cases with status and deadlines
   - Billing Summary 2024 (CSV): Monthly billing by attorney (Jan-Apr)

   Response Guidelines:
   - Always cite the document and folder where information was found
   - For CSV data, provide specific values and calculations when asked
   - Summarize key points before providing details
   - For confidential matters, remind users about attorney-client privilege
   - Direct complex legal questions to the appropriate attorney
   ```

   ![](./media/ex5-agent-instructions.png)

1. Click **Next** to proceed to knowledge source configuration.

1. In the **Knowledge** section, verify that the **Morrison Law Firm** site is listed as a knowledge source.

   ![](./media/ex5-knowledge-auto.png)

1. Ensure all three folders (Templates, Case Files, Data) are included in the scope.

   ![](./media/ex5-folder-scope.png)

1. Click **Create** to finalize the SharePoint Agent.

   ![](./media/ex5-create-final.png)

1. Wait for the agent to be created and indexed. This may take a few moments.

   ![](./media/ex5-agent-created.png)

### Task 5: Test the Agent for Document Search and Data Analysis

In this task, you will test the SharePoint Agent's ability to find documents, locate specific information, and provide insights from the law firm data.

1. Once the agent is created, you will see the chat interface within SharePoint. Start with a document location question:

   **Prompt:**
   ```
   Where can I find the client contract template?
   ```

   ![](./media/ex5-test-location.png)

   **Expected Output:**

   The agent should identify that the **Client Contract Template** is located in the **Templates** folder and provide a brief description of its contents.

   ![](./media/ex5-location-response.png)

1. Test case information lookup:

   **Prompt:**
   ```
   What is the status of the Johnson v. Apex case? Who is the lead attorney and what are the next steps?
   ```

   ![](./media/ex5-test-case.png)

   **Expected Output:**

   The agent should provide details from the case summary including:
   - Case status: Discovery Phase
   - Lead Attorney: Sarah Morrison
   - Next deadline: Deposition scheduled
   - Estimated damages: $1,180,000+

   ![](./media/ex5-case-response.png)

1. Test client data lookup:

   **Prompt:**
   ```
   Look up the client TechStart Solutions. Who is their attorney and what is their outstanding balance?
   ```

   ![](./media/ex5-test-client.png)

   **Expected Output:**

   The agent should find information from the **client-roster.csv**:
   - Client: TechStart Solutions LLC
   - Lead Attorney: David Chen
   - Total Billed: $67,200
   - Outstanding Balance: $12,000

   ![](./media/ex5-client-response.png)

1. Test billing data analysis:

   **Prompt:**
   ```
   How many billable hours did Sarah Morrison have in March 2024? What was her total billed amount?
   ```

   ![](./media/ex5-test-billing.png)

   **Expected Output:**

   The agent should extract from **billing-summary-2024.csv**:
   - Billable Hours: 182
   - Billed Amount: $81,900
   - Collections: $73,700

   ![](./media/ex5-billing-response.png)

1. Test fee schedule lookup:

   **Prompt:**
   ```
   What is the hourly rate for a Senior Associate? What about flat fees for an LLC formation?
   ```

   ![](./media/ex5-test-fees.png)

   **Expected Output:**

   The agent should provide from the **Fee Schedule**:
   - Senior Associate hourly rate: $375
   - LLC Formation flat fee: $800

   ![](./media/ex5-fees-response.png)

1. Test case deadline lookup:

   **Prompt:**
   ```
   What cases have deadlines coming up in June 2024? List them with their deadline descriptions.
   ```

   ![](./media/ex5-test-deadlines.png)

   **Expected Output:**

   The agent should identify from **case-tracking.csv**:
   - Johnson v. Apex: June 12 - Deposition - Robert Lee
   - Metro Construction v. Supplier: June 5 - Discovery Responses Due
   - Sunrise Healthcare Restructuring: June 15 - Restructuring Plan Review

   ![](./media/ex5-deadlines-response.png)

1. Test firm policy questions:

   **Prompt:**
   ```
   What are the billable hour requirements for Associates? What about the bonus threshold?
   ```

   ![](./media/ex5-test-policy.png)

   **Expected Output:**

   The agent should find in the **Firm Policies Handbook**:
   - Associate annual target: 1,800 hours
   - Bonus threshold: 2,000 hours

   ![](./media/ex5-policy-response.png)

1. Test multi-source query:

   **Prompt:**
   ```
   Give me a summary of all clients with outstanding balances over $10,000. Include the client name, attorney, and amount owed.
   ```

   ![](./media/ex5-test-multi.png)

   **Expected Output:**

   The agent should analyze the **client-roster.csv** and identify:
   - TechStart Solutions LLC - David Chen - $12,000
   - Metro Construction Co - David Chen - $15,000
   - Wilson Estate - Patricia Williams - $18,200
   - Sunrise Healthcare LLC - Sarah Morrison - $22,000

   ![](./media/ex5-multi-response.png)

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
