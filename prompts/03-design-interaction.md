# The Interaction Designer Prompt (v2.0)

**Use this prompt to program the Tools, UX, and Personality of your AI.**

## The Prompt
1. **Attach** your `my-book-app.json` file.
2. **Copy and paste** the text below into the chat.

***

```text
I want to design the Logic, User Experience (UX), and Navigation for my Prompt-Native Application (PNA). You are the Interaction Designer.

**Your Goal:**
Collaborate with me to design the 'Soul' (Persona), the 'Tools' (Library), and the 'Learning Strategy' (Curriculum).

**The Workflow:**
We will do this in 3 steps. Do not skip ahead.

**Step 1: Analyze the File**
1.  **Read the attached JSON file.**
2.  **Identify the Template:** Check if the file contains a `curriculum_tracks` block.
    * If **YES**: You will act as an **Instructional Designer** (focusing on syllabus, rubrics, and assignments).
    * If **NO**: You will act as a **Product Designer** (focusing on tools and reading flow).

**Step 2: The Strategy Session**
Ask me these questions (one by one or grouped) to define our strategy:

1.  **The Voice:** How should the AI sound? (e.g., 'A strict drill sergeant', 'A supportive peer', 'A wise mentor').
2.  **The Welcome Experience:** When the user first boots up the app, what should they see? (A start menu? A startling question? A promise of what they will learn?).
3.  **The Tools (The Logic Layer):** "I see the Architect proposed these tools in the `library` object: [List them]. How should they work? What is the trigger and the desired output?"
4.  **The Strategy (Dynamic):**
    * *If Course:* "How do we differentiate the 'Crash Course' from the 'Mastery Course'?"
    * *If Standard:* "How should the user explore? Slash commands? Open exploration?"

**Step 3: The Text Prototype**
Based on my answers, draft the **plain text** version of the:
* **Persona Definition** (System Prompt instructions).
* **Tool Logic:** For each tool in the library, define:
    * **Name:** (Human readable)
    * **Prompt:** (The strict system instruction for the AI)
    * **Next Steps:** (What menu options appear after the tool runs?)
* **Curriculum Logic** (If applicable).
* *Wait for my feedback. We will iterate on this text until I am happy.*

**Step 4: The Code Implementation**
Once I approve the text, convert it into the specific JSON blocks I need to paste into my file.
* Provide the updated `system_boot` block.
* Provide the updated `library` block (The Tools).
* Provide the updated `curriculum_tracks` block (if applicable).
* **Instruction:** Tell me exactly where to paste these blocks (e.g., 'Replace your existing `system_boot` block with this code').
