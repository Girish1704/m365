# Exercise 11: Create a Quiz Generator Agent with Prompt Actions

## Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create a Quiz Generator agent in Microsoft Copilot Studio and implement a prompt action that generates educational quiz questions. Prompt actions are a powerful feature that allows you to define custom AI instructions with specific parameters, enabling highly tailored content generation.

By the end of this exercise, you will have a working prompt action that can generate multiple-choice quiz questions on any topic, with configurable difficulty levels and question counts.

## Exercise Objectives

In this exercise, you will complete the following tasks:

- Task 1: Create a Quiz Generator Agent
- Task 2: Create a Prompt Action for Quiz Generation
- Task 3: Configure Prompt Inputs and Parameters
- Task 4: Write the Prompt Instructions
- Task 5: Test the Prompt Action Directly

### Task 1: Create a Quiz Generator Agent

In this task, you will create a new agent specifically designed for generating educational quizzes.

1. In the VM, open **Microsoft Edge** browser and navigate to:

   ```
   https://copilotstudio.microsoft.com
   ```

   ![](./media/ex11-studio-url.png)

1. Sign in with your lab credentials if prompted:

   - Email/Username: <inject key="AzureAdUserEmail"></inject>
   - Password: <inject key="AzureAdUserPassword"></inject>

   ![](./media/ex11-signin.png)

1. On the Copilot Studio home page, click **+ Create** from the left navigation.

   ![](./media/ex11-create.png)

1. Click on **+ New Agent** to create a new agent.

   ![](./media/ex11-new-agent.png)

1. Click **Skip to configure** to skip the AI-assisted creation and configure manually.

   ![](./media/ex11-skip-configure.png)

1. Configure the agent details:

   | Field | Value |
   |-------|-------|
   | Name | `Quiz Generator` |
   | Description | `An intelligent agent that generates educational quiz questions on any topic with customizable difficulty levels` |
   | Instructions | (See below) |

   **Instructions:**
   ```
   You are a Quiz Generator assistant that helps educators, trainers, and learners create educational assessments.

   Your capabilities include:
   - Generating multiple-choice quiz questions on any topic
   - Supporting different difficulty levels (Easy, Medium, Hard)
   - Creating answer keys with explanations
   - Producing quizzes of varying lengths (1-10 questions)

   When interacting with users:
   - Be helpful and encouraging
   - Ask clarifying questions if the topic is too broad
   - Suggest related topics if appropriate
   - Ensure all generated content is accurate and educational
   ```

   ![](./media/ex11-agent-config.png)

1. Click **Create** to create the agent.

   ![](./media/ex11-create-agent.png)

1. Wait for the agent to be created. You will be redirected to the agent overview page.

   ![](./media/ex11-agent-created.png)

### Task 2: Create a Prompt Action for Quiz Generation

In this task, you will create a prompt action that defines how quiz questions are generated using AI.

1. In the agent editor, click on **Tools** in the left navigation panel.

   ![](./media/ex11-tools-nav.png)

1. Click **+ Add a tool**.

   ![](./media/ex11-add-tool.png)

1. In the **New tool** dialog, select **Prompt**.

   ![](./media/ex11-select-prompt.png)

   >**What is a Prompt?**
   >
   >Prompts apply AI to text, documents, or images to analyze, summarize, or transform them. You can create reusable, parameterized AI generation logic.

1. The **Custom prompt** editor will open. You'll see:

   - **Instructions** panel (left) - where you write your prompt
   - **Model** selector - defaults to GPT-4.1 mini
   - **Model response** panel (right) - shows test results
   - **+ Add content** button - to add inputs and knowledge
   - **Get started with Copilot** section - AI helper to create prompts

   ![](./media/ex11-prompt-editor.png)

1. First, let's rename the prompt. Click on the title **"Custom prompt [date/time]"** at the top and rename it to:

   ```
   Generate Quiz Questions
   ```

   ![](./media/ex11-rename-prompt.png)

### Task 3: Configure Prompt Inputs and Parameters

In this task, you will add input parameters that control quiz generation. The UI uses "/" to add inputs inline.

1. In the **Instructions** text area, you'll see the placeholder text:
   
   *"Use copilot to create your instructions or write it here. Use "/" to add inputs and knowledge"*

1. Click inside the **Instructions** area and type `/` (forward slash).

   ![](./media/ex11-slash-command.png)

1. A menu will appear with two sections:

   **Input:**
   | Option | Description |
   |--------|-------------|
   | **Text** | Text input variable |
   | **Image or document** | File/image input |
   | **Power Fx** | Formula-based input |

   **Knowledge:**
   | Option | Description |
   |--------|-------------|
   | **+ New connection** | Add a new data connection |
   | **Dataverse** | Connect to Dataverse tables |

   ![](./media/ex11-slash-menu.png)

1. Select **Text** under the Input section to create the first parameter.

   ![](./media/ex11-select-text.png)

1. A text input field will be added. Configure it:

   | Field | Value |
   |-------|-------|
   | Name | `Topic` |
   | Description | `The subject or topic for quiz questions (e.g., Solar System, Python Programming)` |

   ![](./media/ex11-input-topic.png)

1. Press Enter or click outside to confirm. You'll see `{Topic}` appear in the instructions area.

1. Add a space after `{Topic}`, then type `/` again and select **Text**.

1. Configure the second input:

   | Field | Value |
   |-------|-------|
   | Name | `NumberOfQuestions` |
   | Description | `How many questions to generate (1-10)` |

   ![](./media/ex11-input-number.png)

1. Add a space, type `/` again and select **Text** for the third parameter.

1. Configure the third input:

   | Field | Value |
   |-------|-------|
   | Name | `DifficultyLevel` |
   | Description | `The difficulty level - Easy, Medium, or Hard` |

   ![](./media/ex11-input-difficulty.png)

1. You should now have three text inputs added: `{Topic}`, `{NumberOfQuestions}`, `{DifficultyLevel}`

   ![](./media/ex11-all-inputs.png)

### Task 4: Write the Prompt Instructions

In this task, you will write detailed instructions that guide the AI in generating high-quality quiz questions.

1. Clear the Instructions area and enter the following complete prompt (you can copy-paste this):

   ```
   You are an expert educational content creator specializing in creating quiz questions for learning and assessment purposes.

   Generate exactly {NumberOfQuestions} multiple choice quiz questions about the topic: {Topic}

   Difficulty Level: {DifficultyLevel}

   ## Difficulty Guidelines:

   **Easy:**
   - Basic concepts and definitions
   - Straightforward, commonly known facts
   - Clear correct answer with obviously incorrect distractors

   **Medium:**
   - Requires understanding and application of concepts
   - May involve comparing or contrasting ideas
   - Distractors are plausible but distinguishable

   **Hard:**
   - Complex scenarios requiring deep understanding
   - May involve analysis, synthesis, or evaluation
   - Distractors are very plausible, requiring careful thought

   ## Question Format Requirements:

   For each question, you MUST provide:
   1. Question number and clear question text
   2. Exactly four answer options labeled A, B, C, and D
   3. The correct answer letter
   4. A brief educational explanation (2-3 sentences)

   ## Quality Standards:

   - Questions must be clear, unambiguous, and grammatically correct
   - All four options must be plausible (no joke answers)
   - Each question should test a different aspect of the topic
   - Explanations should reinforce learning, not just state the answer
   - Avoid "All of the above" or "None of the above" options
   - Ensure factual accuracy

   ## Output Format:

   📝 **Quiz: {Topic}**
   📊 **Difficulty: {DifficultyLevel}**
   📋 **Questions: {NumberOfQuestions}**

   ---

   **Question 1:** [Question text here]

   A) [Option A]
   B) [Option B]
   C) [Option C]
   D) [Option D]

   ✅ **Correct Answer:** [Letter]
   💡 **Explanation:** [Educational explanation here]

   ---

   [Continue for all questions...]

   ---

   ## 📋 Answer Key Summary

   | Q# | Answer | Topic |
   |----|--------|-------|
   | 1 | [Letter] | [Brief topic] |
   | 2 | [Letter] | [Brief topic] |
   [Continue for all questions...]

   Now generate the quiz based on the provided parameters.
   ```

   ![](./media/ex11-full-instructions.png)

   >**Note:** The `{Topic}`, `{NumberOfQuestions}`, and `{DifficultyLevel}` placeholders should already be recognized as your inputs. If they appear as plain text, delete them and use `/` to re-add them as proper input variables.

1. Verify that the model is set to **GPT-4.1 mini** (or a similar model) in the Model dropdown.

   ![](./media/ex11-model-select.png)

### Task 5: Test the Prompt Action Directly

In this task, you will test the prompt directly in the editor to ensure it generates quality quiz content.

1. Click the **Test** button next to the Model selector.

   ![](./media/ex11-test-button.png)

1. A dialog will appear asking for input values. Enter the following test values:

   | Input | Test Value |
   |-------|------------|
   | Topic | `Solar System` |
   | NumberOfQuestions | `3` |
   | DifficultyLevel | `Easy` |

   ![](./media/ex11-test-inputs.png)

1. Click **Run** or **Test** to execute the prompt.

1. The **Model response** panel on the right will show the generated quiz:

   ![](./media/ex11-model-response.png)

   **Example Expected Output:**
   ```
   📝 Quiz: Solar System
   📊 Difficulty: Easy
   📋 Questions: 3

   ---

   Question 1: Which planet is known as the "Red Planet"?

   A) Venus
   B) Mars
   C) Jupiter
   D) Saturn

   ✅ Correct Answer: B
   💡 Explanation: Mars is called the Red Planet because of its reddish appearance, caused by iron oxide (rust) on its surface.

   ---
   [Additional questions...]
   ```

1. **Verify Quality:**

   Check the generated quiz for:
   - [ ] Correct number of questions (3)
   - [ ] Appropriate difficulty (Easy = basic facts)
   - [ ] All questions have exactly 4 options
   - [ ] Correct answers are accurate
   - [ ] Explanations are educational
   - [ ] Proper formatting with emojis

1. **Test with Different Parameters:**

   Click **Test** again and try different values:

   | Test Case | Topic | Questions | Difficulty |
   |-----------|-------|-----------|------------|
   | Test 2 | Microsoft 365 | 5 | Medium |
   | Test 3 | Machine Learning | 3 | Hard |

   ![](./media/ex11-additional-tests.png)

1. If the output quality needs improvement, modify the instructions and test again.

1. Once satisfied with the results, click **Save** in the bottom-right corner.

   ![](./media/ex11-save-prompt.png)

1. You will be returned to the Tools list. Your **Generate Quiz Questions** prompt should now appear in the list.

   ![](./media/ex11-prompt-saved.png)

## Summary

In this exercise, you created a Quiz Generator agent and implemented a prompt action for generating educational quiz questions. You learned how to:

- Create a specialized agent for educational content generation
- Configure prompt actions with multiple input parameters
- Write detailed prompt instructions that guide AI output
- Use variable placeholders (`{{Variable}}`) in prompts
- Define structured output formats for consistent results
- Test prompt actions directly before integrating into topics

In the next exercise, you will build a conversational topic that integrates this prompt action, allowing users to interactively generate quizzes through a guided conversation flow.

### You have successfully completed this exercise. Click on Next to proceed to the next exercise.
