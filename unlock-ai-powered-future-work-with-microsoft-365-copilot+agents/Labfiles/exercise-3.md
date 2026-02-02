# Exercise 3: Explore Document Analyzer Agent to Ask Questions, Analyze Content, and Transform Documents in Word

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will explore the Document Analyzer Agent in Microsoft 365 Copilot. The Document Analyzer Agent is designed to help users understand, analyze, and transform documents. It can answer questions about document content, extract key information, summarize lengthy documents, and help transform content into different formats.

You will use the Document Analyzer Agent to analyze a business document, extract insights, and transform the content for different purposes.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access the Document Analyzer Agent
- Task 2: Analyze document content
- Task 3: Ask questions about the document
- Task 4: Extract key information
- Task 5: Transform document content

### Task 1: Access the Document Analyzer Agent

In this task, you will navigate to Microsoft 365 and access the Document Analyzer Agent in Word.

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

   ![](./media/ex3-apps-panel.png)

1. Select **Word** from the list of apps to open Word Online.

   ![](./media/ex3-word-app.png)

1. Click **New blank document** to create a new document.

   ![](./media/ex3-new-document.png)

1. First, let us create a sample business document to analyze. Copy and paste the following content into the document:

   ```
   ANNUAL BUSINESS REVIEW 2024
   Contoso Corporation

   EXECUTIVE SUMMARY

   Contoso Corporation achieved significant milestones in fiscal year 2024, with total revenue reaching $4.2 billion, representing a 15% year-over-year increase. This growth was driven primarily by our cloud services division, which saw a 28% increase in subscription revenue.

   KEY FINANCIAL HIGHLIGHTS

   - Total Revenue: $4.2 billion (up 15% YoY)
   - Cloud Services Revenue: $1.8 billion (up 28% YoY)
   - Enterprise Solutions Revenue: $1.5 billion (up 8% YoY)
   - Consumer Products Revenue: $0.9 billion (up 5% YoY)
   - Operating Margin: 22% (up from 19% in 2023)
   - Net Income: $756 million (up 24% YoY)
   - Employee Count: 12,500 (up from 10,800)

   STRATEGIC INITIATIVES

   1. Cloud Transformation
   We successfully migrated 85% of enterprise customers to our cloud platform, exceeding our target of 75%. Customer satisfaction scores for cloud services improved to 4.6 out of 5.

   2. AI Integration
   Launched AI-powered features across all product lines. Early adoption rates exceeded expectations with 40% of customers actively using AI features within the first quarter of launch.

   3. Market Expansion
   Entered three new international markets: Japan, Brazil, and Germany. These markets contributed $180 million in revenue, with Japan being the strongest performer at $95 million.

   4. Sustainability Goals
   Achieved carbon neutrality in our data center operations. Reduced overall carbon footprint by 35% compared to 2022 baseline.

   CHALLENGES AND RISKS

   - Increased competition in the cloud services market from established players
   - Talent acquisition remains challenging in AI and machine learning roles
   - Supply chain constraints affected hardware product deliveries in Q2
   - Currency fluctuations impacted international revenue by approximately 3%

   OUTLOOK FOR 2025

   We project continued growth with revenue expected to reach $4.8-5.0 billion. Key focus areas include:
   - Expanding AI capabilities across all products
   - Achieving 95% cloud migration for enterprise customers
   - Launching in five additional international markets
   - Investing $500 million in R&D for next-generation technologies

   The board recommends a 10% increase in dividend payments to shareholders, reflecting our strong financial position and confidence in future growth.
   ```

   ![](./media/ex3-document-content.png)

1. Save the document by clicking **File** > **Save As** > **Save to OneDrive**. Name it:

   ```
   Contoso-Annual-Review-2024
   ```

   ![](./media/ex3-save-document.png)

1. With the document open, click on the **Copilot** icon in the toolbar to access Copilot in Word.

   ![](./media/ex3-copilot-word.png)

### Task 2: Analyze Document Content

In this task, you will use Copilot to analyze the document content.

1. In the Copilot pane, type the following prompt:

   **Prompt:**
   ```
   Analyze this document and provide:
   1. A brief overview of what this document is about
   2. The main sections covered
   3. The overall tone and purpose
   ```

   ![](./media/ex3-analyze-prompt.png)

   **Expected Output:**

   ![](./media/ex3-analyze-response.png)

   Copilot provides a comprehensive analysis of the document structure and content.

1. Request a deeper analysis:

   **Prompt:**
   ```
   What are the key performance indicators (KPIs) mentioned in this document? List them with their values and year-over-year changes.
   ```

   ![](./media/ex3-kpi-prompt.png)

   **Expected Output:**

   ![](./media/ex3-kpi-response.png)

1. Ask for sentiment analysis:

   **Prompt:**
   ```
   What is the overall sentiment of this report? Is it optimistic, cautious, or neutral? Provide evidence from the text to support your assessment.
   ```

   ![](./media/ex3-sentiment-prompt.png)

   **Expected Output:**

   ![](./media/ex3-sentiment-response.png)

### Task 3: Ask Questions About the Document

In this task, you will ask specific questions about the document content.

1. Ask about financial performance:

   **Prompt:**
   ```
   Which business division had the highest growth rate, and what contributed to this growth?
   ```

   ![](./media/ex3-growth-prompt.png)

   **Expected Output:**

   ![](./media/ex3-growth-response.png)

1. Ask about challenges:

   **Prompt:**
   ```
   What challenges did Contoso face in 2024, and how might these impact their 2025 goals?
   ```

   ![](./media/ex3-challenges-prompt.png)

   **Expected Output:**

   ![](./media/ex3-challenges-response.png)

1. Ask about strategic initiatives:

   **Prompt:**
   ```
   Did Contoso meet their strategic targets? Compare the targets mentioned with the actual achievements.
   ```

   ![](./media/ex3-targets-prompt.png)

   **Expected Output:**

   ![](./media/ex3-targets-response.png)

1. Ask a comparative question:

   **Prompt:**
   ```
   How does the revenue from new international markets compare to the overall revenue growth?
   ```

   ![](./media/ex3-compare-prompt.png)

   **Expected Output:**

   ![](./media/ex3-compare-response.png)

### Task 4: Extract Key Information

In this task, you will extract specific information from the document.

1. Extract financial data:

   **Prompt:**
   ```
   Create a table summarizing all financial figures mentioned in this document, including revenue, margins, and growth percentages.
   ```

   ![](./media/ex4-financials-prompt.png)

   **Expected Output:**

   ![](./media/ex3-financials-response.png)

   Copilot creates a structured table with all financial data.

1. Extract action items:

   **Prompt:**
   ```
   What are all the future plans and commitments mentioned in this document? List them as action items with specific targets.
   ```

   ![](./media/ex3-actions-prompt.png)

   **Expected Output:**

   ![](./media/ex3-actions-response.png)

1. Extract key dates and timelines:

   **Prompt:**
   ```
   List all time-related references in this document, including years, quarters, and future projections.
   ```

   ![](./media/ex3-timeline-prompt.png)

   **Expected Output:**

   ![](./media/ex3-timeline-response.png)

### Task 5: Transform Document Content

In this task, you will transform the document content into different formats.

1. Create a summary:

   **Prompt:**
   ```
   Create a 3-paragraph executive summary of this document that could be shared with investors.
   ```

   ![](./media/ex3-summary-prompt.png)

   **Expected Output:**

   ![](./media/ex3-summary-response.png)

1. Transform into bullet points:

   **Prompt:**
   ```
   Convert the key findings of this report into a bulleted list format suitable for a presentation slide. Maximum 10 bullets.
   ```

   ![](./media/ex3-bullets-prompt.png)

   **Expected Output:**

   ![](./media/ex3-bullets-response.png)

1. Create a different perspective:

   **Prompt:**
   ```
   Rewrite the challenges section from a risk management perspective, categorizing each challenge by risk level (high, medium, low) and suggesting mitigation strategies.
   ```

   ![](./media/ex3-risk-prompt.png)

   **Expected Output:**

   ![](./media/ex3-risk-response.png)

1. Create email content:

   **Prompt:**
   ```
   Draft a brief email to the board of directors highlighting the top 3 achievements and top 3 focus areas for 2025 based on this report.
   ```

   ![](./media/ex3-email-prompt.png)

   **Expected Output:**

   ![](./media/ex3-email-response.png)

1. To insert any of the generated content into your document, click **Insert** or **Copy** on the Copilot response.

   ![](./media/ex3-insert-content.png)

## Summary

In this exercise, you explored the Document Analyzer capabilities in Microsoft 365 Copilot for Word. You learned how to:

- Access Copilot in Word for document analysis
- Analyze document content and structure
- Ask specific questions about document content
- Extract key information into structured formats
- Transform document content for different purposes

The Document Analyzer capabilities help you quickly understand, analyze, and repurpose document content for various business needs.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
