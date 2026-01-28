# Exercise 4: Empower Your Sellers with Microsoft 365 Copilot

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will explore how Microsoft 365 Copilot can empower sales professionals to be more effective and efficient. Sales teams spend significant time on administrative tasks like drafting emails, preparing proposals, researching prospects, and updating CRM systems. Copilot can automate and enhance these activities, allowing sellers to focus more on building relationships and closing deals.

You will work through realistic sales scenarios using Copilot across Microsoft 365 applications including Outlook, Word, and Excel.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Research and prepare for a sales meeting
- Task 2: Draft personalized sales outreach emails
- Task 3: Create a sales proposal document
- Task 4: Analyze sales data and generate insights
- Task 5: Prepare meeting follow-up and action items

### Task 1: Research and Prepare for a Sales Meeting

In this task, you will use Copilot to research a prospect and prepare for an upcoming sales meeting.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to the Microsoft 365 portal:

   ```
   https://www.microsoft365.com
   ```

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. On the Microsoft 365 home page, click on the **Copilot** icon from the left navigation panel.

   ![](./media/ex4-copilot-icon.png)

1. Ensure the toggle in the left panel is set to **Work** mode.

   ![](./media/ex4-copilot-work-mode.png)

1. Type the following prompt to research a prospect company:

   **Prompt:**
   ```
   I have a sales meeting with Contoso Ltd next week. They are a mid-sized manufacturing company. Help me prepare by:
   1. Suggesting key questions to ask during the discovery meeting
   2. Identifying potential pain points for manufacturing companies
   3. Creating talking points for how our solutions could help
   ```

   ![](./media/ex4-research-prompt.png)

   **Expected Output:**

   ![](./media/ex4-research-response.png)

   Copilot provides a comprehensive meeting preparation guide with discovery questions and talking points.

1. Follow up with an objections prompt:

   **Prompt:**
   ```
   Based on typical manufacturing industry challenges, what objections might I face and how should I handle them?
   ```

   ![](./media/ex4-objections-prompt.png)

   **Expected Output:**

   ![](./media/ex4-objections.png)

   Copilot provides common sales objections with recommended responses.

1. Create a meeting preparation checklist:

   **Prompt:**
   ```
   Create a pre-meeting checklist I should complete before the Contoso meeting, including research tasks, materials to prepare, and logistics to confirm.
   ```

   ![](./media/ex4-prep-checklist-prompt.png)

   **Expected Output:**

   ![](./media/ex4-prep-checklist.png)

1. Generate an agenda for the meeting:

   **Prompt:**
   ```
   Draft a 30-minute discovery meeting agenda for my first meeting with Contoso Ltd. Include time allocations for introductions, discovery questions, solution overview, and next steps.
   ```

   ![](./media/ex4-meeting-agenda-prompt.png)

   **Expected Output:**

   ![](./media/ex4-meeting-agenda.png)

### Task 2: Draft Personalized Sales Outreach Emails

In this task, you will use Copilot in Outlook to create personalized sales emails.

1. Open a new browser tab and navigate to Outlook:

   ```
   https://outlook.office.com
   ```

   ![](./media/ex4-open-outlook.png)

1. Click **New mail** to compose a new email.

   ![](./media/ex4-new-email.png)

1. In the email compose window, click on the **Copilot** icon in the toolbar.

   ![](./media/ex4-outlook-copilot.png)

1. Select **Draft with Copilot** from the menu.

   ![](./media/ex4-draft-with-copilot.png)

1. Enter the following prompt to generate a cold outreach email:

   **Prompt:**
   ```
   Write a cold outreach email to a VP of Operations at a manufacturing company. Introduce our company's process automation solutions. Keep it concise (under 150 words), personalized, and include a clear call-to-action for a 15-minute discovery call.
   ```

   ![](./media/ex4-outreach-prompt.png)

   **Expected Output:**

   ![](./media/ex4-outreach-email.png)

1. Review the generated email. You have options to:
   - **Keep it** — Use the draft as-is
   - **Regenerate** — Get a different version
   - **Adjust** — Modify tone, length, or style

   ![](./media/ex4-email-options.png)

1. Try adjusting the tone by selecting **Adjust** and choosing a different tone:

   - Click **Adjust** or the settings icon
   - Select a different tone (e.g., more formal, more casual)
   - Review the updated version

   ![](./media/ex4-adjust-tone.png)

1. Create a follow-up email sequence. Return to Copilot Chat and type:

   ```
   Create a 3-email follow-up sequence for prospects who don't respond to the initial outreach:
   - Email 2: Sent 3 days later, shorter and adds value
   - Email 3: Sent 1 week later, creates urgency
   - Email 4: Breakup email sent 2 weeks later
   ```

   ![](./media/ex4-email-sequence.png)

### Task 3: Create a Sales Proposal Document

In this task, you will use Copilot in Word to create a professional sales proposal.

1. Open **Word** from the Microsoft 365 app launcher or navigate to `https://www.office.com/launch/word`.

   ![](./media/ex4-open-word.png)

1. Create a new blank document by clicking **+ New blank document**.

   ![](./media/ex4-new-document.png)

1. In the Word document, access Copilot by clicking the **Copilot** icon in the ribbon or pressing the Copilot shortcut.

   ![](./media/ex4-word-copilot.png)

1. Use Copilot to draft a proposal. Enter the following prompt:

   ```
   Create a professional sales proposal for Contoso Ltd for our process automation solution. Include:
   
   1. Executive Summary
   2. Understanding of Client Needs (manufacturing efficiency, cost reduction, quality improvement)
   3. Proposed Solution overview
   4. Implementation Timeline (12 weeks)
   5. Investment Summary (placeholder pricing)
   6. Why Choose Us section
   7. Next Steps
   
   Make it professional, customer-focused, and approximately 2-3 pages.
   ```

   ![](./media/ex4-proposal-prompt.png)

1. Review the generated proposal. Copilot will create a structured document.

   ![](./media/ex4-proposal-draft.png)

1. Use Copilot to enhance specific sections. Select the "Understanding of Client Needs" section and ask Copilot:

   ```
   Expand this section with specific manufacturing industry pain points and statistics about inefficiency costs.
   ```

   ![](./media/ex4-expand-section.png)

1. Add a competitive advantage section:

   ```
   Add a section titled "Our Differentiators" that highlights 4 key reasons why our solution is better than alternatives.
   ```

   ![](./media/ex4-differentiators.png)

1. Format the document professionally:

   ```
   Apply professional formatting to this proposal with appropriate headings, bullet points, and spacing suitable for a B2B sales document.
   ```

   ![](./media/ex4-format-proposal.png)

1. Save the document as `Contoso-Proposal-<inject key="DeploymentID" enableCopy="false"/>.docx`.

### Task 4: Analyze Sales Data and Generate Insights

In this task, you will use Copilot in Excel to analyze sales data and generate insights.

1. Open **Excel** from the Microsoft 365 app launcher or navigate to `https://www.office.com/launch/excel`.

   ![](./media/ex4-open-excel.png)

1. Create a new blank workbook.

   ![](./media/ex4-new-workbook.png)

1. First, let's create some sample sales data. In the Excel sheet, enter the following data starting from cell A1:

   | Region | Q1 Sales | Q2 Sales | Q3 Sales | Q4 Sales | Target |
   |--------|----------|----------|----------|----------|--------|
   | North | 125000 | 135000 | 142000 | 168000 | 150000 |
   | South | 98000 | 102000 | 115000 | 125000 | 120000 |
   | East | 145000 | 152000 | 148000 | 175000 | 160000 |
   | West | 112000 | 118000 | 125000 | 145000 | 140000 |
   | Central | 87000 | 92000 | 98000 | 110000 | 100000 |

   ![](./media/ex4-sales-data.png)

1. Select the data range and format it as a table by pressing **Ctrl+T** or clicking **Format as Table** in the Home ribbon.

   ![](./media/ex4-format-table.png)

1. Access Copilot in Excel by clicking the **Copilot** button in the ribbon.

   ![](./media/ex4-excel-copilot.png)

1. Ask Copilot to analyze the data:

   ```
   Analyze this sales data and provide insights on:
   1. Which region performed best overall?
   2. Which region showed the most growth?
   3. Which regions met or exceeded their targets?
   4. What trends do you see across quarters?
   ```

   ![](./media/ex4-analysis-prompt.png)

1. Review the insights provided by Copilot.

   ![](./media/ex4-analysis-results.png)

1. Ask Copilot to add calculated columns:

   ```
   Add columns for:
   1. Total Annual Sales
   2. Percentage vs Target
   3. Q4 vs Q1 Growth Rate
   ```

   ![](./media/ex4-add-columns.png)

1. Request a visualization:

   ```
   Create a chart showing quarterly sales performance by region.
   ```

   ![](./media/ex4-create-chart.png)

1. Generate a summary for leadership:

   ```
   Write an executive summary of the sales performance that I can share with my sales director, highlighting key wins and areas for improvement.
   ```

   ![](./media/ex4-exec-summary.png)

### Task 5: Prepare Meeting Follow-up and Action Items

In this task, you will use Copilot to create effective meeting follow-ups.

1. Return to Microsoft 365 Copilot Chat.

1. Imagine you've completed the meeting with Contoso. Use Copilot to create follow-up materials:

   ```
   I just completed a sales meeting with Contoso Ltd. During the meeting, we discussed:
   - Their current manual processes causing delays
   - Interest in our automation solution
   - Concerns about implementation timeline and training
   - Need to involve their IT team in the evaluation
   - Budget approval required from CFO
   
   Create a professional follow-up email that:
   1. Thanks them for their time
   2. Summarizes key discussion points
   3. Addresses their concerns
   4. Lists clear next steps with owners
   5. Proposes a follow-up meeting date
   ```

   ![](./media/ex4-followup-prompt.png)

1. Review and refine the follow-up email.

   ![](./media/ex4-followup-email.png)

1. Create internal action items:

   ```
   Based on the Contoso meeting, create a list of internal action items for our team to complete before the next meeting, including preparing technical documentation, pricing approval, and reference customer contacts.
   ```

   ![](./media/ex4-internal-actions.png)

1. Generate a CRM update summary:

   ```
   Write a concise CRM opportunity update note for the Contoso deal, including meeting summary, opportunity stage, next steps, and estimated close date.
   ```

   ![](./media/ex4-crm-update.png)

1. Create a deal strategy document:

   ```
   Create a brief account strategy document for Contoso Ltd that includes:
   - Account overview
   - Key stakeholders and their priorities
   - Competition we might face
   - Our value proposition
   - Win themes to emphasize
   - Potential risks and mitigation strategies
   ```

   ![](./media/ex4-account-strategy.png)

## Summary

In this exercise, you successfully demonstrated how Microsoft 365 Copilot empowers sales professionals by:

- Researching prospects and preparing for sales meetings
- Drafting personalized outreach emails and follow-up sequences in Outlook
- Creating professional sales proposals in Word
- Analyzing sales data and generating insights in Excel
- Preparing meeting follow-ups, action items, and account strategies

These capabilities help sales teams spend less time on administrative tasks and more time on high-value activities like building relationships and closing deals. Copilot serves as an AI-powered sales assistant that can significantly boost productivity and effectiveness.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
