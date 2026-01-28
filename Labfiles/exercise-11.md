# Exercise 11: Implement Prompt Action to Generate Quiz Questions Based on a Topic

## Estimated Duration: 60 Minutes

## Overview

In this exercise, you will implement a prompt action in Microsoft Copilot Studio that generates quiz questions based on any topic. Prompt actions allow you to leverage the power of large language models (LLMs) directly within your agents to generate dynamic content, transform text, and create personalized responses.

You will build a Quiz Generator agent that can create multiple-choice questions, true/false questions, and open-ended questions for training, education, or assessment purposes.

>**Note:** The AI-generated content may vary from the screenshots shown in this exercise. Copilot responses are dynamic and can differ based on various factors.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Understand prompt actions and their capabilities
- Task 2: Create the Quiz Generator agent
- Task 3: Build the quiz generation prompt action
- Task 4: Configure quiz customization options
- Task 5: Test and enhance the quiz generator

### Task 1: Understand Prompt Actions and Their Capabilities

In this task, you will learn about prompt actions and how they can enhance your agents.

1. In the VM, open **Microsoft Edge** browser from the desktop or taskbar.

1. Navigate to Microsoft Copilot Studio:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex11-copilot-studio.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

1. If you see a **Stay signed in?** prompt, select **Yes**.

1. Understand what prompt actions are:

   **Prompt Actions** are AI-powered capabilities that allow agents to:
   - Generate dynamic content using natural language prompts
   - Transform, summarize, or analyze text
   - Create personalized responses based on input
   - Leverage LLM capabilities for complex text generation

   ![](./media/ex11-prompt-actions-overview.png)

1. Key benefits of prompt actions:

   | Benefit | Description |
   |---------|-------------|
   | Dynamic content | Generate unique content for each interaction |
   | Personalization | Tailor responses to user input and context |
   | Flexibility | Handle varied requests without hardcoded responses |
   | Scalability | Create content that would be impractical to pre-write |

   ![](./media/ex11-prompt-benefits.png)

1. Use cases for prompt actions:

   - **Content generation** — Articles, summaries, descriptions
   - **Quiz/test creation** — Questions and answers
   - **Translation** — Language conversion
   - **Data extraction** — Pull information from text
   - **Sentiment analysis** — Understand tone and emotion
   - **Code generation** — Create code snippets

   ![](./media/ex11-use-cases.png)

### Task 2: Create the Quiz Generator Agent

In this task, you will create an agent specifically designed to generate quizzes.

1. In Copilot Studio, click **+ Create** from the left navigation panel.

   ![](./media/ex11-create-copilot.png)

1. Select **New agent** and in the **Describe your agent** field, enter:

   **Agent Description:**
   ```
   Create a Quiz Generator assistant that helps users create quizzes on any topic. The agent should:
   
   - Ask users what topic they want to create a quiz about
   - Let users choose the number of questions (5, 10, 15, or 20)
   - Allow selection of question types (multiple choice, true/false, open-ended)
   - Let users choose difficulty level (easy, medium, hard)
   - Generate high-quality quiz questions with correct answers
   - Format the quiz in a clear, professional manner
   - Provide answer keys separately
   ```

   ![](./media/ex11-agent-description.png)

1. Click **Create** to generate the agent.

1. Once created, navigate to **Settings** to configure the agent:

   | Field | Value |
   |-------|-------|
   | Name | `Quiz Generator-<inject key="DeploymentID" enableCopy="false"/>` |
   | Description | `AI-powered quiz generator that creates custom quizzes on any topic` |

   ![](./media/ex11-agent-settings.png)

1. Click **Save** to save your settings.

1. Navigate to **Topics** and select the **Greeting** topic. Customize the greeting message:

   ```
   Welcome to the Quiz Generator! 🎯📝

   I can create custom quizzes on any topic you need. Whether it's for:
   - 📚 Training and education
   - 🏢 Employee assessments
   - 🎮 Fun trivia games
   - 📖 Study materials

   Just tell me a topic, and I'll generate professional quiz questions with answers!

   What topic would you like to create a quiz about?
   ```

   ![](./media/ex11-greeting.png)

### Task 3: Build the Quiz Generation Prompt Action

In this task, you will create the core prompt action that generates quiz questions.

1. Navigate to **Actions** in your agent.

   ![](./media/ex11-actions-section.png)

1. Click **+ Add an action** > **Create a prompt**.

   ![](./media/ex11-create-prompt.png)

1. Configure the prompt action:

   | Field | Value |
   |-------|-------|
   | Name | `Generate Quiz Questions` |
   | Description | `Generates quiz questions based on topic, type, difficulty, and quantity` |

   ![](./media/ex11-prompt-config.png)

1. Define the input parameters:

   | Parameter | Type | Description |
   |-----------|------|-------------|
   | Topic | Text | The subject matter for the quiz |
   | QuestionCount | Number | Number of questions to generate |
   | QuestionType | Text | Type of questions (multiple choice, true/false, open-ended) |
   | DifficultyLevel | Text | Difficulty (easy, medium, hard) |

   ![](./media/ex11-input-parameters.png)

1. Write the prompt template:

   ```
   You are an expert quiz creator. Generate a high-quality quiz based on the following specifications:

   TOPIC: {{Topic}}
   NUMBER OF QUESTIONS: {{QuestionCount}}
   QUESTION TYPE: {{QuestionType}}
   DIFFICULTY LEVEL: {{DifficultyLevel}}

   INSTRUCTIONS:
   1. Create exactly {{QuestionCount}} questions about {{Topic}}
   2. All questions must be {{QuestionType}} format
   3. Questions should be {{DifficultyLevel}} difficulty
   4. Ensure questions are accurate and educational
   5. Provide clear, unambiguous answer options for multiple choice
   6. Include the correct answer for each question

   FORMAT REQUIREMENTS:

   For MULTIPLE CHOICE questions:
   Q1. [Question text]
   A) [Option A]
   B) [Option B]
   C) [Option C]
   D) [Option D]
   ✓ Correct Answer: [Letter]

   For TRUE/FALSE questions:
   Q1. [Statement]
   ✓ Correct Answer: [True/False]
   Explanation: [Brief explanation]

   For OPEN-ENDED questions:
   Q1. [Question text]
   ✓ Sample Answer: [Model answer or key points to include]

   QUALITY GUIDELINES:
   - Easy: Basic facts and definitions, straightforward questions
   - Medium: Application of concepts, some analysis required
   - Hard: Complex scenarios, synthesis of multiple concepts, critical thinking

   Generate the quiz now:
   ```

   ![](./media/ex11-prompt-template.png)

1. Test the prompt action with sample inputs:

   | Parameter | Test Value |
   |-----------|------------|
   | Topic | "Microsoft 365 Copilot" |
   | QuestionCount | 5 |
   | QuestionType | "multiple choice" |
   | DifficultyLevel | "medium" |

   ![](./media/ex11-test-prompt.png)

1. Review the generated output to ensure quality.

   ![](./media/ex11-prompt-output.png)

1. Save the prompt action.

   ![](./media/ex11-save-prompt.png)

### Task 4: Configure Quiz Customization Options

In this task, you will create the conversation flow that collects user preferences.

1. Navigate to **Topics** and create a new topic: `Generate Quiz`.

   ![](./media/ex11-create-topic.png)

1. Add trigger phrases:

   ```
   Create a quiz
   Generate quiz questions
   Make a quiz about
   I need a quiz on
   Build a quiz
   Quiz me on
   Create test questions
   ```

   ![](./media/ex11-trigger-phrases.png)

1. Build the conversation flow:

   **Step 1: Get Topic**

   Add a **Question** node:
   ```
   Great! Let's create a quiz. 📝

   What topic would you like the quiz to cover?

   You can enter any subject, like:
   - "Cloud Computing"
   - "Project Management"
   - "World Geography"
   - "Python Programming"
   ```

   Save response as variable: `QuizTopic`

   ![](./media/ex11-topic-question.png)

1. **Step 2: Get Question Count**

   Add a **Question** node:
   ```
   Excellent choice! How many questions would you like in your quiz?
   ```

   Options:
   - 5 questions (Quick quiz)
   - 10 questions (Standard)
   - 15 questions (Comprehensive)
   - 20 questions (Extended)

   Save response as variable: `QuestionCount`

   ![](./media/ex11-count-question.png)

1. **Step 3: Get Question Type**

   Add a **Question** node:
   ```
   What type of questions would you prefer?
   ```

   Options:
   - Multiple Choice (A, B, C, D options)
   - True/False (Statement verification)
   - Open-Ended (Written responses)
   - Mixed (Variety of types)

   Save response as variable: `QuestionType`

   ![](./media/ex11-type-question.png)

1. **Step 4: Get Difficulty Level**

   Add a **Question** node:
   ```
   What difficulty level should the quiz be?
   ```

   Options:
   - Easy (Basic facts and concepts)
   - Medium (Application and analysis)
   - Hard (Complex scenarios and critical thinking)

   Save response as variable: `DifficultyLevel`

   ![](./media/ex11-difficulty-question.png)

1. **Step 5: Confirm and Generate**

   Add a **Message** node:
   ```
   Perfect! Here's your quiz configuration:

   📚 Topic: {QuizTopic}
   🔢 Questions: {QuestionCount}
   📝 Type: {QuestionType}
   ⚡ Difficulty: {DifficultyLevel}

   Generating your quiz now... ⏳
   ```

   ![](./media/ex11-confirmation.png)

1. **Step 6: Call the Prompt Action**

   Add a **Call an action** node and select your `Generate Quiz Questions` prompt action.

   Map the variables:
   - Topic → QuizTopic
   - QuestionCount → (extract number from QuestionCount)
   - QuestionType → QuestionType
   - DifficultyLevel → DifficultyLevel

   ![](./media/ex11-call-action.png)

1. **Step 7: Display Results**

   Add a **Message** node to show the generated quiz:
   ```
   🎯 YOUR QUIZ IS READY! 🎯

   {GeneratedQuiz}

   ━━━━━━━━━━━━━━━━━━━━━

   Would you like me to:
   1. Generate more questions on this topic
   2. Create a quiz on a different topic
   3. Get just the answer key
   4. Export the quiz to a different format
   ```

   ![](./media/ex11-display-results.png)

1. Create follow-up handling:

   **For "Answer Key Only":**
   Create a prompt action that extracts just the answers:

   ```
   Extract only the correct answers from the following quiz and format them as an answer key:

   {GeneratedQuiz}

   Format:
   ANSWER KEY
   1. [Answer]
   2. [Answer]
   ...
   ```

   ![](./media/ex11-answer-key-prompt.png)

### Task 5: Test and Enhance the Quiz Generator

In this task, you will test the complete quiz generator and add enhancements.

1. Navigate to the **Test** panel.

   ![](./media/ex11-test-panel.png)

1. Test the complete flow:

   **Test 1: Multiple Choice Quiz**
   ```
   Create a quiz about Artificial Intelligence
   ```
   - Select: 10 questions
   - Select: Multiple Choice
   - Select: Medium difficulty

   ![](./media/ex11-test-mc.png)

1. Review the generated quiz for:
   - Accuracy of questions
   - Appropriate difficulty
   - Clear answer options
   - Correct answer marking

   ![](./media/ex11-review-quiz.png)

1. **Test 2: True/False Quiz**
   ```
   Make a quiz on Climate Change
   ```
   - Select: 5 questions
   - Select: True/False
   - Select: Easy difficulty

   ![](./media/ex11-test-tf.png)

1. **Test 3: Open-Ended Quiz**
   ```
   Create test questions about Leadership Skills
   ```
   - Select: 5 questions
   - Select: Open-Ended
   - Select: Hard difficulty

   ![](./media/ex11-test-open.png)

1. Add an **Export Quiz** feature. Create a new topic:

   Trigger phrases:
   ```
   Export my quiz
   Save the quiz
   Download quiz
   Send quiz to email
   ```

   ![](./media/ex11-export-triggers.png)

1. Create an export action using Power Automate:

   **Flow: Export Quiz to Email**
   - Input: Quiz content, User email
   - Format quiz as HTML or Word document
   - Send via email to user

   ![](./media/ex11-export-flow.png)

1. Add a **Quiz History** feature to save generated quizzes:

   ```
   Your quiz has been saved! You can access your previous quizzes by saying "Show my quiz history".

   Quiz ID: {QuizID}
   Created: {Timestamp}
   Topic: {QuizTopic}
   ```

   ![](./media/ex11-quiz-history.png)

1. Enhance with **Adaptive Difficulty**:

   Create a prompt that adjusts based on feedback:
   ```
   The user found the previous questions {UserFeedback}. 
   Generate 3 more questions about {Topic} with adjusted difficulty.
   
   If feedback is "too easy" → increase difficulty
   If feedback is "too hard" → decrease difficulty
   If feedback is "just right" → maintain difficulty
   ```

   ![](./media/ex11-adaptive-difficulty.png)

1. Test the enhancements:

   - Generate a quiz
   - Request answer key
   - Ask for more questions
   - Try exporting

   ![](./media/ex11-test-enhancements.png)

1. Publish the agent:

   - Click **Publish**
   - Enable Microsoft 365 Copilot channel
   - Configure access permissions

   ![](./media/ex11-publish.png)

1. Verify the agent in Microsoft 365 Copilot:

   - Navigate to Copilot
   - Find the Quiz Generator
   - Create a test quiz

   ![](./media/ex11-verify-copilot.png)

## Summary

In this exercise, you successfully:

- Learned about prompt actions and their capabilities for dynamic content generation
- Created a Quiz Generator agent with comprehensive customization options
- Built a powerful prompt action that generates quiz questions using AI
- Configured conversation flows to collect user preferences for:
  - Quiz topic
  - Number of questions
  - Question types (multiple choice, true/false, open-ended)
  - Difficulty levels
- Implemented follow-up features like answer key extraction and quiz export
- Tested the generator with various topics and configurations
- Published the agent to Microsoft 365 Copilot

Prompt actions enable agents to create dynamic, personalized content that would be impossible to pre-write, making them essential for use cases like content generation, assessment creation, and personalized assistance.

### Congratulations! You have successfully completed all exercises in this lab!

## Lab Complete Summary

Over the course of 3 days, you have:

**Day 1:**
- Explored Microsoft 365 Copilot Chat for event planning
- Created and configured custom agents in Copilot Chat
- Used pre-built agents to enhance productivity
- Empowered sales scenarios with Copilot
- Collaborated using Copilot Pages

**Day 2:**
- Built a comprehensive HR Agent with Microsoft Copilot Studio
- Created a declarative Poetic Agent using the Microsoft 365 Agents Toolkit
- Developed a SharePoint-based Career Guidance Agent

**Day 3:**
- Built autonomous agents for automated onboarding
- Implemented IT Support agent flows with intelligent routing
- Created a Quiz Generator using prompt actions

You now have the skills to deploy and customize Microsoft 365 Copilot and build powerful agents for your organization!
