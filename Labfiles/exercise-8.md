# Exercise 8: Create a Career Guidance SharePoint Agent

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will create a SharePoint-based agent that provides career guidance to employees. SharePoint agents leverage the content stored in SharePoint sites to provide contextual and grounded responses. This is particularly powerful for organizational knowledge bases, as the agent can answer questions based on your company's specific documentation and resources.

You will create a SharePoint site with career development resources and configure an agent that helps employees navigate their career paths within the organization.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create a Career Development SharePoint site
- Task 2: Populate the site with career resources
- Task 3: Create a SharePoint agent
- Task 4: Configure agent settings and knowledge scope
- Task 5: Test and share the Career Guidance agent

### Task 1: Create a Career Development SharePoint Site

In this task, you will create a dedicated SharePoint site for career development resources.

1. Open a new browser tab and navigate to SharePoint: `https://<inject key="TenantName" enableCopy="false"/>.sharepoint.com`

   ![](./media/ex8-sharepoint-home.png)

1. Click on **+ Create site** in the top navigation.

   ![](./media/ex8-create-site.png)

1. Select **Team site** for collaboration features.

   ![](./media/ex8-team-site.png)

1. Configure the site settings:

   | Field | Value |
   |-------|-------|
   | Site name | `Career Development Hub-<inject key="DeploymentID" enableCopy="false"/>` |
   | Site description | `Resources and guidance for employee career development and growth` |
   | Privacy settings | Private - only members can access |
   | Language | English |

   ![](./media/ex8-site-settings.png)

1. Click **Create** and wait for the site to be provisioned.

   ![](./media/ex8-site-creating.png)

1. Once created, you will be redirected to the new site's home page.

   ![](./media/ex8-site-created.png)

1. Customize the site by adding a logo and updating the home page:

   - Click **Settings** (gear icon) > **Change the look** > **Header**
   - Upload a career-themed logo or use default branding

   ![](./media/ex8-customize-site.png)

### Task 2: Populate the Site with Career Resources

In this task, you will create comprehensive career development content for the agent to use.

1. Navigate to **Documents** library in your new site.

   ![](./media/ex8-documents-library.png)

1. Create a folder structure by clicking **+ New** > **Folder**:
   - `Career Paths`
   - `Skills Development`
   - `Performance & Reviews`
   - `Learning Resources`
   - `Promotion Guidelines`

   ![](./media/ex8-create-folders.png)

1. In the **Career Paths** folder, create a new Word document by clicking **+ New** > **Word document**.

   ![](./media/ex8-new-document.png)

1. Name the document `Engineering-Career-Path.docx` and add the following content:

   ```
   ENGINEERING CAREER PATH GUIDE

   ENGINEERING CAREER LADDER

   Level 1: Junior Engineer (0-2 years experience)
   - Focus on learning and executing assigned tasks
   - Work under close supervision of senior team members
   - Build foundational technical skills
   - Expected competencies: Basic coding, debugging, documentation

   Level 2: Engineer (2-4 years experience)
   - Work independently on moderate complexity projects
   - Begin mentoring junior team members
   - Contribute to technical design discussions
   - Expected competencies: System design basics, code review, project estimation

   Level 3: Senior Engineer (4-7 years experience)
   - Lead technical initiatives and projects
   - Mentor and develop junior engineers
   - Make architectural decisions
   - Expected competencies: Advanced system design, technical leadership, cross-team collaboration

   Level 4: Staff Engineer (7-10 years experience)
   - Drive technical strategy across teams
   - Influence engineering culture and practices
   - Solve organization-wide technical challenges
   - Expected competencies: Strategic thinking, organizational influence, technical vision

   Level 5: Principal Engineer (10+ years experience)
   - Set technical direction for the organization
   - Represent engineering in executive decisions
   - Drive industry-leading technical initiatives
   - Expected competencies: Executive communication, industry expertise, innovation leadership

   GROWTH TIPS
   1. Seek challenging projects that stretch your abilities
   2. Build relationships across teams and departments
   3. Contribute to open source or internal tools
   4. Present at team meetings and conferences
   5. Document and share your learnings
   ```

   ![](./media/ex8-engineering-path.png)

1. Save the document. Create another document `Marketing-Career-Path.docx`:

   ```
   MARKETING CAREER PATH GUIDE

   MARKETING CAREER LADDER

   Level 1: Marketing Coordinator (0-2 years)
   - Execute marketing campaigns under supervision
   - Manage social media scheduling
   - Assist with content creation
   - Track campaign metrics
   - Expected skills: Content writing, social media, basic analytics

   Level 2: Marketing Specialist (2-4 years)
   - Own specific marketing channels or campaigns
   - Develop content strategy for assigned areas
   - Analyze and report on campaign performance
   - Expected skills: Campaign management, data analysis, A/B testing

   Level 3: Senior Marketing Manager (4-7 years)
   - Lead marketing initiatives and team members
   - Develop integrated marketing strategies
   - Manage significant marketing budgets
   - Expected skills: Strategic planning, team leadership, budget management

   Level 4: Director of Marketing (7-10 years)
   - Set marketing strategy for business units
   - Lead and develop marketing teams
   - Partner with sales and product teams
   - Expected skills: Business acumen, executive presence, cross-functional leadership

   Level 5: VP of Marketing (10+ years)
   - Define overall marketing vision and strategy
   - Member of executive leadership team
   - Drive brand and market positioning
   - Expected skills: C-suite communication, market vision, organizational leadership

   GROWTH TIPS
   1. Stay current with digital marketing trends
   2. Build analytical skills and data literacy
   3. Develop cross-functional partnerships
   4. Build and showcase a portfolio of successful campaigns
   5. Pursue relevant certifications (Google, HubSpot, etc.)
   ```

   ![](./media/ex8-marketing-path.png)

1. In the **Skills Development** folder, create `Skills-Framework.docx`:

   ```
   COMPANY SKILLS FRAMEWORK

   CORE COMPETENCIES (Required for all employees)

   1. Communication
   - Clear and concise written communication
   - Effective verbal presentation
   - Active listening
   - Adapting style for different audiences

   2. Collaboration
   - Working effectively in teams
   - Building relationships across departments
   - Conflict resolution
   - Giving and receiving feedback

   3. Problem Solving
   - Analytical thinking
   - Creative solution development
   - Decision making under uncertainty
   - Root cause analysis

   4. Adaptability
   - Embracing change
   - Learning agility
   - Resilience under pressure
   - Growth mindset

   5. Customer Focus
   - Understanding customer needs
   - Delivering quality results
   - Service orientation
   - Building customer relationships

   LEADERSHIP COMPETENCIES (For people managers)

   1. People Development
   - Coaching and mentoring
   - Performance management
   - Career development support
   - Building high-performing teams

   2. Strategic Thinking
   - Vision setting
   - Long-term planning
   - Resource allocation
   - Risk management

   3. Influence & Impact
   - Stakeholder management
   - Executive communication
   - Change leadership
   - Organizational navigation

   SKILL DEVELOPMENT RESOURCES
   - Internal learning platform: learning.company.com
   - External subscriptions: LinkedIn Learning, Coursera
   - Annual learning budget: $2,000 per employee
   - Mentorship program: Contact HR to enroll
   ```

   ![](./media/ex8-skills-framework.png)

1. In the **Promotion Guidelines** folder, create `Promotion-Process.docx`:

   ```
   PROMOTION GUIDELINES AND PROCESS

   OVERVIEW
   Promotions at our company recognize employees who consistently perform above their current level and demonstrate readiness for increased responsibility.

   PROMOTION CRITERIA

   1. Performance Excellence
   - Consistently exceeds expectations in current role
   - Delivers high-quality results
   - Demonstrates reliability and accountability

   2. Skill Demonstration
   - Shows competencies required for next level
   - Has closed skill gaps through development
   - Demonstrates technical or functional expertise

   3. Impact & Scope
   - Work impact extends beyond immediate team
   - Takes on additional responsibilities
   - Contributes to organizational goals

   4. Leadership Behaviors
   - Models company values
   - Mentors and develops others
   - Drives positive team culture

   PROMOTION PROCESS

   Step 1: Self-Assessment (Employee)
   - Review next-level job description and requirements
   - Document achievements and impact
   - Identify supporting evidence and examples
   - Discuss readiness with manager

   Step 2: Manager Nomination
   - Manager completes promotion packet
   - Includes performance history, achievements, peer feedback
   - Submits to department leadership

   Step 3: Calibration Review
   - Leadership reviews all nominations
   - Ensures consistency across teams
   - Makes promotion decisions

   Step 4: Communication
   - Approved promotions communicated to employees
   - Effective date and compensation changes confirmed
   - Development feedback provided if not approved

   PROMOTION CYCLES
   - Major cycle: Annual (aligned with fiscal year)
   - Off-cycle: Available for exceptional cases
   - Submit nominations: 6 weeks before cycle end

   TIPS FOR PROMOTION SUCCESS
   1. Have regular career conversations with your manager
   2. Seek feedback on gaps between current and next level
   3. Document your achievements throughout the year
   4. Take on stretch assignments that demonstrate next-level skills
   5. Build visibility with leadership through project work
   ```

   ![](./media/ex8-promotion-process.png)

1. In the **Learning Resources** folder, create `Learning-Opportunities.docx`:

   ```
   LEARNING & DEVELOPMENT OPPORTUNITIES

   INTERNAL LEARNING PROGRAMS

   1. New Hire Orientation
   - Duration: 1 week
   - Covers company culture, systems, policies
   - Required for all new employees

   2. Leadership Development Program
   - Duration: 6 months
   - For emerging leaders and new managers
   - Cohort-based with executive mentorship
   - Apply through HR

   3. Technical Excellence Program
   - Duration: Ongoing
   - Advanced technical training and certifications
   - Available for engineering, IT, and data roles
   - Budget: Additional $5,000 for certifications

   4. Mentorship Program
   - Duration: 6-12 months
   - Matched with senior leader mentor
   - Monthly meetings and goal setting
   - Open enrollment quarterly

   EXTERNAL LEARNING RESOURCES

   1. LinkedIn Learning
   - Full library access for all employees
   - Self-paced courses on demand
   - Login: Use company SSO

   2. Coursera for Business
   - Professional certificates and courses
   - University partnerships
   - Request access through learning portal

   3. Conference Attendance
   - Annual budget: 1 conference per employee
   - Submit request to manager 3 months in advance
   - Share learnings with team after attendance

   4. Tuition Reimbursement
   - Up to $10,000 per year for degree programs
   - Must be relevant to current or future role
   - Requires manager and HR approval

   HOW TO ACCESS
   1. Visit learning.company.com
   2. Browse course catalog
   3. Discuss development goals with manager
   4. Enroll in relevant programs
   5. Track progress in your development plan

   CONTACT
   Learning & Development Team: learning@company.com
   ```

   ![](./media/ex8-learning-opportunities.png)

1. Verify all documents are saved and visible in the SharePoint site.

   ![](./media/ex8-documents-complete.png)

### Task 3: Create a SharePoint Agent

In this task, you will create an agent directly from your SharePoint site.

1. In your SharePoint site, look for the **Copilot** icon or **Create agent** option. This may be in:
   - The site header/navigation
   - The settings menu
   - The site contents area

   ![](./media/ex8-copilot-option.png)

1. Click on **Create agent** or **Copilot** to start the agent creation process.

   ![](./media/ex8-create-agent.png)

1. If prompted, select **Create a custom agent** for your SharePoint site.

   ![](./media/ex8-custom-agent.png)

1. Configure the agent settings:

   | Field | Value |
   |-------|-------|
   | Agent name | `Career Guidance Agent-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `Your AI assistant for career development, growth opportunities, and professional guidance at our company` |

   ![](./media/ex8-agent-settings.png)

1. Define the agent instructions:

   ```
   You are a Career Guidance Agent designed to help employees navigate their career development at our company. Your role is to:

   1. PROVIDE CAREER PATH GUIDANCE
   - Explain career ladders for different functions
   - Describe requirements for each level
   - Suggest steps to advance to the next level
   - Share relevant growth tips

   2. ANSWER SKILLS QUESTIONS
   - Explain core competencies expected at each level
   - Identify skills needed for career progression
   - Suggest development resources for skill building
   - Connect employees with learning opportunities

   3. EXPLAIN PROMOTION PROCESS
   - Detail the promotion criteria and process
   - Explain promotion cycles and timelines
   - Provide tips for promotion success
   - Clarify what documentation is needed

   4. SHARE LEARNING RESOURCES
   - Inform about internal training programs
   - Explain external learning benefits
   - Guide employees to relevant resources
   - Describe mentorship opportunities

   GUIDELINES
   - Base all answers on the company documentation in this SharePoint site
   - Be encouraging and supportive of career aspirations
   - If information isn't available, direct employees to HR or their manager
   - Provide specific, actionable advice when possible
   - Never make promises about promotions or raises
   - Maintain confidentiality and professionalism
   ```

   ![](./media/ex8-agent-instructions.png)

1. Click **Create** or **Save** to create the agent.

   ![](./media/ex8-create-agent-button.png)

### Task 4: Configure Agent Settings and Knowledge Scope

In this task, you will configure the agent's knowledge sources and additional settings.

1. After creation, you should be in the agent configuration interface. Navigate to **Knowledge** or **Data sources** section.

   ![](./media/ex8-knowledge-section.png)

1. Verify that the SharePoint site content is connected:
   - The Documents library should be included
   - All folders and documents should be accessible

   ![](./media/ex8-verify-knowledge.png)

1. If needed, add specific document libraries or folders:
   - Career Paths folder
   - Skills Development folder
   - Performance & Reviews folder
   - Learning Resources folder
   - Promotion Guidelines folder

   ![](./media/ex8-add-folders.png)

1. Configure conversation starters to guide employees:

   | Starter | Text |
   |---------|------|
   | Career path inquiry | What career paths are available in engineering? |
   | Promotion question | How do I get promoted to the next level? |
   | Skills development | What skills should I develop for career growth? |
   | Learning resources | What learning resources are available to me? |
   | Mentorship | How can I find a mentor? |

   ![](./media/ex8-conversation-starters.png)

1. Set the response behavior:
   - Response style: Professional and encouraging
   - Length: Balanced
   - Citation: Include references to source documents

   ![](./media/ex8-response-settings.png)

1. Save all configuration changes.

   ![](./media/ex8-save-config.png)

### Task 5: Test and Share the Career Guidance Agent

In this task, you will test the agent and share it with your organization.

1. Open the testing interface for your agent.

   ![](./media/ex8-test-interface.png)

1. Test with career path questions:

   ```
   What is the career path for engineers at our company?
   ```

   ![](./media/ex8-test-engineering-path.png)

1. Verify the response includes information from your Engineering-Career-Path document.

   ![](./media/ex8-verify-response.png)

1. Test promotion questions:

   ```
   How do I prepare for a promotion?
   ```

   ![](./media/ex8-test-promotion.png)

1. Test learning resources:

   ```
   What training programs are available for leadership development?
   ```

   ![](./media/ex8-test-learning.png)

1. Test skills questions:

   ```
   What core competencies do I need to demonstrate for career growth?
   ```

   ![](./media/ex8-test-skills.png)

1. Test edge cases:

   ```
   What is the salary for a Senior Engineer?
   ```

   ![](./media/ex8-test-edge-case.png)

   >**Note:** The agent should appropriately respond that salary information isn't available in the knowledge base and direct the user to HR.

1. Once satisfied with testing, share the agent. Navigate to **Share** or **Publish** settings.

   ![](./media/ex8-share-settings.png)

1. Configure sharing options:
   - Share with your organization
   - Make discoverable in Copilot
   - Set appropriate access permissions

   ![](./media/ex8-configure-sharing.png)

1. Click **Share** or **Publish** to make the agent available.

   ![](./media/ex8-publish-agent.png)

1. Verify the agent is accessible in Microsoft 365 Copilot:
   - Navigate to Microsoft 365 Copilot
   - Find the Career Guidance Agent
   - Start a conversation

   ![](./media/ex8-agent-in-copilot.png)

1. Test the agent from Microsoft 365 Copilot to ensure it works correctly.

   ![](./media/ex8-final-test.png)

## Summary

In this exercise, you successfully:

- Created a Career Development Hub SharePoint site
- Populated the site with comprehensive career resources including:
  - Career path guides for different functions
  - Skills framework documentation
  - Promotion guidelines and processes
  - Learning and development opportunities
- Created a SharePoint-based Career Guidance Agent
- Configured the agent's knowledge scope and instructions
- Set up conversation starters for common career questions
- Tested the agent with various career-related queries
- Published and shared the agent with your organization

SharePoint agents are powerful tools for making organizational knowledge accessible through natural conversation. They're ideal for knowledge bases, documentation repositories, and specialized guidance where the content already exists in SharePoint.

### You have successfully completed Day 2 of the lab. Click **Next** to proceed to Day 3.
