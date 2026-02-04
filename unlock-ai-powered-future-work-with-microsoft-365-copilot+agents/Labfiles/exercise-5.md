# Exercise 5: Create and Configure a Copilot Agent in SharePoint to Deliver Contextual Answers

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create a SharePoint Agent that provides contextual answers based on content stored in a SharePoint site. SharePoint Agents are designed to help users find information within organizational content, making it easier to access knowledge stored in documents, pages, and lists.

You will create a SharePoint site with HR policy documents and configure an agent that helps employees find answers to HR-related questions.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create an HR Policies SharePoint site
- Task 2: Populate the site with HR documents
- Task 3: Create a SharePoint Agent
- Task 4: Configure the agent settings
- Task 5: Test the SharePoint Agent

### Task 1: Create an HR Policies SharePoint Site

In this task, you will create a SharePoint site to store HR policy documents.

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
   | Site name | `HR Policies Hub-<inject key="DeploymentID" enableCopy="false"/>` |
   | Site description | `Central repository for HR policies and employee resources` |
   | Privacy settings | Private |

   ![](./media/ex5-site-settings.png)

1. Click **Create** and wait for the site to be provisioned.

   ![](./media/ex5-site-creating.png)

1. Once created, copy the site URL and save it in **Notepad** for later reference.

   ![](./media/ex5-site-created.png)

### Task 2: Populate the Site with HR Documents

In this task, you will create HR policy documents that the agent will use as its knowledge base.

1. In your new SharePoint site, click on **Documents** in the left navigation.

   ![](./media/ex5-documents.png)

1. Click **+ New** > **Folder** to create a folder structure:

   - Create folder: `Policies`
   - Create folder: `Benefits`
   - Create folder: `Procedures`

   ![](./media/ex5-create-folders.png)

1. Navigate to the **Policies** folder and click **+ New** > **Word document**.

   ![](./media/ex5-new-document.png)

1. Name the document `Leave-Policy` and add the following content:

   ```
   EMPLOYEE LEAVE POLICY
   Contoso Corporation
   Effective Date: January 1, 2024

   1. ANNUAL LEAVE

   1.1 Entitlement
   - Full-time employees: 20 days per calendar year
   - Part-time employees: Pro-rated based on working hours
   - New employees: Pro-rated from start date

   1.2 Carryover
   - Maximum 5 days can be carried over to next year
   - Carried over days must be used by March 31
   - Unused days beyond limit will be forfeited

   1.3 Request Process
   - Submit leave request through HR Portal
   - Minimum 2 weeks notice for planned leave
   - Manager approval required before confirmation
   - Emergency leave: Notify manager as soon as possible

   2. SICK LEAVE

   2.1 Entitlement
   - All employees: 10 days per calendar year
   - Does not carry over to next year

   2.2 Documentation
   - 1-2 days: Self-certification accepted
   - 3+ days: Medical certificate required
   - Extended illness: Weekly medical updates required

   3. PARENTAL LEAVE

   3.1 Maternity Leave
   - Primary caregiver: 16 weeks paid leave
   - Can be taken up to 4 weeks before expected due date
   - Additional 8 weeks unpaid leave available

   3.2 Paternity Leave
   - Secondary caregiver: 4 weeks paid leave
   - Must be taken within 3 months of birth/adoption

   4. OTHER LEAVE TYPES

   4.1 Bereavement Leave
   - Immediate family: 5 days paid
   - Extended family: 3 days paid

   4.2 Jury Duty
   - Full pay for duration of service
   - Provide court documentation

   4.3 Personal Days
   - 3 personal days per year
   - 24-hour notice required when possible

   CONTACT
   HR Department: hr@contoso.com
   HR Portal: hrportal.contoso.com
   ```

   ![](./media/ex5-leave-policy.png)

1. Save and close the document.

1. Create another document in the **Benefits** folder named `Benefits-Guide`:

   ```
   EMPLOYEE BENEFITS GUIDE
   Contoso Corporation
   2024 Benefits Overview

   1. HEALTH INSURANCE

   1.1 Medical Coverage
   - PPO Plan: Comprehensive coverage with network flexibility
   - HMO Plan: Lower premiums with network restrictions
   - Company pays 80% of premium costs
   - Coverage begins first day of employment

   1.2 Dental Coverage
   - Preventive care: 100% covered
   - Basic procedures: 80% covered
   - Major procedures: 50% covered
   - Annual maximum: $2,000 per person

   1.3 Vision Coverage
   - Annual eye exam: Fully covered
   - Glasses/contacts allowance: $200/year
   - Frame allowance: $150/year

   2. RETIREMENT BENEFITS

   2.1 401(k) Plan
   - Company match: 100% up to 4% of salary
   - Additional 50% match on next 2%
   - Vesting: Immediate for employee contributions
   - Company match vesting: 3-year graded schedule

   2.2 Pension Plan
   - Available for employees with 5+ years service
   - Defined benefit based on years of service and salary

   3. WELLNESS BENEFITS

   3.1 Gym Membership
   - $50/month reimbursement toward gym membership
   - Submit receipts through expense portal

   3.2 Mental Health Support
   - Employee Assistance Program (EAP)
   - 6 free counseling sessions per year
   - 24/7 crisis hotline available

   3.3 Wellness Stipend
   - $500 annual wellness stipend
   - Use for fitness equipment, wellness apps, classes

   4. ADDITIONAL BENEFITS

   4.1 Life Insurance
   - Basic: 2x annual salary (company paid)
   - Supplemental: Up to 5x salary (employee paid)

   4.2 Disability Insurance
   - Short-term: 60% of salary for up to 12 weeks
   - Long-term: 60% of salary after 12 weeks

   4.3 Education Assistance
   - Tuition reimbursement: Up to $5,250/year
   - Must maintain B average
   - Must be job-related coursework

   ENROLLMENT
   - Open enrollment: November 1-30 annually
   - New hires: 30 days from start date
   - Life events: 30 days from qualifying event

   CONTACT
   Benefits Team: benefits@contoso.com
   Benefits Portal: benefits.contoso.com
   ```

   ![](./media/ex5-benefits-guide.png)

1. Save and close the document.

1. Create a document in the **Procedures** folder named `Onboarding-Checklist`:

   ```
   NEW EMPLOYEE ONBOARDING CHECKLIST
   Contoso Corporation

   BEFORE YOUR FIRST DAY

   HR will send:
   - Welcome email with start date and time
   - New hire paperwork (complete online)
   - IT equipment request form
   - Building access request

   You should:
   - Complete all online paperwork
   - Provide required documents (ID, tax forms)
   - Set up direct deposit
   - Review employee handbook

   FIRST DAY

   Morning:
   - Report to reception at 9:00 AM
   - Meet with HR for orientation
   - Receive employee badge
   - Collect IT equipment
   - Complete security training

   Afternoon:
   - Meet your manager and team
   - Tour of office facilities
   - Set up workstation
   - Access system accounts

   FIRST WEEK

   Complete required training:
   - Information Security Awareness
   - Code of Conduct
   - Anti-Harassment Training
   - Safety and Emergency Procedures

   Meet with:
   - Direct manager (goals and expectations)
   - HR (benefits enrollment)
   - IT (system access and tools)
   - Mentor (if assigned)

   FIRST 30 DAYS

   - Complete all required training modules
   - Enroll in benefits (within 30 days)
   - Set up 401(k) contributions
   - Schedule 30-day check-in with manager
   - Join relevant Teams channels
   - Update profile in company directory

   FIRST 90 DAYS

   - Complete probation period review
   - Finalize performance goals
   - Complete any role-specific certifications
   - Participate in team meetings
   - Schedule 90-day review with manager

   RESOURCES

   - HR Portal: hrportal.contoso.com
   - IT Help Desk: helpdesk.contoso.com
   - Employee Directory: directory.contoso.com
   - Learning Platform: learn.contoso.com

   CONTACTS

   HR Onboarding Team: onboarding@contoso.com
   Your HR Business Partner: [Assigned in welcome email]
   IT Support: itsupport@contoso.com
   ```

   ![](./media/ex5-onboarding-checklist.png)

1. Save and close the document.

### Task 3: Create a SharePoint Agent

In this task, you will create a SharePoint Agent for the HR Policies site.

1. In the SharePoint site, click on the **Settings** gear icon in the top right corner.

   ![](./media/ex5-settings.png)

1. Look for **Copilot** or **Create agent** option in the settings menu.

   ![](./media/ex5-copilot-option.png)

   >**Note:** If this option is not available, you can create the agent through Microsoft 365 Copilot and add the SharePoint site as a knowledge source.

1. Alternatively, navigate to Microsoft 365 Copilot:
   - Go to `https://www.microsoft365.com`
   - Click on **Copilot** in the left navigation
   - Click on **Agents** > **Create agent**

   ![](./media/ex5-create-agent-copilot.png)

1. Configure the agent:

   | Field | Value |
   |-------|-------|
   | Agent name | `HR Policy Assistant-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `Helps employees find information about HR policies, benefits, leave, and onboarding procedures.` |

   ![](./media/ex5-agent-config.png)

### Task 4: Configure the Agent Settings

In this task, you will configure the agent instructions and knowledge sources.

1. In the **Instructions** section, enter:

   **Agent Instructions:**
   ```
   You are an HR Policy Assistant that helps employees find information about company policies and procedures. Your role is to:

   1. Answer questions about leave policies (annual, sick, parental, bereavement)
   2. Explain employee benefits (health insurance, retirement, wellness)
   3. Guide new employees through the onboarding process
   4. Provide information about HR procedures and contacts

   Guidelines:
   - Provide accurate information based on official HR documents
   - Quote specific policy details when relevant
   - Direct employees to HR for personal situations requiring judgment
   - Remind employees to check the HR portal for the most current information
   - Be helpful and professional in all interactions

   You should NOT:
   - Make decisions about individual employee cases
   - Provide legal or financial advice
   - Share confidential employee information
   - Approve or deny leave requests
   ```

   ![](./media/ex5-instructions.png)

1. In the **Knowledge** section, click **+ Add knowledge source**.

   ![](./media/ex5-add-knowledge.png)

1. Select **SharePoint** and enter your HR Policies site URL.

   ![](./media/ex5-sharepoint-knowledge.png)

   >**Note:** If the site shows as not found, this may be due to indexing delays. Select **Add anyway** to continue.

1. Click **Add** to include the SharePoint site.

1. Click **Create** to finalize the agent.

   ![](./media/ex5-create-agent.png)

### Task 5: Test the SharePoint Agent

In this task, you will test the agent with HR-related queries.

1. In the agent chat interface, start with a general question:

   **Prompt:**
   ```
   How many days of annual leave do I get?
   ```

   ![](./media/ex5-test-leave.png)

   **Expected Output:**

   ![](./media/ex5-leave-response.png)

   The agent should provide information about annual leave entitlement from the Leave Policy document.

1. Test benefits questions:

   **Prompt:**
   ```
   What is the company match for the 401(k) plan?
   ```

   ![](./media/ex5-test-401k.png)

   **Expected Output:**

   ![](./media/ex5-401k-response.png)

1. Test onboarding questions:

   **Prompt:**
   ```
   I am a new employee starting next week. What should I do on my first day?
   ```

   ![](./media/ex5-test-onboarding.png)

   **Expected Output:**

   ![](./media/ex5-onboarding-response.png)

1. Test health insurance questions:

   **Prompt:**
   ```
   What health insurance options are available and how much does the company pay?
   ```

   ![](./media/ex5-test-health.png)

   **Expected Output:**

   ![](./media/ex5-health-response.png)

1. Test parental leave:

   **Prompt:**
   ```
   I am expecting a baby. What parental leave am I entitled to?
   ```

   ![](./media/ex5-test-parental.png)

   **Expected Output:**

   ![](./media/ex5-parental-response.png)

1. Test document requirements:

   **Prompt:**
   ```
   How many sick days require a medical certificate?
   ```

   ![](./media/ex5-test-medical.png)

   **Expected Output:**

   ![](./media/ex5-medical-response.png)

1. Test contact information:

   **Prompt:**
   ```
   How do I contact HR about my benefits enrollment?
   ```

   ![](./media/ex5-test-contact.png)

   **Expected Output:**

   ![](./media/ex5-contact-response.png)

## Summary

In this exercise, you created a SharePoint Agent that delivers contextual answers based on HR policy documents. You learned how to:

- Create a SharePoint site for organizational content
- Populate the site with policy documents
- Create and configure a SharePoint Agent
- Define agent instructions for specific use cases
- Test the agent with various HR-related queries

SharePoint Agents help employees quickly find information within organizational content, reducing the need for manual searches and HR inquiries.

### You have successfully completed this exercise. Click on Next to proceed to the Day 2 Overview.
