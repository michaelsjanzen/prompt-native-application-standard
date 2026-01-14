# How to Manually Build a Prompt-Native Application (PNA)
**(The "Surgical Swap" Method)**

You are about to build an **Active Document**.

Unlike a static PDF, a PNA is a file that processes information *for* the reader. This guide uses the "Surgical Swap" method—you don't need to write code; you just need to swap out generic blocks for your specific content.

**Historical Context:** This method is adapted from the "System Architect" and "Context Engineering" workflows used to build high-performance agent personas. We are applying those robust architectural principles to create educational and publishing tools.

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
1.  **Choose your Template:** Navigate to the `templates/` folder in this repository.
    * **Option A (`book-companion-template.json`):** Use this for a standard reference book (Simple).
    * **Option B (`course-companion-template.json`):** Use this if you want to create a graded course (Advanced).
2.  Copy the entire content of your chosen template.
3.  Paste it into your text editor.
4.  Save it as `my-book-app.json`.

## Phase 2: The Architect Interview
1.  Open **Prompt 1 (`01-build-my-app.md`)**.
2.  Start a chat with the AI (Claude/Gemini) and paste the prompt.
3.  Attach your manuscript AND your chosen template.
4.  The AI will interview you about your strategy.
5.  **The Output:** The AI will give you a "Skeleton" code block (Meta + System Boot). Replace the top half of your file with this new code.

## Phase 3: The Generator Loop (Content)
You will now convert your book chapters into "Code Blocks."
1.  Open **Prompt 2 (`02-generate-chapter-block.md`)**.
2.  **Important:** If you are building a Course, check your Syllabus in the Skeleton first.
3.  Paste the prompt into a new AI chat.
4.  Paste your chapter text.
5.  Copy the resulting JSON block.

## Phase 4: The Surgical Swap
1.  In your text editor, highlight the ENTIRE placeholder block for Chapter 1.
2.  Paste the code block you got from the AI.
3.  **The Comma Rule:**
    * If a chapter follows this one, ensure there is a comma after the closing curly brace `},`
    * If this is the LAST chapter, ensure there is NO comma `}`

## Phase 5: Validation (The Safety Net)
1.  Open **Prompt 4 (`04-validate-my-code.md`)**.
2.  Start a new chat and paste the prompt.
3.  Attach your full `my-book-app.json` file.
4.  The AI will check for syntax errors.
