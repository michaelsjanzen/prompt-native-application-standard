# The Interaction Designer Prompt (v2.0)

**Use this prompt to program the UX, Navigation, and Personality of your AI.**

## The Prompt
1. **Attach** your `my-book-app.json` file.
2. **Copy and paste** the text below into the chat.

***

```text
I want to design the User Experience (UX) and Navigation for my Prompt-Native Application (PNA). You are the Interaction Designer and Strategist.

**Your Goal:**
Collaborate with me to design the 'Soul' (Persona), the 'Home Screen' (Welcome Message), and the 'Learning Strategy' (Curriculum).

**The Workflow:**
We will do this in 3 steps. Do not skip ahead.

**Step 1: Analyze the File**
1.  **Read the attached JSON file.**
2.  **Identify the Template:** Check if the file contains a `curriculum_tracks` block.
    * If **YES**: You will act as an **Instructional Designer** (focusing on syllabus, rubrics, and assignments).
    * If **NO**: You will act as a **UX Designer** (focusing on menus and reading flow).

**Step 2: The Strategy Session**
Ask me these questions (one by one or grouped) to define our strategy:

1.  **The Voice:** How should the AI sound? (e.g., 'A strict drill sergeant', 'A supportive peer', 'A wise mentor').
2.  **The Welcome Experience:** When the user first boots up the app, what should they see? (A start menu? A startling question? A promise of what they will learn?).
3.  **The Strategy (Dynamic):**
    * *If this is a Course:* "How do we differentiate the 'Crash Course' from the 'Mastery Course'? What constitutes an 'A-Grade' answer vs. a failure?"
    * *If this is a Standard Book:* "How should the user explore? Slash commands? Numbered lists? Open exploration?"
4.  **Guardrails:** What should the AI *refuse* to do?

**Step 3: The Text Prototype**
Based on my answers, draft the **plain text** version of the:
* **Persona Definition** (System Prompt instructions).
* **Welcome Message** (The 'Home' screen text).
* **Curriculum Logic** (If applicable: The specific tracks, grading criteria, and assignment prompts).
* *Wait for my feedback. We will iterate on this text until I am happy.*

**Step 4: The Code Implementation**
Once I approve the text, convert it into the specific JSON blocks I need to paste into my file.
* Provide the updated `system_boot` block.
* Provide the updated `curriculum_tracks` block (if applicable).
* **Instruction:** Tell me exactly where to paste these blocks (e.g., 'Replace your existing `system_boot` block with this code').
