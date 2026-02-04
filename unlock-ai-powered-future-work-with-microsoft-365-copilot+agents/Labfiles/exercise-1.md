# Exercise 1: Enhance Data Storytelling Using Microsoft 365 Copilot Analyst Agent

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will explore the Analyst Agent in Microsoft 365 Copilot. The Analyst Agent is a pre-built agent designed to help users analyze data, generate insights, and create compelling data visualizations. It can work with Excel and CSV data, help identify trends, and produce professional-quality reports.

You will use the Analyst Agent to analyze a real sales dataset containing order information, product lines, customer data, and regional performance across 2003-2005. The dataset includes:

- **Territories:** NA (North America), EMEA (Europe, Middle East, Africa), APAC (Asia Pacific), Japan
- **Product Lines:** Classic Cars, Motorcycles, Trucks and Buses, and more
- **Deal Sizes:** Small, Medium, Large
- **Customer Information:** Company names, contacts, and locations
- **Order Details:** Order numbers, quantities, prices, sales amounts, and dates

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

   >**Note:** This CSV file contains 376 rows of real sales data with columns including ORDERNUMBER, QUANTITYORDERED, PRICEEACH, SALES, ORDERDATE, STATUS, YEAR_ID (2003-2005), PRODUCTLINE, CUSTOMERNAME, TERRITORY, COUNTRY, and DEALSIZE.

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

   The Analyst Agent will reason through the data and provide a comprehensive analysis including:

   - **Territory Sales Table:** EMEA leads with approximately $845K, followed by NA with ~$760K, while APAC and Japan contribute ~$120K each
   - **Top Product Line:** Classic Cars is the clear leader with over $1.16M in sales (more than 2x Motorcycles)
   - **Year-over-Year Trends:** Growth of +17% from 2003 to 2004, followed by a decline in 2005 (likely due to partial year data)
   - **Deal Size Patterns:** Medium deals dominate both volume (230 orders) and revenue, with Large deals showing higher average order values

   ![](./media/ex1-analyze-response.png)

   >**Note:** The Analyst Agent performs real-time data analysis and may display "Reasoning" or "Coding and executing" status while processing your request.

1. Ask for deeper insights:

   **Prompt:**
   ```
   Which territory and product line combination has the highest sales performance? Also identify the top 5 customers by total sales amount.
   ```

   ![](./media/ex1-insights-prompt.png)

   **Expected Output:**

   The Analyst Agent will identify:

   - **Highest Performing Combination:** EMEA x Classic Cars with approximately $588K (the strongest territory/product-line pair)
   - **Top 5 Customers by Total Sales:**
     1. Mini Gifts Distributors Ltd. - ~$116K
     2. Euro Shopping Channel - ~$93K
     3. Dragon Souveniers, Ltd. - ~$62K
     4. Corporate Gift Ideas Co. - ~$52K
     5. Land of Toys Inc. - ~$46K

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

   The Analyst Agent will identify trends such as:

   - **Trend 1:** Significant growth from 2003 to 2004 (+17%), followed by a sharp decline in 2005 - possibly due to partial year data or market changes
   - **Trend 2:** Strong and consistent outperformance by Classic Cars across all years - driven by premium product positioning and distributor affinity
   - **Trend 3:** Territory imbalance with EMEA and NA dominating while APAC and Japan show "high-value but low-volume" profiles

   ![](./media/ex1-trends-response.png)

1. Ask for predictive insights:

   **Prompt:**
   ```
   Based on the sales trends across 2003-2005, which territories and product lines should the company focus on for growth? Which customer segments show the most potential?
   ```

   ![](./media/ex1-predict-prompt.png)

   **Expected Output:**

   The Analyst Agent will provide strategic recommendations including:

   - **Priority Territories:** EMEA (highest revenue, strong Classic Cars performance) and NA (solid customer base)
   - **Growth Opportunities:** Japan and APAC show highest average order values - potential for premium/collector offerings
   - **Product Focus:** Continue investing in Classic Cars while expanding Motorcycles as a secondary growth driver
   - **Customer Segments:** Major wholesalers (Mini Gifts, Euro Shopping Channel) and premium collectors in Japan/APAC

   ![](./media/ex1-predict-response.png)

1. Request comparative analysis:

   **Prompt:**
   ```
   Compare the performance of Classic Cars vs Motorcycles product lines across all territories. Which product line is more consistent and which has more variability in deal sizes?
   ```

   ![](./media/ex1-compare-prompt.png)

   **Expected Output:**

   The Analyst Agent will provide a detailed comparison:

   - **Classic Cars:** Higher total revenue (~$1.16M), heavier reliance on Large deals, slightly higher variability in per-order values
   - **Motorcycles:** More balanced across territories, concentrated in Medium deals, more predictable and consistent
   - **Verdict:** Motorcycles is more consistent (lower variability), while Classic Cars has more variability but higher revenue potential

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

   The Analyst Agent will recommend charts such as:

   - **YoY Sales Column Chart:** Shows 2003, 2004, 2005 totals to highlight the +17% growth and 2005 decline
   - **Territory Contribution Stacked Bar:** 100% bars showing NA, EMEA, APAC, Japan mix by year
   - **Territory x Product Line Heatmap:** Matrix with color intensity for sales, highlighting EMEA x Classic Cars as the strongest cell
   - **Product Line Ranked Bars:** Horizontal bars showing Classic Cars > Motorcycles > Trucks & Buses
   - **Top Customers Pareto Chart:** Bars with cumulative % line showing customer concentration
   - **Deal Size Boxplots:** Distribution of order values by deal size and product line

   ![](./media/ex1-viz-response.png)

1. Ask for a specific visualization description:

   **Prompt:**
   ```
   Describe a dashboard layout that would effectively present this sales data to senior leadership. Include 4-5 key visualizations covering territory performance, product line analysis, customer distribution, and deal size patterns.
   ```

   ![](./media/ex1-dashboard-prompt.png)

   **Expected Output:**

   The Analyst Agent will describe an executive dashboard layout including:

   - **Top Section:** KPI strip with Total Sales, YoY %, Top Territory, Top Product Line
   - **Tile 1:** YoY Sales Trend (Clustered Columns for 2003-2005)
   - **Tile 2:** Territory x Product Line Heatmap (EMEA x Classic Cars highlighted)
   - **Tile 3:** Top Customers Pareto Chart (showing concentration risk)
   - **Tile 4:** Deal Size Mix by Product Line (100% stacked bars)
   - **Tile 5:** Per-Order Sales Distribution Boxplots

   ![](./media/ex1-dashboard-response.png)

1. Request data formatting for export:

   **Prompt:**
   ```
   Format the territory sales summary as a table that I can copy into a PowerPoint presentation, with clear headers showing territory, total sales, number of orders, and average deal size.
   ```

   ![](./media/ex1-table-prompt.png)

   **Expected Output:**

   The Analyst Agent will generate a clean, copy-ready table:

   | Territory | Total Sales ($) | Number of Orders | Average Deal Size ($) |
   |-----------|-----------------|------------------|----------------------|
   | EMEA      | 845,849.18      | 176              | 4,805.96             |
   | NA        | 759,793.05      | 150              | 5,065.29             |
   | APAC      | 123,612.55      | 27               | 4,578.24             |
   | Japan     | 117,941.25      | 21               | 5,616.25             |

   >**Note:** Some records may have blank territory values. The Analyst can map these using country data if requested.

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

   The Analyst Agent will generate a professional executive summary covering:

   - **Performance Overview:** Strong momentum from 2003-2004 with 17% growth, total sales exceeding $1.8M across the period
   - **Regional Achievements:** EMEA as the top-performing territory, NA providing steady volume, Japan/APAC showing premium potential
   - **Product Line Success:** Classic Cars as the flagship driver with $1.16M, Motorcycles as a stable secondary line
   - **Recommended Actions:** Focus on EMEA growth, deepen key account relationships, explore premium offerings in Japan/APAC, strengthen discount governance

   ![](./media/ex1-summary-response.png)

1. Ask for presentation talking points:

   **Prompt:**
   ```
   Create 5 key talking points for presenting this sales data to the board of directors. Each point should include the data insight from territories, product lines, or customer segments and its business implication.
   ```

   ![](./media/ex1-talking-points-prompt.png)

   **Expected Output:**

   The Analyst Agent will create 5 board-ready talking points such as:

   1. **EMEA Leadership:** Strongest territory with $845K - prioritize inventory and partnerships
   2. **Classic Cars Dominance:** Flagship product driving 2x revenue vs Motorcycles - continue investment
   3. **2005 Decline Investigation:** Sharp drop requires analysis - partial data or market change?
   4. **Customer Concentration Risk:** Top 5 customers drive significant share - diversify mid-tier accounts
   5. **Deal Size Variability:** Classic Cars has higher Large-deal dependence - adjust forecasting

   ![](./media/ex1-talking-points-response.png)

1. Request a data story:

   **Prompt:**
   ```
   Tell the story of our sales performance across 2003-2005 in a narrative format that would engage a non-technical audience. Highlight the growth in different territories, successful product lines, and key customer relationships.
   ```

   ![](./media/ex1-story-prompt.png)

   **Expected Output:**

   The Analyst Agent will craft an engaging narrative telling the story of:

   - The journey from 2003 foundation to 2004 growth peak
   - How EMEA became the powerhouse market
   - The Classic Cars success story and customer partnerships
   - Key relationships with Mini Gifts Distributors, Euro Shopping Channel, and other top accounts
   - Opportunities in premium markets like Japan and APAC

   ![](./media/ex1-story-response.png)

## Summary

In this exercise, you explored the Analyst Agent in Microsoft 365 Copilot. You learned how to:

- Access and activate the Analyst Agent
- Upload and analyze real sales data from a CSV file (376 orders across 2003-2005)
- Generate insights on territories (EMEA, NA, APAC, Japan), product lines (Classic Cars, Motorcycles), and customers
- Request data visualization recommendations for executive dashboards
- Build compelling data-driven narratives and board-ready talking points

The Analyst Agent is a powerful tool for transforming raw data into actionable insights and professional presentations, with real-time data analysis capabilities.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
