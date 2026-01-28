# Exercise 9: Build an Autonomous Agent with Copilot Studio

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will build an autonomous agent using Microsoft Copilot Studio. Autonomous agents are AI-powered assistants that can operate independently, executing tasks and making decisions without requiring constant user input. They are triggered by events, schedules, or conditions and can perform multi-step workflows automatically.

You will create an autonomous agent for employee onboarding that automatically sends welcome messages, assigns training tasks, and schedules orientation meetings for new hires.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Understand autonomous agents and their capabilities
- Task 2: Create an autonomous onboarding agent
- Task 3: Configure triggers and automation rules
- Task 4: Build the autonomous workflow
- Task 5: Test and monitor the autonomous agent

### Task 1: Understand Autonomous Agents and Their Capabilities

In this task, you will learn about autonomous agents and when to use them.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to Microsoft Copilot Studio:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex9-copilot-studio.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. Before building, understand the difference between conversational and autonomous agents:

   | Feature | Conversational Agent | Autonomous Agent |
   |---------|---------------------|------------------|
   | Trigger | User initiates conversation | Events, schedules, conditions |
   | Interaction | Requires user input | Operates independently |
   | Use case | Q&A, support, guidance | Automation, monitoring, workflows |
   | Execution | Synchronous | Asynchronous |

   ![](./media/ex9-agent-types.png)

1. Key capabilities of autonomous agents:

   - **Event-driven triggers** — React to changes in data or systems
   - **Scheduled execution** — Run at specified times or intervals
   - **Multi-step workflows** — Execute complex sequences of actions
   - **Decision making** — Apply AI reasoning to determine next steps
   - **System integration** — Connect with multiple enterprise systems

   ![](./media/ex9-autonomous-capabilities.png)

   >**Note:** Autonomous agents are ideal for repetitive tasks, monitoring scenarios, and processes that don't require human decision-making at every step.

### Task 2: Create an Autonomous Onboarding Agent

In this task, you will create a new autonomous agent for employee onboarding.

1. In Copilot Studio, click on **+ Create** from the left navigation panel.

   ![](./media/ex9-create-copilot.png)

1. Look for the **Autonomous agent** option or select **New agent** and specify autonomous capabilities.

   ![](./media/ex9-autonomous-option.png)

1. In the **Describe your agent** field, enter the following description:

   **Agent Description:**
   ```
   Create an autonomous onboarding agent that:
   - Triggers when a new employee is added to the HR system
   - Automatically sends a welcome email to the new hire
   - Creates onboarding tasks in Microsoft Planner
   - Schedules orientation meetings with HR and the hiring manager
   - Assigns required compliance training
   - Sends reminders for incomplete onboarding tasks
   - Reports onboarding progress to HR
   ```

   ![](./media/ex9-agent-description.png)

1. Click **Create** to generate the agent.

1. Once created, navigate to **Settings** to configure the agent:

   | Field | Value |
   |-------|-------|
   | Name | `Onboarding Automation Agent-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `Autonomous agent that automates the employee onboarding process` |

   ![](./media/ex9-agent-settings.png)

1. Click **Save** to save your settings.

   ![](./media/ex9-agent-created.png)

### Task 3: Configure Triggers and Automation Rules

In this task, you will set up triggers that start the autonomous agent's workflow.

1. In the agent editor, navigate to the **Triggers** section from the left panel.

   ![](./media/ex9-triggers-section.png)

1. Click **+ Add trigger** to create a new trigger.

   ![](./media/ex9-add-trigger.png)

1. Choose the trigger type. For this agent, we'll simulate with a scheduled trigger:

   | Trigger Type | Description |
   |--------------|-------------|
   | Schedule | Run at specific times |
   | When a record is created | React to new data |
   | When data changes | React to updates |
   | Manual | Triggered on demand |

   ![](./media/ex9-trigger-types.png)

1. For this exercise, select **Schedule** trigger to simulate new hire processing:

   | Field | Value |
   |-------|-------|
   | Trigger name | `Daily New Hire Check` |
   | Frequency | Daily |
   | Time | 9:00 AM |
   | Time zone | Your local time zone |

   ![](./media/ex9-schedule-trigger.png)

1. Optionally, add a **Manual trigger** for testing:

   | Field | Value |
   |-------|-------|
   | Trigger name | `Manual Onboarding Start` |
   | Type | Manual |

   ![](./media/ex9-manual-trigger.png)

1. Create a **condition** to check for new hires. Click **+ Add condition** or use the flow designer:

   ```
   Condition: Check if there are new employees added in the last 24 hours
   - Connect to HR data source (simulated with SharePoint list)
   - Filter: Created date = Today
   - Action: For each new hire, execute onboarding workflow
   ```

   ![](./media/ex9-condition.png)

1. Save the trigger configuration.

   ![](./media/ex9-save-trigger.png)

### Task 4: Build the Autonomous Workflow

In this task, you will design the automated onboarding workflow.

1. Navigate to the **Flow** or **Workflow** section of the autonomous agent.

   ![](./media/ex9-workflow-section.png)

1. The workflow designer will show a visual flow builder. Start by adding the first action after the trigger.

   ![](./media/ex9-flow-designer.png)

1. **Action 1: Send Welcome Email**

   Click **+ Add action** and select **Send an email** (using Office 365 Outlook connector):

   | Field | Value |
   |-------|-------|
   | To | New employee email (from trigger data) |
   | Subject | `Welcome to the Team! - Your Onboarding Journey Begins` |
   | Body | (See below) |

   Email body:
   ```
   Dear [Employee Name],

   Welcome to our company! We're thrilled to have you join our team.

   Your onboarding journey begins today, and I'm here to help you every step of the way. Here's what you can expect:

   📋 FIRST WEEK:
   - Complete required compliance training
   - Attend orientation session with HR
   - Meet with your manager and team
   - Set up your workstation and systems access

   📚 RESOURCES:
   - Employee Handbook: [Link]
   - IT Support Portal: [Link]
   - Benefits Enrollment: [Link]

   Your orientation meeting has been scheduled, and training assignments will appear in your learning portal.

   If you have any questions, don't hesitate to reach out!

   Best regards,
   Onboarding Automation Agent
   Human Resources
   ```

   ![](./media/ex9-welcome-email.png)

1. **Action 2: Create Onboarding Tasks**

   Add another action to create tasks in Microsoft Planner or To-Do:

   | Task | Due Date | Assignment |
   |------|----------|------------|
   | Complete I-9 Documentation | Day 1 | New Employee |
   | Set up workstation | Day 1 | IT Team |
   | Attend HR Orientation | Day 2 | New Employee |
   | Complete compliance training | Week 1 | New Employee |
   | Meet with hiring manager | Day 3 | New Employee + Manager |
   | Team introduction meeting | Week 1 | New Employee + Team |

   ![](./media/ex9-create-tasks.png)

1. **Action 3: Schedule Orientation Meeting**

   Add an action to create a calendar event:

   | Field | Value |
   |-------|-------|
   | Subject | `New Employee Orientation - [Employee Name]` |
   | Attendees | New employee, HR representative |
   | Duration | 2 hours |
   | Date | Second business day after start date |
   | Location | HR Conference Room / Teams Meeting |

   ![](./media/ex9-schedule-meeting.png)

1. **Action 4: Assign Training**

   Add an action to assign training (connect to learning management system or send notification):

   ```
   Assign required training courses:
   1. Company Culture and Values (30 min)
   2. Information Security Awareness (45 min)
   3. Harassment Prevention (1 hour)
   4. Safety and Emergency Procedures (30 min)
   
   Completion deadline: End of first week
   ```

   ![](./media/ex9-assign-training.png)

1. **Action 5: Set Reminder Flow**

   Add a delayed action to send reminders:

   | Field | Value |
   |-------|-------|
   | Delay | 3 days after start |
   | Condition | Check if training is incomplete |
   | Action | Send reminder email |

   ![](./media/ex9-reminder-flow.png)

1. **Action 6: Send Progress Report**

   Add a final action to report to HR:

   | Field | Value |
   |-------|-------|
   | To | HR Manager |
   | Subject | `Onboarding Progress Report - [Employee Name]` |
   | Content | Summary of completed and pending tasks |
   | Timing | End of first week |

   ![](./media/ex9-progress-report.png)

1. Connect all actions in the flow designer to create a complete workflow.

   ![](./media/ex9-complete-workflow.png)

1. Save the workflow.

   ![](./media/ex9-save-workflow.png)

### Task 5: Test and Monitor the Autonomous Agent

In this task, you will test the autonomous agent and set up monitoring.

1. Navigate to the **Test** section of the agent.

   ![](./media/ex9-test-section.png)

1. Use the manual trigger to test the workflow:

   - Click **Run test** or **Trigger manually**
   - Provide test data for a new employee:

   | Field | Value |
   |-------|-------|
   | Employee Name | Test Employee |
   | Email | your email for testing |
   | Start Date | Today |
   | Department | Engineering |
   | Manager | Your name |

   ![](./media/ex9-test-data.png)

1. Click **Run** to execute the test.

   ![](./media/ex9-run-test.png)

1. Monitor the workflow execution:

   - Watch each step complete
   - Check for any errors or failures
   - Verify actions are performed correctly

   ![](./media/ex9-monitor-execution.png)

1. Verify the outputs:

   - Check your email for the welcome message
   - Verify tasks were created (if connected to Planner)
   - Check calendar for the orientation meeting

   ![](./media/ex9-verify-outputs.png)

1. Navigate to **Analytics** or **Monitoring** section to view agent performance.

   ![](./media/ex9-analytics.png)

1. Review key metrics:

   - Total runs
   - Success rate
   - Average execution time
   - Error rate and types

   ![](./media/ex9-metrics.png)

1. Set up alerts for failures:

   - Configure email notifications for errors
   - Set thresholds for execution time
   - Enable detailed logging

   ![](./media/ex9-alerts.png)

1. Once testing is complete and successful, enable the scheduled trigger:

   - Navigate to **Triggers**
   - Toggle the schedule trigger to **Active**
   - Confirm activation

   ![](./media/ex9-activate-trigger.png)

1. The autonomous agent is now running and will automatically process new hire onboarding.

   ![](./media/ex9-agent-active.png)

## Summary

In this exercise, you successfully:

- Learned the differences between conversational and autonomous agents
- Created an autonomous onboarding agent in Microsoft Copilot Studio
- Configured triggers including scheduled and manual triggers
- Built a comprehensive automated workflow including:
  - Sending welcome emails
  - Creating onboarding tasks
  - Scheduling orientation meetings
  - Assigning required training
  - Setting up reminders
  - Generating progress reports
- Tested the agent using manual triggers
- Set up monitoring and analytics for the autonomous agent

Autonomous agents are powerful tools for automating repetitive business processes, allowing organizations to scale operations without increasing manual workload.

### You have successfully completed this exercise. Click **Next** to proceed to the next exercise.
