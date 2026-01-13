# How to Manually Build a Prompt-Native Application (PNA)
**(The "Surgical Swap" Method)**

Building a Prompt-Native Application (PNA) is like snapping together building blocks. You don't need to write code; you just need to swap out the generic blocks for your specific content.

**IMPORTANT:** Never press "Enter" twice inside a text block in the code. Empty lines break the file. Let the AI handle the formatting for you.

### Why do we build it in pieces?
You might be tempted to ask the AI to "Just generate the whole app for my 50,000-word book at once." **Do not do this.**
1.  **The "Output Limit" Trap:** AIs can *read* massive books (Input), but can only *write* a small amount of code at a time (Output).
2.  **The "Black Box" Problem:** By pasting the blocks yourself, you learn the structure. This is crucial for debugging later.

## Pro Tips for Success

**1. Use a Code Editor, NOT a Word Processor**
* **Do not** use Microsoft Word.
* **Recommended:** Download [VS Code](https://code.visualstudio.com/) (Free) or use Sublime Text.

**2. Save Versions**
* Save a new file for each stage: `book-v1-skeleton.json`, `book-v2-content.json`, `book-v3-final.json`.

---

## Phase 1: Create the Skeleton
1. **Choose your Template:** Navigate to the `templates/` folder in this repository.
    * **Option A (`book-companion-template.json`):** Use this for a standard reference book (Simple).
    * **Option B (`course-companion-template.json`):** Use this if you want to create a graded course with a syllabus (Advanced).
2. Copy the entire content of your chosen template.
3. Paste it into your text editor.
4. Save it as `my-book-app.json`.

## Phase 2: The Architect Interview
1. Open **Prompt 1 (`01-build-my-app.md`)**.
2. Start a chat with the AI (Claude/Gemini) and paste the prompt.
3. Attach your manuscript AND your chosen template.
4. The AI will interview you about your strategy (e.g., "Do you want a Drill Sergeant Persona?").
5. **The Output:** The AI will give you a "Skeleton" code block (Meta + System Boot). Replace the top half of your file with this new code.

## Phase 3: The Generator Loop (Content)
You will now convert your book chapters into "Code Blocks."
1. Open **Prompt 2 (`02-generate-chapter-block.md`)**.
2. **Important:** If you are building a Course, check your Syllabus in the Skeleton first. If the syllabus says `"read": ["chapter_1"]`, you MUST tell the AI to generate the ID as `chapter_1`.
3. Paste the prompt into a new AI chat.
4. Paste your chapter text.
5. Copy the resulting JSON block.

## Phase 4: The Surgical Swap
1. In your text editor, highlight the ENTIRE placeholder block for Chapter 1.
2. Paste the code block you got from the AI.
3. **The Comma Rule:**
    * If a chapter follows this one, ensure there is a comma after the closing curly brace `},`
    * If this is the LAST chapter, ensure there is NO comma `}`

## Phase 5: Validation (The Safety Net)
1. Open **Prompt 4 (`04-validate-my-code.md`)**.
2. Start a new chat and paste the prompt.
3. Attach your full `my-book-app.json` file.
4. The AI will check for syntax errors and (if applicable) verify that your Course Syllabus links to valid chapters.

---

## Appendix: Upgrading a Legacy File (v1.0 to v2.0)
If you already have a working PNA file (v1.0) and want to add the Course/Curriculum layer without rebuilding the whole file:

1.  Open **Prompt 6 (`06-upgrade-v1-to-v2.md`)**.
2.  Paste the prompt into an AI chat and attach your existing `.json` file.
3.  The AI will analyze your content and draft the new `curriculum_tracks` block and an updated `system_boot`.
4.  **The Surgical Insert:**
    * Find the `standard_navigation` block in your file.
    * Paste the new `curriculum_tracks` block directly **after** it (and before `content_modules`).
    * *Remember to add a comma after the navigation block if one is missing!*
