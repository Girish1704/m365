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

In this task, you will upload a sales data file and have the Analyst Agent analyze it.

1. With the Analyst Agent active, you will see a chat interface ready for your prompts.

   ![](./media/ex1-analyst-chat.png)

1. A sales data file has been provided for you in the VM. Navigate to the following location to verify the file exists:

   ```
   C:\datasets\sales_data_sample.csv
   ```

   >**Note:** This CSV file contains real-world sales data including order numbers, quantities, prices, product lines, customer information, and regional data across multiple years.

   ![](./media/ex1-sales-data-file.png)

1. In the Copilot chat, click the **Attach file** or **Upload** icon to upload a file.

   ![](./media/ex1-attach-icon.png)

1. Navigate to `C:\datasets\` and select the **sales_data_sample.csv** file, then click **Open**.

   ![](./media/ex1-select-csv.png)

1. Once the file is attached, type the following prompt to analyze the data:

   **Prompt:**
   ```
   Analyze this sales data and provide:
   1. Total sales by territory (NA, EMEA, APAC, Japan)
   2. Top performing product line
   3. Year-over-year sales trends
   4. Any notable patterns or anomalies in deal sizes
   ```

   ![](./media/ex1-analyze-prompt.png)

   **Expected Output:**

   ![](./media/ex1-analyze-response.png)

   The Analyst Agent provides a detailed breakdown of the sales data including territory performance, product line analysis, and trends.

1. Ask for deeper insights:

   **Prompt:**
   ```
   Which territory and product line combination has the highest sales performance? Also identify the top 5 customers by total sales amount.
   ```

   ![](./media/ex1-insights-prompt.png)

   **Expected Output:**

   ![](./media/ex1-insights-response.png)

### Task 3: Generate Data Insights and Trends

In this task, you will use the Analyst Agent to identify trends and generate actionable insights.

1. Request trend analysis:

   **Prompt:**
   ```
   Identify the top 3 trends in this sales data across the years 2003-2005 and explain what business factors might be driving these trends.
   ```

   ![](./media/ex1-trends-prompt.png)

   **Expected Output:**

   ![](./media/ex1-trends-response.png)

   The Analyst Agent identifies key trends with business context.

1. Ask for predictive insights:

   **Prompt:**
   ```
   Based on the sales trends across 2003-2005, which territories and product lines should the company focus on for growth? Which customer segments show the most potential?
   ```

   ![](./media/ex1-predict-prompt.png)

   **Expected Output:**

   ![](./media/ex1-predict-response.png)

1. Request comparative analysis:

   **Prompt:**
   ```
   Compare the performance of Classic Cars vs Motorcycles product lines across all territories. Which product line is more consistent and which has more variability in deal sizes?
   ```

   ![](./media/ex1-compare-prompt.png)

   **Expected Output:**

   ![](./media/ex1-compare-response.png)

### Task 4: Create Data Visualizations

In this task, you will ask the Analyst Agent to suggest and describe data visualizations.

1. Request visualization recommendations:

   **Prompt:**
   ```
   What are the best types of charts to visualize this sales data for an executive presentation? Consider the territories, product lines, and time-based trends. Describe each chart and what insights it would highlight.
   ```

   ![](./media/ex1-viz-prompt.png)

   **Expected Output:**

   ![](./media/ex1-viz-response.png)

   The Analyst Agent recommends appropriate visualizations.

1. Ask for a specific visualization description:

   **Prompt:**
   ```
   Describe a dashboard layout that would effectively present this sales data to senior leadership. Include 4-5 key visualizations covering territory performance, product line analysis, customer distribution, and deal size patterns.
   ```

   ![](./media/ex1-dashboard-prompt.png)

   **Expected Output:**

   ![](./media/ex1-dashboard-response.png)

1. Request data formatting for export:

   **Prompt:**
   ```
   Format the territory sales summary as a table that I can copy into a PowerPoint presentation, with clear headers showing territory, total sales, number of orders, and average deal size.
   ```

   ![](./media/ex1-table-prompt.png)

   **Expected Output:**

   ![](./media/ex1-table-response.png)

### Task 5: Build a Data-Driven Narrative

In this task, you will use the Analyst Agent to create a compelling narrative around the data.

1. Request an executive summary:

   **Prompt:**
   ```
   Write an executive summary (3-4 paragraphs) of our sales performance based on this data from 2003-2005. Include key achievements across territories, top-performing product lines, and recommended actions for future growth.
   ```

   ![](./media/ex1-summary-prompt.png)

   **Expected Output:**

   ![](./media/ex1-summary-response.png)

   The Analyst Agent creates a professional executive summary.

1. Ask for presentation talking points:

   **Prompt:**
   ```
   Create 5 key talking points for presenting this sales data to the board of directors. Each point should include the data insight from territories, product lines, or customer segments and its business implication.
   ```

   ![](./media/ex1-talking-points-prompt.png)

   **Expected Output:**

   ![](./media/ex1-talking-points-response.png)

1. Request a data story:

   **Prompt:**
   ```
   Tell the story of our sales performance across 2003-2005 in a narrative format that would engage a non-technical audience. Highlight the growth in different territories, successful product lines, and key customer relationships.
   ```

   ![](./media/ex1-story-prompt.png)

   **Expected Output:**

   ![](./media/ex1-story-response.png)

## Summary

In this exercise, you explored the Analyst Agent in Microsoft 365 Copilot. You learned how to:

- Access and activate the Analyst Agent
- Upload and analyze real sales data from a CSV file
- Generate insights and identify trends across territories and product lines
- Create data visualization recommendations
- Build compelling data-driven narratives for executive presentations

The Analyst Agent is a powerful tool for transforming raw data into actionable insights and professional presentations.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
