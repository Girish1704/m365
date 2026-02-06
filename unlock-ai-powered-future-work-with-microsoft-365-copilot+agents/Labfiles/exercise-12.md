# Exercise 12: Build Conversational Topics and Deploy Quiz Generator

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will build a conversational topic that integrates the prompt action created in the previous exercise. Users will be able to interactively generate quizzes through a guided conversation that collects their preferences and delivers customized quiz content. You will also test the complete solution and optionally deploy it to Microsoft Teams.

By the end of this exercise, you will have a fully functional Quiz Generator agent that users can interact with through natural conversation.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create the Generate Quiz Topic
- Task 2: Build the Conversation Flow
- Task 3: Connect the Prompt Action to the Topic
- Task 4: Test the Complete Quiz Generator
- Task 5: Publish and Deploy to Teams (Optional)

### Task 1: Create the Generate Quiz Topic

In this task, you will create a topic that triggers when users want to generate a quiz.

1. In Microsoft Copilot Studio, open your **Quiz Generator** agent created in the previous exercise.

   ![](../media/ex12-open-agent.png)

1. Click on **Topics** in the left navigation panel.

   ![](../media/ex12-topics-nav.png)

1. Click **+ Add a topic** and select **From blank**.

   ![](../media/ex12-new-topic.png)

1. Configure the topic name:

   **Topic Name:**
   ```
   Generate Quiz
   ```

   ![](../media/ex12-topic-name.png)

1. In the **Trigger** node, you'll see **The agent chooses** with an **Edit** link. In the **Describe what the topic does** field, enter:

   ```
   This topic generates customized multiple-choice quiz questions on any topic. It helps users create quizzes by collecting the topic, number of questions, and difficulty level. Users can ask things like "Create a quiz", "Generate quiz questions", "Make a test", "Quiz me on", or "Help me make a quiz".
   ```

   ![](../media/ex12-trigger-description.png)

1. Click **Save** to save the topic configuration.

   ![](../media/ex12-save-topic.png)

### Task 2: Build the Conversation Flow

In this task, you will create the conversation flow that collects quiz parameters from users.

1. In the topic editor, you'll see the trigger node. Click the **+** button below it to add the first step.

   ![](../media/ex12-add-first-step.png)

1. **Step 1 - Welcome Message:**

   Select **Send a message** and enter:

   ```
   Welcome to the Quiz Generator!

   I can create customized multiple-choice quizzes on any topic you'd like.
   ```

   ![](../media/ex12-welcome-message.png)

1. Click **+** to add the next step.

1. **Step 2 - Collect Topic:**

   Select **Ask a question** and configure:

   | Field | Value |
   |-------|-------|
   | Question text | `What topic would you like the quiz to cover?` |
   | Subtitle (optional) | `For example: "Solar System", "World War II", "Python Programming", "Microsoft 365"` |
   | Identify | User's entire response |
   | Save response as | Click **>** and create a new variable named `QuizTopic` |

   ![](../media/ex12-topic-question.png)

1. Click **+** to add the next step.

1. **Step 3 - Collect Number of Questions:**

   Select **Ask a question** and configure:

   | Field | Value |
   |-------|-------|
   | Question text | `How many questions would you like in your quiz?` |
   | Identify | Multiple choice options |

   Add the following options:
   - `3 questions`
   - `5 questions`
   - `7 questions`
   - `10 questions`

   | Field | Value |
   |-------|-------|
   | Save response as | Create a new variable named `QuestionCount` |

   ![](../media/ex12-count-question.png)

1. Click **+** to add the next step.

1. **Step 4 - Collect Difficulty Level:**

   Select **Ask a question** and configure:

   | Field | Value |
   |-------|-------|
   | Question text | `What difficulty level would you prefer?` |
   | Identify | Multiple choice options |

   Add the following options:
   - `Easy - Basic concepts and facts`
   - `Medium - Requires understanding and application`
   - `Hard - Complex scenarios and deep knowledge`

   | Field | Value |
   |-------|-------|
   | Save response as | Create a new variable named `QuizDifficulty` |

   ![](../media/ex12-difficulty-question.png)

1. Click **+** to add the next step.

1. **Step 5 - Convert Choice Variables to Text:**

   Since the prompt action expects string inputs, we need to convert the multiple choice variables to text format.

   Select **Variable management** > **Set a variable value** and configure:

   | Field | Value |
   |-------|-------|
   | Variable | Click **Create new** and name it `QuestionCountText` |
   | To value | Use the formula: `Text(Topic.QuestionCount)` |

   ![](../media/ex12-convert-count.png)

1. Click **+** and add another **Set a variable value**:

   | Field | Value |
   |-------|-------|
   | Variable | Click **Create new** and name it `DifficultyText` |
   | To value | Use the formula: `Text(Topic.QuizDifficulty)` |

   ![](../media/ex12-convert-difficulty.png)

   >**Note:** The `Text()` function converts the choice/option set value to a string that the prompt action can accept.

1. Click **+** to add the next step.

1. **Step 6 - Confirmation Message:**

   Select **Send a message** and enter:

   ```
   Perfect! Here's what I'll create for you:

   Topic: {Topic.QuizTopic}
   Questions: {Topic.QuestionCountText}
   Difficulty: {Topic.DifficultyText}

   Generating your quiz now... Please wait a moment.
   ```

   ![](../media/ex12-confirm-message.png)

   >**Note:** Use the **{x}** button to insert variables. The variable format may appear as `{Topic.VariableName}` or just `{VariableName}` depending on your Copilot Studio version.

1. Click **Save** to save your progress.

### Task 3: Connect the Prompt Action to the Topic

In this task, you will integrate the prompt action to generate the quiz based on collected parameters.

1. Click **+** after the confirmation message to add the next step.

1. Select **Call an action** (or **Add a tool**).

   ![](../media/ex12-call-action.png)

1. In the action selection panel, find and select **Generate Quiz Questions** (the prompt action you created in Exercise 11).

   ![](../media/ex12-select-prompt-action.png)

1. Map the input parameters using the **converted text variables**:

   | Prompt Input | Topic Variable |
   |--------------|----------------|
   | Topic | `QuizTopic` |
   | NumberOfQuestions | `QuestionCountText` |
   | DifficultyLevel | `DifficultyText` |

   ![](../media/ex12-map-inputs.png)

   >**Tip:** Click on each input field, then click the **{x}** icon to select the corresponding variable from the topic. Make sure to use the Text versions of the variables (QuestionCountText and DifficultyText) for the prompt action inputs.

1. The action will automatically create an output variable for the quiz content. Note the output variable name (e.g., `QuizContent` or `Generate Quiz Questions.QuizContent`).

   ![](../media/ex12-action-output.png)

1. Click **+** to add the next step.

1. **Step 6 - Display the Generated Quiz:**

   Select **Send a message** and enter:

   ```
   Here's your customized quiz!

   {Topic.QuizContent}
   ```

   >**Note:** Replace `{Topic.QuizContent}` with the actual output variable from your prompt action. Use the **{x}** button to insert it correctly.

   ![](../media/ex12-display-quiz.png)

1. Click **+** to add the follow-up step.

1. **Step 7 - Follow-up Options:**

   Select **Ask a question** and configure:

   | Field | Value |
   |-------|-------|
   | Question text | `What would you like to do next?` |
   | Identify | Multiple choice options |

   Add the following options:
   - `Generate another quiz`
   - `Make it harder`
   - `Make it easier`
   - `Add more questions`
   - `I'm done, thank you!`

   | Field | Value |
   |-------|-------|
   | Save response as | Create a new variable named `NextAction` |

   ![](../media/ex12-followup-options.png)

1. Click **+** to add condition branches.

1. **Step 8 - Handle Follow-up Actions:**

   Select **Add a condition** > **Branch based on a condition**.

   ![](../media/ex12-add-condition.png)

1. Configure the first condition:

   - Condition: `NextAction` **is equal to** `Generate another quiz`
   - Action: Select **Redirect to another topic** > **Generate Quiz** (redirects back to start)

   ![](../media/ex12-condition-another.png)

1. Add another condition branch:

   - Condition: `NextAction` **is equal to** `I'm done, thank you!`
   - Action: Add a **Message** node:
     ```
     Thank you for using the Quiz Generator!

     Good luck with your learning journey. Feel free to come back anytime you need more quizzes!
     ```

   ![](../media/ex12-condition-done.png)

1. For the "Make it harder" / "Make it easier" / "Add more questions" options, you can either:

   - **Option A:** Set the corresponding variable and redirect back to the prompt action
   - **Option B:** Add a message suggesting they start a new quiz with different settings

   For simplicity, add a default message:
   ```
   To change difficulty or add more questions, let's start a new quiz! Just tell me the topic again.
   ```

   Then redirect to the topic start.

   ![](../media/ex12-default-action.png)

1. Click **Save** to save the complete topic.

   ![](../media/ex12-save-complete.png)

### Task 4: Test the Complete Quiz Generator

In this task, you will perform comprehensive testing of the quiz generator.

1. Click the **Test** button in the top-right corner to open the test panel.

   ![](../media/ex12-test-button.png)

1. **Test 1 - Complete Flow:**

   **Prompt:**
   ```
   Create a quiz
   ```

   ![](../media/ex12-test-start.png)

1. Follow the conversation:

   - **Topic:** `Solar System`
   - **Questions:** `5 questions`
   - **Difficulty:** `Easy - Basic concepts and facts`

   ![](../media/ex12-test-flow.png)

1. Verify the output:

   - [ ] Welcome message appears
   - [ ] Topic question is asked
   - [ ] Number of questions options appear
   - [ ] Difficulty level options appear
   - [ ] Confirmation message shows selected options
   - [ ] Quiz is generated with correct format
   - [ ] Questions match the topic (Solar System)
   - [ ] Difficulty is appropriate (Easy)
   - [ ] Follow-up options appear

   ![](../media/ex12-test-output.png)

1. **Test 2 - Different Topic and Difficulty:**

   Click **Reset** to start fresh.

   **Prompt:**
   ```
   I need quiz questions
   ```

   Provide:
   - **Topic:** `Microsoft 365 Copilot`
   - **Questions:** `3 questions`
   - **Difficulty:** `Medium - Requires understanding and application`

   ![](../media/ex12-test-medium.png)

1. Verify the medium difficulty questions require more thought and understanding.

1. **Test 3 - Hard Difficulty:**

   Reset and test:

   **Prompt:**
   ```
   Quiz me on
   ```

   Provide:
   - **Topic:** `Machine Learning algorithms`
   - **Questions:** `5 questions`
   - **Difficulty:** `Hard - Complex scenarios and deep knowledge`

   ![](../media/ex12-test-hard.png)

1. Verify the hard questions include complex scenarios and require deep knowledge.

1. **Test 4 - Follow-up Actions:**

   After generating a quiz, select:
   - `Generate another quiz`

   Verify the conversation restarts and asks for a new topic.

   ![](../media/ex12-test-restart.png)

1. **Test 5 - Completion Flow:**

   Generate a quiz and then select:
   - `I'm done, thank you!`

   Verify the goodbye message appears.

   ![](../media/ex12-test-complete.png)

1. Document your test results:

   | Test Case | Topic | Questions | Difficulty | Status |
   |-----------|-------|-----------|------------|--------|
   | Basic Flow | Solar System | 5 | Beginner | Pass |
   | M365 Topic | Microsoft 365 Copilot | 3 | Intermediate | Pass |
   | Hard Mode | Machine Learning | 5 | Advanced | Pass |
   | Restart | Any | Any | Any | Pass |
   | Goodbye | Any | Any | Any | Pass |

### Task 5: Publish and Deploy to Teams (Optional)

In this task, you will publish the Quiz Generator and optionally deploy it to Microsoft Teams.

1. Once testing is complete, click **Publish** in the top menu.

   ![](../media/ex12-publish-button.png)

1. Review the publishing summary and click **Publish** to confirm.

   ![](../media/ex12-publish-confirm.png)

1. Wait for the publishing process to complete (1-2 minutes).

   ![](../media/ex12-publish-success.png)

1. **(Optional) Deploy to Microsoft Teams:**

   - Click on **Channels** in the left navigation
   - Select **Microsoft Teams**

   ![](../media/ex12-channels.png)

1. Click **Turn on Teams** to enable the Teams channel.

   ![](../media/ex12-turn-on-teams.png)

1. Configure Teams availability:

   - Select **Show to everyone in my org** or **Show to users or groups**
   - Click **Submit for admin approval** (or **Add to Teams** if you have permissions)

   ![](../media/ex12-teams-config.png)

1. Click **Open the app in Teams** to test in Teams.

   ![](../media/ex12-open-teams.png)

1. In Microsoft Teams, test the Quiz Generator:

   **Prompt:**
   ```
   Create a quiz about cloud computing
   ```

   ![](../media/ex12-teams-test.png)

1. Verify the complete flow works correctly in Teams:

   - Welcome message displays
   - All questions are asked correctly
   - Quiz is generated and displayed
   - Follow-up options work

   ![](../media/ex12-teams-complete.png)

## Summary

In this exercise, you built a complete conversational topic that integrates the prompt action for quiz generation. You learned how to:

- Create topics with multiple trigger phrases for natural language activation
- Build multi-step conversation flows with questions and messages
- Use variables to collect and pass user inputs
- Connect prompt actions to topics with proper input mapping
- Handle follow-up actions with condition branches
- Test conversational flows comprehensively
- Publish and deploy agents to Microsoft Teams

Your Quiz Generator agent is now a complete solution that can:
- Generate quizzes on any topic
- Support multiple difficulty levels (Beginner, Intermediate, Advanced)
- Create 3, 5, 7, or 10 questions per quiz
- Provide answer keys with explanations
- Allow users to generate multiple quizzes in one session
- Be accessed through Teams (if deployed)

## Congratulations!

You have successfully completed all exercises in this lab! You've learned how to:

1. **Create Copilot Agents** with custom instructions and knowledge bases
2. **Integrate Freshdesk** for professional ticketing workflows
3. **Build AI-generated Topics** using natural language descriptions
4. **Create Power Automate Flows** for automation
5. **Deploy to Microsoft Teams** for organization-wide access
6. **Implement Prompt Actions** for custom AI content generation
7. **Build Conversational Topics** for interactive user experiences

These skills enable you to build powerful AI-powered solutions using Microsoft Copilot Studio that can transform how your organization handles support, education, and automation.

### You have successfully completed all exercises in this lab!
