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

**3. The "Intelligent Pagination" Rule**
* **Problem:** If a user asks the AI to "Read Chapter 1," and Chapter 1 is 5,000 words long, the AI will often cut off mid-sentence.
* **Solution:** In your instructions (or `library` tools), always add this rule: *"If text is long, proactively split it. Render Part 1, then STOP and ask the user if they want to proceed to Part 2."*

---

## Phase 1: Create the Skeleton
1.  **Choose your Template:** Navigate to the `templates/` folder in this repository.
    * **Option A (`book-companion-template.json`):** Use this for a standard reference book (Simple).
    * **Option B (`course-companion-template.json`):** Use this if you want to create a graded course (Advanced).
2.  Copy the entire content of your chosen template.
3.  Paste it into your text editor.
4.  Save it as `my-book-app.json`.

## Phase 2: The Architect Interview (System Boot)
1.  Open **Prompt 1 (`01-build-my-app.md`)**.
2.  Start a chat with the AI (Claude/Gemini) and paste the prompt.
3.  Attach your manuscript AND your chosen template.
4.  The AI will interview you about your strategy.
5.  **The Output:** The AI will give you a "Skeleton" code block (`meta` + `system_boot`). Replace the top half of your file with this new code.
    * *Tip: This is where you define your "Persona" (e.g., "Strict Tutor" or "Helpful Librarian").*

## Phase 3: The Generator Loop (Content)
You will now convert your book chapters into "Code Blocks."
1.  Open **Prompt 2 (`02-generate-chapter-block.md`)**.
2.  **Important:** If you are building a Course, check your Syllabus in the Skeleton first.
3.  Paste the prompt into a new AI chat.
4.  Paste your chapter text.
5.  Copy the resulting JSON block and paste it into `content_modules`.

## Phase 3.5: The Logic Layer (Building the Library)
**This is the differentiator.** This step turns your file from a "Book" into an "App."
The `library` object contains your **Tools**—the specific commands users can run.

**Examples of Tools:**
* `[REVIEW]`: Forces the AI to act as an impartial critic to review the book.
* `[APPLY]`: Takes a framework from Chapter 3 and applies it to the user's messy notes.
* `[QUIZ]`: Generates a scenario based on Chapter 5 and grades the user's response.

**How to Build Them:**
1.  Identify the 3-5 "Killer Apps" from your book (e.g., A Calculator, A Strategy Generator, A Diagnostic).
2.  Ask the AI: *"Write a JSON object for a tool called 'The Strategy Generator' that uses the rules from Chapter 4 to fix a user's problem."*
3.  Paste these objects into the `library` section of your JSON.
4.  *Advanced:* You can add `next_steps` to each tool to guide the user after the tool runs.

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
