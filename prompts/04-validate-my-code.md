# The Validator Prompt

**Use this prompt to check your file for errors before publishing.**

## The Prompt
1. **Attach** your `my-book-app.json` file to a **new** chat (or copy/paste the code if you cannot attach).
2. **Copy and paste** the text below into the chat.

***

"I have attached my Prompt-Native Application (PNA) JSON file. I need you to perform a Quality Assurance (QA) check.

**Your Goal:**
Validate that my JSON file is syntactically correct and ready for distribution.

**Instructions:**
1.  **Rigorous Scan:** Check for the following errors:
    * **JSON Syntax:** Missing commas, extra commas (especially at the end of lists), and unescaped characters.
    * **Structure:** Ensure the `content_modules` block is properly formatted.
    * **Leftover Artifacts:** Flag any values that still say 'INSERT_HERE', 'EMPTY_PLACEHOLDER', or generic 'chapter_x' keys that were not updated.

**Output:**
* If the file is **Valid**: Reply with '✅ PASSED: Your PNA file is valid and ready.'
* If there are **Errors**: List the specific line numbers and errors, then provide the **corrected code block** for the broken section only."
