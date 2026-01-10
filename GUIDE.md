# How to Build Your Book Cartridge (The "Surgical Swap" Method)

Building a Prompt-Native Application (PNA) is like snapping together building blocks. You don't need to write code; you just need to swap out the generic blocks for your specific content.

**IMPORTANT:** Never press "Enter" inside a text block in the code. Line breaks break the file. Let the AI handle the formatting for you.

---

## Phase 1: Create the Skeleton
1. Open the file `templates/book-companion-template.json`.
2. Copy the entire content.
3. Paste it into a text editor (Notepad, TextEdit, BBEdit, VS Code). **Do not use Word.**
4. Save it as `my-book-app.json`.

You will see blocks that look like this:
```json
"chapter_1": {
  "_INSTRUCTION": "SELECT THIS ENTIRE BLOCK (from { to }) AND REPLACE",
  "status": "EMPTY_PLACEHOLDER"
},
```

## Phase 2: The Generator Loop
You will now use an AI (ChatGPT, Claude, etc.) to convert your book chapters into "Code Blocks."
1. Copy the Prompt: Go to prompts/02-generate-chapter-block.md in this repository and copy the text.
2. Paste into AI: Start a new chat with your preferred AI and paste the prompt.
3. Input Text: When asked, paste the text of your chapter.
4. Copy Output: The AI will give you a code block. Copy it.

##  Phase 3: The Surgical Swap
This is the only technical part. You must replace the Placeholder with the New Block.
1. In your text editor, highlight the ENTIRE placeholder block for Chapter 1.
  * Start highlighting at: The opening { (curly brace).
  * Stop highlighting at: The closing } (curly brace).
2. Paste the code block you got from the AI.

## The "Comma Danger" Zone
JSON is very strict about commas.
* If you are pasting a block in the MIDDLE of the list: It usually needs a comma after the closing },
* If you are pasting the LAST block: It must NOT have a comma after the closing }

Visual Check:
JSON
"chapter_1": { ... },  <-- COMMA HERE because Chapter 2 follows
"chapter_2": { ... }   <-- NO COMMA because it is the last item

## Phase 4: Validation (The Safety Net)
Before you share your file, you must check for bugs.
1. Copy your entire my-book-app.json file.
2. Open a new chat with an AI.
3. Paste the prompt from prompts/03-validate-my-code.md.
4. Paste your code.
5. If the AI says "Valid JSON," you are done! If it finds errors, it will give you a fixed version to copy.
