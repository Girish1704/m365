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

   >**Important:** Ensure the document contains readable text content before attempting analysis. If Copilot indicates "no readable content" or "empty document," verify that:
   >- The document has actual text (not just images)
   >- The content was properly pasted or typed
   >- The file was saved successfully
   >
   >If you encounter issues, try refreshing the page or re-opening the document.

### Task 2: Analyze Document Content

In this task, you will use Copilot to analyze the document content.

>**Note:** Copilot in Word analyzes the document you have open. Make sure the Contoso-Annual-Review-2024 document is the active document before proceeding.

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

   Copilot will analyze the document and provide:
   - **Brief Overview:** Identifies this as a corporate annual business review covering fiscal year 2024 performance
   - **Main Sections:** Executive Summary, Key Financial Highlights, Strategic Initiatives, Challenges and Risks, Outlook for 2025
   - **Tone and Purpose:** Professional, optimistic yet balanced; designed for stakeholder communication

   ![](./media/ex3-analyze-response.png)

   >**Troubleshooting:** If Copilot responds that it cannot find content or the document appears empty:
   >- Check that you're in the correct document (Contoso-Annual-Review-2024)
   >- Scroll through the document to ensure all content is visible
   >- Try asking a more specific question like "What is the total revenue mentioned?"
   >- Save the document and refresh if needed

1. Request a deeper analysis:

   **Prompt:**
   ```
   What are the key performance indicators (KPIs) mentioned in this document? List them with their values and year-over-year changes.
   ```

   ![](./media/ex3-kpi-prompt.png)

   **Expected Output:**

   Copilot will extract and list KPIs such as:
   - Total Revenue: $4.2B (↑15% YoY)
   - Cloud Services Revenue: $1.8B (↑28% YoY)
   - Operating Margin: 22% (↑3 percentage points from 19%)
   - Net Income: $756M (↑24% YoY)
   - Employee Count: 12,500 (↑15.7% from 10,800)

   ![](./media/ex3-kpi-response.png)

   >**Tip:** If you want the data in a specific format, you can ask: "Can you format this as a table?" or "Can you show this as a comparison chart?"

1. Ask for sentiment analysis:

   **Prompt:**
   ```
   What is the overall sentiment of this report? Is it optimistic, cautious, or neutral? Provide evidence from the text to support your assessment.
   ```

   ![](./media/ex3-sentiment-prompt.png)

   **Expected Output:**

   Copilot will assess the overall sentiment as **Optimistic** with supporting evidence:
   - Positive language: "significant milestones," "exceeded our target," "exceeded expectations"
   - Strong financial performance: 15% revenue growth, 24% net income increase
   - Successful strategic initiatives: 85% cloud migration vs 75% target
   - Forward-looking confidence: Board recommending 10% dividend increase
   
   However, it will note balanced reporting with acknowledgment of challenges (competition, talent acquisition, supply chain).

   ![](./media/ex3-sentiment-response.png)

   >**Note:** If Copilot cannot assess sentiment, it means it couldn't access the document text. Verify the document is open and has content.

### Task 3: Ask Questions About the Document

In this task, you will ask specific questions about the document content.

>**Important:** The quality of answers depends on how specific your questions are. More focused questions typically yield better responses.

In this task, you will ask specific questions about the document content.

1. Ask about financial performance:

   **Prompt:**
   ```
   Which business division had the highest growth rate, and what contributed to this growth?
   ```

   ![](./media/ex3-growth-prompt.png)

   **Expected Output:**

   Copilot will identify:
   - **Highest Growth Division:** Cloud Services with 28% YoY growth
   - **Contributing Factors:**
     - Successful cloud migration initiative (85% of enterprise customers migrated)
     - High customer satisfaction (4.6/5) indicating strong retention
     - Market shift toward cloud-based solutions
     - AI integration making cloud offerings more competitive

   ![](./media/ex3-growth-response.png)

   >**Pro Tip:** If you want more detail, follow up with: "What about the other divisions? How did they perform?"

1. Ask about challenges:

   **Prompt:**
   ```
   What challenges did Contoso face in 2024, and how might these impact their 2025 goals?
   ```

   ![](./media/ex3-challenges-prompt.png)

   **Expected Output:**

   Copilot will analyze the challenges and their potential impact:

   **2024 Challenges:**
   1. **Increased cloud competition** - Could pressure margins and slow growth
   2. **AI/ML talent shortage** - May slow AI feature development
   3. **Supply chain constraints** - Affected Q2 hardware deliveries
   4. **Currency fluctuations** - 3% impact on international revenue

   **Impact on 2025 Goals:**
   - **Cloud migration goal (95%):** Competition may make this harder to achieve
   - **AI expansion:** Talent gaps could delay rollout of new AI capabilities
   - **International expansion (5 new markets):** Currency risks could affect revenue projections
   - **$4.8-5.0B revenue target:** Supply chain and competition risks could pressure this target

   ![](./media/ex3-challenges-response.png)

   >**Note:** Copilot makes logical connections between stated challenges and stated goals. The quality of this analysis depends on how explicitly these connections are stated in the source document.

1. Ask about strategic initiatives:

   **Prompt:**
   ```
   Did Contoso meet their strategic targets? Compare the targets mentioned with the actual achievements.
   ```

   ![](./media/ex3-targets-prompt.png)

   **Expected Output:**

   Copilot will compare targets with achievements:

   **Explicitly Met/Exceeded Targets:**
   - **Cloud Migration:** Target 75% → Achieved 85% ✅ **Exceeded**
   - **AI Adoption:** "Exceeded expectations" with 40% customer adoption in Q1 ✅
   
   **Achievements Reported (No Explicit Target Stated):**
   - Market Expansion: Entered 3 new markets, contributed $180M revenue
   - Sustainability: Achieved carbon neutrality, 35% footprint reduction
   - Customer Satisfaction: 4.6/5 for cloud services

   ![](./media/ex3-targets-response.png)

   >**Important:** Copilot can only confirm "met target" when both target and actual are explicitly stated in the document. For other items, it will note strong performance but cannot quantify as "met/missed" without baseline targets.

1. Ask a comparative question:

   **Prompt:**
   ```
   How does the revenue from new international markets compare to the overall revenue growth?
   ```

   ![](./media/ex3-compare-prompt.png)

   **Expected Output:**

   Copilot will perform calculations and comparisons:

   **Revenue from New International Markets:** $180M
   - Japan: $95M
   - Brazil + Germany: $85M (combined)

   **Overall Revenue Growth (YoY):**
   - 2024 Revenue: $4.2B (up 15%)
   - 2023 Revenue: ~$3.65B (calculated: $4.2B ÷ 1.15)
   - Dollar Growth: ~$550M

   **Comparison:**
   - New markets revenue ($180M) represents **32.7%** of total YoY growth (~$550M)
   - New markets are **4.3%** of total 2024 revenue ($180M / $4.2B)
   
   **Key Insight:** While new markets are a small portion of total revenue, they contributed nearly one-third of the company's growth.

   ![](./media/ex3-compare-response.png)

   >**Note:** Copilot can perform mathematical reasoning and calculations based on document data. If calculations seem incorrect, you can ask it to "show your work" or "verify the calculation."

### Task 4: Extract Key Information

In this task, you will extract specific information from the document.

1. Extract financial data:

   **Prompt:**
   ```
   Create a table summarizing all financial figures mentioned in this document, including revenue, margins, and growth percentages.
   ```

   ![](./media/ex4-financials-prompt.png)

   **Expected Output:**

   Copilot will create a comprehensive financial table:

   | **Metric** | **2024 Value** | **2023 Value** | **YoY Change** |
   |------------|----------------|----------------|----------------|
   | Total Revenue | $4.2B | $3.65B | +15% |
   | Cloud Services | $1.8B | $1.41B | +28% |
   | Enterprise Solutions | $1.5B | $1.39B | +8% |
   | Consumer Products | $0.9B | $0.86B | +5% |
   | Operating Margin | 22% | 19% | +3 pp |
   | Net Income | $756M | $610M | +24% |
   | Employees | 12,500 | 10,800 | +15.7% |

   ![](./media/ex3-financials-response.png)

   >**Tip:** If the table isn't formatted exactly as you need, you can refine with:
   >- "Can you add a column for dollar change (not just percentage)?"
   >- "Can you highlight which metrics exceeded 20% growth?"
   >- "Can you format this for Excel import?"

1. Extract action items:

   **Prompt:**
   ```
   What are all the future plans and commitments mentioned in this document? List them as action items with specific targets.
   ```

   ![](./media/ex3-actions-prompt.png)

   **Expected Output:**

   Copilot will extract future commitments as actionable items:

   **2025 Action Items:**
   1. ☐ Achieve revenue of $4.8-5.0B (16-19% growth target)
   2. ☐ Reach 95% cloud migration for enterprise customers (up from 85%)
   3. ☐ Launch in 5 additional international markets
   4. ☐ Invest $500M in R&D for next-generation technologies
   5. ☐ Expand AI capabilities across all products
   6. ☐ Implement 10% dividend increase to shareholders

   ![](./media/ex3-actions-response.png)

   >**Pro Tip:** You can ask Copilot to: "Organize these by priority" or "Add responsible parties and deadlines based on industry best practices"

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

   Copilot will generate an investor-focused executive summary covering:
   - **Paragraph 1:** Strong financial performance (15% revenue growth, $4.2B total, 24% net income increase)
   - **Paragraph 2:** Strategic success (85% cloud migration, successful AI integration, international expansion)
   - **Paragraph 3:** Forward outlook (confident 2025 projections, $500M R&D investment, 10% dividend increase)

   ![](./media/ex3-summary-response.png)

   >**Iteration Tip:** If the summary doesn't match your needs:
   >- "Make this more concise (2 paragraphs instead of 3)"
   >- "Add more specific financial figures"
   >- "Adjust the tone to be more conservative"
   >- "Focus more on risks and challenges"

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

   Copilot will reframe challenges as risks with mitigation strategies:

   **HIGH RISK:**
   - **Increased Cloud Competition**
     - *Impact:* Revenue growth and margin pressure
     - *Mitigation:* Accelerate AI differentiation, strengthen customer success programs, competitive pricing strategy

   **MEDIUM RISK:**
   - **AI/ML Talent Shortage**
     - *Impact:* Delayed product innovation
     - *Mitigation:* Strategic partnerships, acquisition targets, enhanced employee development programs
   
   - **Currency Fluctuations (3% impact)**
     - *Impact:* International revenue volatility
     - *Mitigation:* Currency hedging strategies, localized pricing models

   **LOW RISK:**
   - **Supply Chain Constraints (Q2 only)**
     - *Impact:* Limited hardware delivery delays
     - *Mitigation:* Diversify supplier base, increase inventory buffers

   ![](./media/ex3-risk-response.png)

   >**Note:** Risk categorization may vary based on Copilot's interpretation. You can refine by asking: "Can you justify why each risk is rated at that level?"

1. Create email content:

   **Prompt:**
   ```
   Draft a brief email to the board of directors highlighting the top 3 achievements and top 3 focus areas for 2025 based on this report.
   ```

   ![](./media/ex3-email-prompt.png)

   **Expected Output:**

   Copilot will draft a concise board email:

   ```
   Subject: FY2024 Results Summary and 2025 Strategic Focus

   Dear Board Members,

   I'm pleased to share Contoso's strong FY2024 performance:

   Top 3 Achievements:
   1. Revenue Growth: Achieved $4.2B (↑15% YoY) with exceptional cloud performance (↑28%)
   2. Strategic Execution: Exceeded cloud migration target (85% vs 75% goal) with 4.6/5 satisfaction
   3. Market Expansion: Successfully entered Japan, Brazil, and Germany, contributing $180M

   Top 3 Focus Areas for 2025:
   1. Revenue Target: $4.8-5.0B through AI expansion and cloud acceleration to 95% migration
   2. Innovation Investment: $500M R&D commitment for next-generation technologies
   3. Global Growth: Launch in 5 additional international markets

   Full annual review attached. We recommend a 10% dividend increase reflecting our strong position.

   Best regards,
   [Name]
   ```

   ![](./media/ex3-email-response.png)

   >**Customization Options:** You can refine the email by asking:
   >- "Make this more formal/casual"
   >- "Add a section about challenges"
   >- "Make it shorter (3 bullets each instead of full paragraphs)"
   >- "Change the tone to be more cautious about 2025 targets"

1. To insert any of the generated content into your document, click **Insert** or **Copy** on the Copilot response.

   >**Important:** When you click **Insert**, Copilot will add the content at your current cursor position in the document. Make sure your cursor is in the right location before inserting.

   ![](./media/ex3-insert-content.png)

## Summary

In this exercise, you explored the Document Analyzer capabilities in Microsoft 365 Copilot for Word. You learned how to:

- Access Copilot in Word for document analysis
- Analyze document content and structure
- Ask specific questions about document content
- Extract key information into structured formats
- Transform document content for different purposes
- Iterate and refine outputs to get exactly what you need

The Document Analyzer capabilities help you quickly understand, analyze, and repurpose document content for various business needs.

## Key Takeaways

**Document Requirements:**
- Copilot needs readable text content in the active document to perform analysis
- If you get "no content found" errors, verify the document is open and contains text
- Save your document before running complex analysis to avoid losing work

**Question Quality Matters:**
- More specific questions yield better, more focused answers
- Breaking complex questions into smaller parts often produces better results
- You can build on previous answers with follow-up questions

**Iterative Refinement:**
- First responses may not be exactly what you need - that's normal
- Use follow-up prompts to refine format, tone, length, or focus
- Asking "Can you format this as a table/list/email?" often improves usability

**Copilot's Capabilities:**
- Can perform calculations and comparisons based on document data
- Can make logical inferences connecting different parts of the document
- Can transform content into multiple formats (summaries, tables, emails, bullet points)
- Works best with explicitly stated information; struggles with implicit or missing data

**Common Follow-Up Prompts:**
- "Can you make this more concise?"
- "Can you format this as a table?"
- "Can you provide more specific evidence?"
- "Can you show your calculations?"
- "Can you adjust the tone to be more [formal/casual/optimistic/cautious]?"

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
