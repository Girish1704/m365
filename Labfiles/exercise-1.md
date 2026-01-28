# Exercise 1: Drive Event Planning with Microsoft 365 Copilot Chat

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will explore Microsoft 365 Copilot Chat to plan and organize a corporate event. You'll learn how to leverage Copilot's natural language understanding to generate event ideas, create agendas, draft communications, and manage event logistics—all through conversational interactions.

Microsoft 365 Copilot Chat combines the power of large language models (LLMs) with your organizational data through Microsoft Graph, enabling contextual and intelligent responses that understand your business context.

**Copilot Chat vs. Microsoft 365 Copilot:**

At the start of this lab, it's important to understand the distinction between:
- **Copilot Chat (Free, Web-Based)** → A publicly accessible AI-powered chat tool that allows users to upload documents, ask questions, and receive general guidance. It operates using publicly available information.
- **Microsoft 365 Copilot (Work, Enterprise-Level)** → An AI-powered assistant deeply integrated with Microsoft 365 tools (Word, PowerPoint, Outlook, Excel, and Teams). It can access internal files, emails, calendars, and chats to provide organization-specific insights based on a company's existing data.

>**Note:** Copilot may generate outputs that differ slightly from the screenshots provided—please proceed with the workflow as expected.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access Microsoft 365 Copilot Chat
- Task 2: Generate event planning ideas and themes
- Task 3: Create a detailed event agenda
- Task 4: Draft event invitation emails
- Task 5: Generate event logistics checklist

### Task 1: Access Microsoft 365 Copilot Chat

In this task, you will navigate to Microsoft 365 Copilot Chat and familiarize yourself with its interface.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to the Microsoft 365 portal:

   ```
   https://www.microsoft365.com
   ```

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex1-signin.png)

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. On the Microsoft 365 home page, click on the **Copilot** icon from the left navigation panel.

   ![](./media/ex1-copilot-icon.png)

1. You will be redirected to the Microsoft 365 Copilot Chat interface. Take a moment to explore the interface:

   - **Chat input area** — Where you type your prompts
   - **Conversation history** — Previous conversations are saved for reference
   - **New chat** — Start a fresh conversation
   - **Work/Web toggle** — Switch between work data and web search modes

   ![](./media/ex1-copilot-interface.png)

1. From the left panel, select **Chat (1)**, and ensure the toggle is set to **Work (2)** mode to access your organizational data and context.

   ![](./media/ex1-work-mode.png)

   >**Note:** Work mode allows Copilot to access your Microsoft 365 data including emails, documents, calendar, and more through Microsoft Graph.

### Task 2: Generate Event Planning Ideas and Themes

In this task, you will use Copilot Chat to brainstorm ideas for a corporate team-building event.

1. In the Copilot Chat input area, type the following prompt and press **Enter** or click **Send**:

   **Prompt:**
   ```
   I need to plan a corporate team-building event for 50 employees. The event should be held next month, promote collaboration, and be suitable for both in-office and remote participants. Can you suggest 5 creative event themes with brief descriptions?
   ```

   ![](./media/ex1-event-prompt.png)

   **Expected Output:**

   ![](./media/ex1-event-themes.png)

   Copilot will provide creative event themes tailored to your requirements, such as:
   - Hybrid Hackathon
   - Virtual Escape Room Challenge
   - Cross-Team Innovation Day
   - Wellness & Team Bonding Retreat
   - Cultural Exchange Fair

1. To get more details on a specific theme, follow up with a prompt like:

   **Prompt:**
   ```
   I like the hybrid hackathon idea. Can you expand on this theme and suggest specific activities that would work for both in-person and remote participants?
   ```

   ![](./media/ex1-hackathon-details.png)

1. Copilot maintains context from previous messages, allowing for natural conversational flow. Notice how it builds upon the previous response.

   >**Note:** Microsoft 365 Copilot uses your organizational context to provide relevant suggestions. If your organization has previous event data in SharePoint or emails, Copilot may reference those for personalized recommendations.

### Task 3: Create a Detailed Event Agenda

In this task, you will use Copilot to generate a comprehensive event agenda.

1. Continue the conversation by typing:

   **Prompt:**
   ```
   Create a detailed agenda for a 4-hour hybrid hackathon event. Include time slots, activities, breaks, and specify which activities are for in-person vs remote participants.
   ```

   ![](./media/ex1-agenda-prompt.png)

   **Expected Output:**

   ![](./media/ex1-agenda-response.png)

   Copilot creates a structured timeline with activities for both in-person and remote participants.

1. To modify the agenda, type:

   **Prompt:**
   ```
   This looks great! Can you add a 15-minute networking session at the beginning and include suggested tools for remote collaboration during the hackathon?
   ```

   ![](./media/ex1-agenda-modified-prompt.png)

   **Expected Output:**

   ![](./media/ex1-agenda-modified.png)

1. To export this agenda in a shareable format, type:

   **Prompt:**
   ```
   Format this agenda as a table that I can copy to a Word document or email.
   ```

   **Expected Output:**

   ![](./media/ex1-agenda-table.png)

   Copilot formats the agenda as a professional table.

### Task 4: Draft Event Invitation Emails

In this task, you will use Copilot to create professional event invitation emails.

1. Type the following prompt to generate an invitation email:

   **Prompt:**
   ```
   Draft a professional and engaging email invitation for the hybrid hackathon event. The email should:
   - Have an exciting subject line
   - Explain the event purpose and benefits
   - Include date, time, and participation options (in-person vs remote)
   - Have a clear call-to-action for RSVP
   - Be suitable for sending to all 50 employees
   ```

   ![](./media/ex1-email-prompt.png)

   **Expected Output:**

   ![](./media/ex1-email-response.png)

   Copilot creates a well-structured email invitation with all the requested elements.

1. Request a reminder version:

   **Prompt:**
   ```
   Create a shorter version of this email for a reminder to be sent one week before the event.
   ```

   ![](./media/ex1-email-reminder-prompt.png)

   **Expected Output:**

   ![](./media/ex1-email-reminder.png)

1. Create a version for leadership:

   **Prompt:**
   ```
   Create a version of this invitation specifically for senior leadership, emphasizing the strategic value of the event for team collaboration and innovation.
   ```

   ![](./media/ex1-email-leadership-prompt.png)

   **Expected Output:**

   ![](./media/ex1-email-leadership.png)

### Task 5: Generate Event Logistics Checklist

In this task, you will create a comprehensive logistics checklist for event preparation.

1. Type the following prompt:

   **Prompt:**
   ```
   Create a comprehensive logistics checklist for organizing the hybrid hackathon event. Include categories for:
   - Venue and setup (for in-person)
   - Technology and tools (for hybrid participation)
   - Catering and refreshments
   - Communication and marketing
   - Day-of-event coordination
   - Post-event follow-up
   
   Format it as a checklist with responsible parties and deadlines.
   ```

   ![](./media/ex1-checklist-prompt.png)

   **Expected Output:**

   ![](./media/ex1-checklist-response.png)

   Copilot generates a comprehensive checklist organized by category.

1. To make this actionable, ask Copilot to prioritize tasks:

   **Prompt:**
   ```
   Convert the top 10 most critical items from this checklist into a task list format with suggested deadlines, assuming the event is 4 weeks away.
   ```

   ![](./media/ex1-task-list-prompt.png)

   **Expected Output:**

   ![](./media/ex1-task-list.png)

   Copilot creates a prioritized task list with deadlines.

1. Finally, ask Copilot to summarize the entire event plan:

   ```
   Summarize our entire event planning conversation into a one-page executive brief that I can share with my manager for approval.
   ```

   ![](./media/ex1-executive-summary.png)

   >**Note:** You can copy this summary and paste it into a Word document or email directly. Copilot maintains context throughout the conversation, making it easy to iterate and refine your event plan.

## Summary

In this exercise, you successfully used Microsoft 365 Copilot Chat to:

- Access and navigate the Copilot Chat interface
- Generate creative event planning ideas and themes
- Create a detailed event agenda for a hybrid event
- Draft professional event invitation emails for different audiences
- Generate comprehensive logistics checklists and task lists

You experienced how Copilot Chat maintains conversational context, allowing for natural iteration and refinement of content. This demonstrates how Copilot can significantly accelerate planning and content creation tasks.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
