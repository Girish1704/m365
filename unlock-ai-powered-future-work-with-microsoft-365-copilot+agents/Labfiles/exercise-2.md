# Exercise 2: Use the Researcher Agent to Surface Insights and Produce Professional Outputs

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will explore the Researcher Agent in Microsoft 365 Copilot. The Researcher Agent is designed to help users gather information, organize content, and produce professional-quality outputs. It can research topics, synthesize information from multiple sources, and create structured documents.

You will use the Researcher Agent to research a business topic, organize findings, and produce a professional report.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access the Researcher Agent
- Task 2: Research a business topic
- Task 3: Organize and synthesize information
- Task 4: Create structured content
- Task 5: Produce a professional report

### Task 1: Access the Researcher Agent

In this task, you will navigate to Microsoft 365 Copilot and access the Researcher Agent.

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

   ![](./media/ex2-copilot-icon.png)

1. In the Copilot interface, click on the **Agents** button on the right side panel.

   ![](./media/ex2-agents-button.png)

1. In the agents panel, browse or search for the **Researcher** agent.

   ![](./media/ex2-researcher-agent.png)

1. Click on the **Researcher** agent to open it. You will see the Researcher interface with a prompt box asking **"What do you want to research today?"**

   ![](./media/ex2-researcher-interface.png)

1. Notice the quick action cards available on the Researcher home page:

   | Quick Action | Description |
   |--------------|-------------|
   | **Project update** | Executive status report on a project |
   | **Topic report** | Get updates on any topic |
   | **Customer brief** | Prepare for a meeting with a customer |
   | **Market analysis** | Analyze the market position of a company |
   | **Meeting prep** | Prepare for upcoming meetings |
   | **Daily briefing** | Show today's updates, tasks, and meetings |

   ![](./media/ex2-quick-actions.png)

1. Also notice the input options:
   - **+** button to add attachments
   - **Computer use** option for advanced scenarios
   - **Sources** to specify research sources
   - **Microphone** icon for voice input

   >**Note:** The Researcher agent can access web sources, your Microsoft 365 data (emails, files, calendar), and any sources you explicitly add.

### Task 2: Research a Business Topic

In this task, you will use the Researcher Agent to research a business topic.

1. You can either click on one of the quick action cards or type directly in the prompt box. Let's start with a custom research topic. In the **"What do you want to research today?"** box, type:

   **Prompt:**
   ```
   I need to research the topic of "AI adoption in enterprise organizations". Please provide:
   1. An overview of current AI adoption trends
   2. Key benefits organizations are seeing
   3. Common challenges and barriers
   4. Best practices for successful implementation
   ```

   ![](./media/ex2-research-prompt.png)

   **Expected Output:**

   The Researcher Agent will search for information and provide a comprehensive report including:

   - **Current Trends:** Growth statistics, adoption rates, and emerging patterns
   - **Key Benefits:** Productivity gains, cost savings, improved decision-making
   - **Challenges:** Data quality, talent gaps, change management, ethical concerns
   - **Best Practices:** Start small, focus on data quality, build cross-functional teams

   ![](./media/ex2-research-response.png)

   >**Note:** The Researcher may display "Searching" or "Gathering information" status while compiling the research.

1. Dig deeper into specific areas:

   **Prompt:**
   ```
   Expand on the implementation challenges. What are the top 5 reasons AI projects fail in enterprises, and what can organizations do to avoid these pitfalls?
   ```

   ![](./media/ex2-challenges-prompt.png)

   **Expected Output:**

   The Researcher will provide detailed analysis of common failure points such as:

   - **Unclear business objectives** - Starting with technology instead of business problems
   - **Poor data quality** - Insufficient or unreliable data for training models
   - **Lack of executive sponsorship** - Missing leadership commitment and resources
   - **Talent gaps** - Shortage of skilled AI/ML professionals
   - **Change resistance** - Organizational culture not ready for AI-driven processes

   ![](./media/ex2-challenges-response.png)

1. Now try using one of the quick action cards. Click on **Market analysis** and enter a company name like **Microsoft** to see how the Researcher analyzes market positioning.

   ![](./media/ex2-market-analysis.png)

   **Expected Output:**

   The Researcher will provide market analysis covering competitive landscape, market share, strategic positioning, and recent developments.

   ![](./media/ex2-market-response.png)

1. Request industry-specific insights:

   **Prompt:**
   ```
   How does AI adoption differ across industries? Compare AI adoption patterns in financial services, healthcare, and manufacturing sectors.
   ```

   ![](./media/ex2-industry-prompt.png)

   **Expected Output:**

   ![](./media/ex2-industry-response.png)

### Task 3: Organize and Synthesize Information

In this task, you will have the Researcher Agent organize and synthesize the gathered information.

1. Request a structured outline:

   **Prompt:**
   ```
   Based on the research we have gathered, create a detailed outline for a whitepaper titled "Enterprise AI Adoption: A Strategic Guide for Business Leaders". Include main sections and subsections.
   ```

   ![](./media/ex2-outline-prompt.png)

   **Expected Output:**

   ![](./media/ex2-outline-response.png)

   The Researcher Agent creates a comprehensive outline.

1. Ask for key takeaways:

   **Prompt:**
   ```
   Synthesize all the information we have discussed into 10 key takeaways that a C-level executive should know about AI adoption.
   ```

   ![](./media/ex2-takeaways-prompt.png)

   **Expected Output:**

   ![](./media/ex2-takeaways-response.png)

1. Request a comparison framework:

   **Prompt:**
   ```
   Create a comparison table that organizations can use to evaluate their AI readiness. Include categories like data infrastructure, talent, culture, and governance, with maturity levels from beginner to advanced.
   ```

   ![](./media/ex2-framework-prompt.png)

   **Expected Output:**

   ![](./media/ex2-framework-response.png)

### Task 4: Create Structured Content

In this task, you will use the Researcher Agent to create different types of structured content.

1. Create an infographic description:

   **Prompt:**
   ```
   Describe an infographic that visualizes the AI adoption journey for enterprises. Include 5-6 stages with key activities and milestones for each stage.
   ```

   ![](./media/ex2-infographic-prompt.png)

   **Expected Output:**

   ![](./media/ex2-infographic-response.png)

1. Create a checklist:

   **Prompt:**
   ```
   Create a comprehensive AI readiness checklist that organizations can use before starting their AI journey. Organize it by category with specific actionable items.
   ```

   ![](./media/ex2-checklist-prompt.png)

   **Expected Output:**

   ![](./media/ex2-checklist-response.png)

1. Create FAQ content:

   **Prompt:**
   ```
   Generate a FAQ section with 8-10 common questions that business leaders ask about AI adoption, along with clear and concise answers.
   ```

   ![](./media/ex2-faq-prompt.png)

   **Expected Output:**

   ![](./media/ex2-faq-response.png)

### Task 5: Produce a Professional Report

In this task, you will have the Researcher Agent produce a professional report.

1. Request an executive summary:

   **Prompt:**
   ```
   Write a professional executive summary (400-500 words) for the AI adoption whitepaper. It should capture the key findings, recommendations, and call to action for business leaders.
   ```

   ![](./media/ex2-execsummary-prompt.png)

   **Expected Output:**

   ![](./media/ex2-execsummary-response.png)

   The Researcher Agent creates a polished executive summary.

1. Create an introduction section:

   **Prompt:**
   ```
   Write the introduction section for the whitepaper. Set the context for why AI adoption is critical now, the opportunity it presents, and what readers will learn from this document.
   ```

   ![](./media/ex2-intro-prompt.png)

   **Expected Output:**

   ![](./media/ex2-intro-response.png)

1. Create a conclusion with recommendations:

   **Prompt:**
   ```
   Write the conclusion section with 5 specific recommendations for organizations looking to accelerate their AI adoption. Each recommendation should be actionable and prioritized.
   ```

   ![](./media/ex2-conclusion-prompt.png)

   **Expected Output:**

   ![](./media/ex2-conclusion-response.png)

1. Request the complete document structure:

   **Prompt:**
   ```
   Compile all the sections we have created into a complete document outline with the executive summary, introduction, main content sections, and conclusion. Show how they flow together.
   ```

   ![](./media/ex2-compile-prompt.png)

   **Expected Output:**

   ![](./media/ex2-compile-response.png)

## Summary

In this exercise, you explored the Researcher Agent in Microsoft 365 Copilot. You learned how to:

- Access and activate the Researcher Agent
- Research business topics comprehensively
- Organize and synthesize information effectively
- Create various types of structured content
- Produce professional reports and documents

The Researcher Agent is valuable for creating well-researched, professional-quality content quickly and efficiently.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
