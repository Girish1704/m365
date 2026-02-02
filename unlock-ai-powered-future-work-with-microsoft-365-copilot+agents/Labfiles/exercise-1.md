# Exercise 1: Enhance Data Storytelling Using Microsoft 365 Copilot Analyst Agent

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will explore the Analyst Agent in Microsoft 365 Copilot. The Analyst Agent is a pre-built agent designed to help users analyze data, generate insights, and create compelling data visualizations. It can work with Excel data, help identify trends, and produce professional-quality reports.

You will use the Analyst Agent to analyze sales data, generate insights, and create data-driven narratives that can be shared with stakeholders.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access the Analyst Agent in Microsoft 365 Copilot
- Task 2: Upload and analyze sales data
- Task 3: Generate data insights and trends
- Task 4: Create data visualizations
- Task 5: Build a data-driven narrative

### Task 1: Access the Analyst Agent in Microsoft 365 Copilot

In this task, you will navigate to Microsoft 365 Copilot and access the Analyst Agent.

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

   ![](./media/ex1-copilot-icon.png)

1. In the Copilot interface, click on the **Agents** button on the right side panel.

   ![](./media/ex1-agents-button.png)

1. In the agents panel, browse or search for the **Analyst** agent.

   ![](./media/ex1-analyst-agent.png)

1. Click on the **Analyst** agent to view its details and capabilities:

   - Analyze data from Excel files
   - Generate insights and trends
   - Create charts and visualizations
   - Provide data-driven recommendations

   ![](./media/ex1-analyst-details.png)

1. Click **Start chat** or **Use this agent** to begin working with the Analyst Agent.

   ![](./media/ex1-start-analyst.png)

### Task 2: Upload and Analyze Sales Data

In this task, you will upload sales data and have the Analyst Agent analyze it.

1. With the Analyst Agent active, you will see a chat interface ready for your prompts.

   ![](./media/ex1-analyst-chat.png)

1. First, let us create sample sales data. Type the following prompt:

   **Prompt:**
   ```
   Create a sample sales dataset for a retail company with the following columns: Month, Region (North, South, East, West), Product Category (Electronics, Clothing, Home & Garden), Sales Amount, and Units Sold. Include data for the last 12 months.
   ```

   ![](./media/ex1-create-data-prompt.png)

   **Expected Output:**

   ![](./media/ex1-create-data-response.png)

   The Analyst Agent generates a comprehensive sales dataset.

1. Now ask the Analyst to analyze this data:

   **Prompt:**
   ```
   Analyze this sales data and provide:
   1. Total sales by region
   2. Top performing product category
   3. Month-over-month growth trends
   4. Any notable patterns or anomalies
   ```

   ![](./media/ex1-analyze-prompt.png)

   **Expected Output:**

   ![](./media/ex1-analyze-response.png)

   The Analyst Agent provides a detailed breakdown of the sales data.

1. Ask for deeper insights:

   **Prompt:**
   ```
   Which region and product category combination has the highest growth potential based on this data? Explain your reasoning.
   ```

   ![](./media/ex1-insights-prompt.png)

   **Expected Output:**

   ![](./media/ex1-insights-response.png)

### Task 3: Generate Data Insights and Trends

In this task, you will use the Analyst Agent to identify trends and generate actionable insights.

1. Request trend analysis:

   **Prompt:**
   ```
   Identify the top 3 trends in this sales data and explain what business factors might be driving these trends.
   ```

   ![](./media/ex1-trends-prompt.png)

   **Expected Output:**

   ![](./media/ex1-trends-response.png)

   The Analyst Agent identifies key trends with business context.

1. Ask for predictive insights:

   **Prompt:**
   ```
   Based on the current trends, what would you predict for next quarter's sales? Which regions and categories should we focus on?
   ```

   ![](./media/ex1-predict-prompt.png)

   **Expected Output:**

   ![](./media/ex1-predict-response.png)

1. Request comparative analysis:

   **Prompt:**
   ```
   Compare the performance of Electronics vs Clothing categories across all regions. Which category is more consistent and which has more variability?
   ```

   ![](./media/ex1-compare-prompt.png)

   **Expected Output:**

   ![](./media/ex1-compare-response.png)

### Task 4: Create Data Visualizations

In this task, you will ask the Analyst Agent to suggest and describe data visualizations.

1. Request visualization recommendations:

   **Prompt:**
   ```
   What are the best types of charts to visualize this sales data for an executive presentation? Describe each chart and what insights it would highlight.
   ```

   ![](./media/ex1-viz-prompt.png)

   **Expected Output:**

   ![](./media/ex1-viz-response.png)

   The Analyst Agent recommends appropriate visualizations.

1. Ask for a specific visualization description:

   **Prompt:**
   ```
   Describe a dashboard layout that would effectively present this sales data to senior leadership. Include 4-5 key visualizations and explain the story each tells.
   ```

   ![](./media/ex1-dashboard-prompt.png)

   **Expected Output:**

   ![](./media/ex1-dashboard-response.png)

1. Request data formatting for export:

   **Prompt:**
   ```
   Format the regional sales summary as a table that I can copy into a PowerPoint presentation, with clear headers and totals.
   ```

   ![](./media/ex1-table-prompt.png)

   **Expected Output:**

   ![](./media/ex1-table-response.png)

### Task 5: Build a Data-Driven Narrative

In this task, you will use the Analyst Agent to create a compelling narrative around the data.

1. Request an executive summary:

   **Prompt:**
   ```
   Write an executive summary (3-4 paragraphs) of our sales performance based on this data. Include key achievements, areas of concern, and recommended actions.
   ```

   ![](./media/ex1-summary-prompt.png)

   **Expected Output:**

   ![](./media/ex1-summary-response.png)

   The Analyst Agent creates a professional executive summary.

1. Ask for presentation talking points:

   **Prompt:**
   ```
   Create 5 key talking points for presenting this sales data to the board of directors. Each point should include the data insight and its business implication.
   ```

   ![](./media/ex1-talking-points-prompt.png)

   **Expected Output:**

   ![](./media/ex1-talking-points-response.png)

1. Request a data story:

   **Prompt:**
   ```
   Tell the story of our sales performance this year in a narrative format that would engage a non-technical audience. Start with where we were, what happened, and where we are now.
   ```

   ![](./media/ex1-story-prompt.png)

   **Expected Output:**

   ![](./media/ex1-story-response.png)

## Summary

In this exercise, you explored the Analyst Agent in Microsoft 365 Copilot. You learned how to:

- Access and activate the Analyst Agent
- Upload and analyze sales data
- Generate insights and identify trends
- Create data visualization recommendations
- Build compelling data-driven narratives

The Analyst Agent is a powerful tool for transforming raw data into actionable insights and professional presentations.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
