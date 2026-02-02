# Exercise 9: Implement Prompt Action to Generate Quiz Questions Based on a Topic

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will implement a prompt action in Microsoft Copilot Studio that generates quiz questions based on a given topic. Prompt actions allow you to create custom AI-powered responses by defining specific instructions and parameters that shape how the agent generates content.

This is useful for educational scenarios, training content creation, and knowledge assessment automation.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Access Copilot Studio and create a Quiz Generator agent
- Task 2: Configure a prompt action for quiz generation
- Task 3: Define prompt parameters and instructions
- Task 4: Integrate the prompt action into a topic
- Task 5: Test and refine the quiz generator

### Task 1: Access Copilot Studio and Create a Quiz Generator Agent

In this task, you will create a new agent specifically designed for generating educational quizzes.

1. In the VM, open **Microsoft Edge** browser and navigate to:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex9-studio-url.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex9-signin.png)

1. On the Copilot Studio home page, click **+ Create** from the left navigation.

   ![](./media/ex9-create.png)

1. Select **New agent**.

   ![](./media/ex9-new-agent.png)

1. In the **Describe your agent** field, enter:

   **Agent Description:**
   ```
   Create a quiz generator agent that:
   - Takes a topic from the user
   - Generates multiple choice questions about that topic
   - Supports different difficulty levels
   - Creates answer keys with explanations
   - Can generate quizzes of varying lengths
   - Helps educators and trainers create assessments quickly
   ```

   ![](./media/ex9-agent-description.png)

1. Click **Create** to generate the agent.

1. Once created, configure the agent settings:

   - Click **Settings** from the top menu
   - Update the following:

   | Field | Value |
   |-------|-------|
   | Name | `Quiz Generator-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `An intelligent agent that generates educational quiz questions on any topic` |

   ![](./media/ex9-agent-settings.png)

1. Click **Save** to save the settings.

### Task 2: Configure a Prompt Action for Quiz Generation

In this task, you will create a prompt action that defines how quiz questions are generated.

1. In the agent editor, click on **Actions** in the left navigation.

   ![](./media/ex9-actions.png)

1. Click **+ Add an action**.

   ![](./media/ex9-add-action.png)

1. Select **Prompt** from the action types.

   ![](./media/ex9-select-prompt.png)

   >**Note:** Prompt actions allow you to create custom AI-powered responses using specific instructions and parameters.

1. In the prompt action editor, configure the following:

   **Name:**
   ```
   Generate Quiz Questions
   ```

   ![](./media/ex9-prompt-name.png)

1. In the **Describe the prompt's purpose** field, enter:

   ```
   Generate multiple choice quiz questions based on a specified topic, difficulty level, and number of questions
   ```

   ![](./media/ex9-prompt-purpose.png)

### Task 3: Define Prompt Parameters and Instructions

In this task, you will define the input parameters and detailed instructions for the prompt action.

1. In the **Inputs** section, click **+ Add input** to add parameters:

   **Input 1 - Topic:**
   - Name: `Topic`
   - Description: `The subject or topic for which to generate quiz questions`
   - Type: Text
   - Required: Yes

   ![](./media/ex9-input-topic.png)

1. **Input 2 - Number of Questions:**

   - Click **+ Add input**
   - Name: `NumberOfQuestions`
   - Description: `How many questions to generate (1-10)`
   - Type: Text
   - Required: Yes

   ![](./media/ex9-input-number.png)

1. **Input 3 - Difficulty Level:**

   - Click **+ Add input**
   - Name: `DifficultyLevel`
   - Description: `The difficulty level - Easy, Medium, or Hard`
   - Type: Text
   - Required: Yes

   ![](./media/ex9-input-difficulty.png)

1. In the **Prompt** section, enter the detailed instructions:

   ```
   You are an expert educational content creator specializing in creating quiz questions for learning and assessment purposes.

   Generate exactly {{NumberOfQuestions}} multiple choice quiz questions about the topic: {{Topic}}

   Difficulty Level: {{DifficultyLevel}}

   Follow these guidelines:

   ## Question Format:
   For each question, provide:
   1. The question number and question text
   2. Four answer options labeled A, B, C, and D
   3. The correct answer
   4. A brief explanation of why that answer is correct

   ## Difficulty Guidelines:
   - Easy: Basic concepts, straightforward questions, commonly known facts
   - Medium: Requires some understanding and application of concepts
   - Hard: Complex scenarios, requires deeper understanding, may include tricky options

   ## Quality Standards:
   - Questions should be clear and unambiguous
   - All incorrect options (distractors) should be plausible
   - Avoid obvious wrong answers
   - Each question should test a different aspect of the topic
   - Explanations should be educational and help reinforce learning

   ## Output Format:
   Present the quiz in this format:

   **Quiz: [Topic Name]**
   **Difficulty: [Level]**
   **Number of Questions: [Number]**

   ---

   **Question 1:** [Question text]
   A) [Option A]
   B) [Option B]
   C) [Option C]
   D) [Option D]

   **Correct Answer:** [Letter]
   **Explanation:** [Brief explanation]

   ---

   [Continue for all questions...]

   ---

   **Answer Key Summary:**
   1. [Letter] - [Brief topic]
   2. [Letter] - [Brief topic]
   [etc.]

   Now generate the quiz based on the provided parameters.
   ```

   ![](./media/ex9-prompt-instructions.png)

1. In the **Outputs** section, configure the output:

   - Name: `QuizContent`
   - Description: `The generated quiz questions with answers and explanations`
   - Type: Text

   ![](./media/ex9-output.png)

1. Click **Save** to save the prompt action.

   ![](./media/ex9-save-prompt.png)

### Task 4: Integrate the Prompt Action into a Topic

In this task, you will create a topic that uses the prompt action to generate quizzes interactively.

1. Click on **Topics** in the left navigation.

   ![](./media/ex9-topics.png)

1. Click **+ New topic** > **From blank**.

   ![](./media/ex9-new-topic.png)

1. Name the topic `Generate Quiz` and add trigger phrases:

   ```
   Create a quiz
   Generate quiz questions
   Make a test
   I need quiz questions
   Create assessment questions
   Help me make a quiz
   Generate questions about
   ```

   ![](./media/ex9-topic-triggers.png)

1. Build the conversation flow to collect quiz parameters:

   **Step 1 - Welcome Message:**
   
   Add a **Message** node:
   ```
   I can help you create a quiz on any topic! Let me gather some information about what you need.
   ```

   ![](./media/ex9-welcome-message.png)

1. **Step 2 - Collect Topic:**

   Add a **Question** node:
   - Question text: `What topic would you like the quiz to cover? (e.g., "World War II", "Python Programming", "Climate Change")`
   - Identify: User's entire response
   - Save response as: `QuizTopic`

   ![](./media/ex9-topic-question.png)

1. **Step 3 - Collect Number of Questions:**

   Add a **Question** node:
   - Question text: `How many questions would you like? (Choose 1-10)`
   - Identify: Multiple choice options
   - Options:
     - 3
     - 5
     - 7
     - 10

   - Save response as: `QuestionCount`

   ![](./media/ex9-count-question.png)

1. **Step 4 - Collect Difficulty Level:**

   Add a **Question** node:
   - Question text: `What difficulty level should the questions be?`
   - Identify: Multiple choice options
   - Options:
     - Easy
     - Medium
     - Hard

   - Save response as: `QuizDifficulty`

   ![](./media/ex9-difficulty-question.png)

1. **Step 5 - Confirm and Generate:**

   Add a **Message** node:
   ```
   Great! I'll generate a {QuizDifficulty} quiz with {QuestionCount} questions about {QuizTopic}.

   Please wait while I create your quiz...
   ```

   ![](./media/ex9-confirm-message.png)

1. **Step 6 - Call the Prompt Action:**

   Add a **Call an action** node:
   - Select **Generate Quiz Questions** (the prompt action you created)

   ![](./media/ex9-call-prompt.png)

1. Map the inputs:

   - Topic: `QuizTopic`
   - NumberOfQuestions: `QuestionCount`
   - DifficultyLevel: `QuizDifficulty`

   ![](./media/ex9-map-inputs.png)

1. **Step 7 - Display the Quiz:**

   Add a **Message** node to display the output:
   ```
   Here is your quiz:

   {Topic.QuizContent}

   Would you like me to generate another quiz on a different topic?
   ```

   ![](./media/ex9-display-quiz.png)

1. **Step 8 - Add Follow-up Options:**

   Add a **Question** node:
   - Question text: `What would you like to do next?`
   - Identify: Multiple choice options
   - Options:
     - Generate another quiz
     - Make the quiz harder
     - Make the quiz easier
     - Add more questions
     - I'm done

   - Save response as: `NextAction`

   ![](./media/ex9-followup-question.png)

1. Add **Condition** branches based on the response:

   - If "Generate another quiz" - Redirect back to topic start
   - If "I'm done" - End with goodbye message

   ![](./media/ex9-conditions.png)

1. Click **Save** to save the topic.

   ![](./media/ex9-save-topic.png)

### Task 5: Test and Refine the Quiz Generator

In this task, you will test the quiz generator with various topics and difficulty levels.

1. Click the **Test** button to open the test panel.

   ![](./media/ex9-test-button.png)

1. **Test 1 - Basic Quiz Generation:**

   **Prompt:**
   ```
   Create a quiz
   ```

   ![](./media/ex9-test-start.png)

   **Expected Flow:**

   The agent should ask for topic, number of questions, and difficulty:

   ![](./media/ex9-test-flow.png)

1. Provide the following information:

   - Topic: `Solar System`
   - Number of questions: `5`
   - Difficulty: `Easy`

   ![](./media/ex9-test-inputs.png)

   **Expected Output:**

   The agent should generate a quiz like this:

   ![](./media/ex9-quiz-output.png)

   >**Note:** The actual questions and content will vary based on AI generation. The format should follow the specified structure with questions, options, correct answers, and explanations.

1. **Test 2 - Technical Topic:**

   Start a new conversation:

   **Prompt:**
   ```
   I need quiz questions
   ```

   Provide:
   - Topic: `Microsoft 365 Copilot features`
   - Number of questions: `3`
   - Difficulty: `Medium`

   ![](./media/ex9-test-technical.png)

   **Expected Output:**

   ![](./media/ex9-technical-output.png)

1. **Test 3 - Hard Difficulty:**

   Start a new conversation:

   **Prompt:**
   ```
   Generate quiz questions
   ```

   Provide:
   - Topic: `Machine Learning algorithms`
   - Number of questions: `5`
   - Difficulty: `Hard`

   ![](./media/ex9-test-hard.png)

   **Expected Output:**

   The questions should be noticeably more challenging with complex scenarios:

   ![](./media/ex9-hard-output.png)

1. **Test 4 - Follow-up Actions:**

   After generating a quiz, test the follow-up options:

   - Select "Generate another quiz" to verify the flow restarts correctly

   ![](./media/ex9-test-followup.png)

1. **Verify Question Quality:**

   Review the generated quizzes for:
   - Correct formatting (questions, options A-D, answers, explanations)
   - Appropriate difficulty level
   - Accurate information
   - Plausible distractors (wrong answers)

   ![](./media/ex9-verify-quality.png)

1. If needed, refine the prompt instructions in the prompt action:

   - Navigate back to **Actions** > **Generate Quiz Questions**
   - Modify the prompt instructions to improve output quality
   - Save and test again

   ![](./media/ex9-refine-prompt.png)

1. Once testing is complete, click **Publish** to publish the agent.

   ![](./media/ex9-publish.png)

1. Select the channels for publishing and confirm.

   ![](./media/ex9-publish-confirm.png)

## Summary

In this exercise, you implemented a prompt action in Microsoft Copilot Studio to generate educational quiz questions. You learned how to:

- Create a specialized quiz generator agent
- Configure prompt actions with detailed instructions
- Define input parameters for customizable outputs
- Build conversational flows that integrate prompt actions
- Test and refine AI-generated content
- Create follow-up options for enhanced user experience

Prompt actions are powerful tools for creating custom AI-powered responses that can be tailored to specific business needs, from educational content to automated report generation.

### You have successfully completed this exercise. Congratulations on completing all exercises in this lab!
