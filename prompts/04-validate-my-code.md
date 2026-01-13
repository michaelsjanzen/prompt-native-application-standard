# The Validator Prompt (v2.0)

**Use this prompt to check your file for errors before publishing.**

## The Prompt
1. **Attach** your `my-book-app.json` file to a **new** chat.
2. **Copy and paste** the text below into the chat.

***

```text
I have attached my Prompt-Native Application (PNA) JSON file. I need you to perform a Quality Assurance (QA) check.

**Your Goal:**
Validate that my JSON file is syntactically correct and, if applicable, that the Course Logic is sound.

**Instructions:**
1.  **Syntax Scan:** Check for standard JSON errors:
    * Missing commas (especially between chapters).
    * Extra trailing commas (at the end of lists/objects).
    * Unescaped double quotes inside text content.
    * Smart quotes (“ ”) that should be straight quotes (" ").

2.  **Reference Integrity (Crucial):**
    * **Scan the `curriculum_tracks` block** (if it exists).
    * Look at every `linked_content` or `assigned_reading` ID listed in the syllabus.
    * **Verify** that every one of those IDs exists as a key in the `content_modules` section.
    * *Report specifically if a Course Track points to a missing Chapter ID.*

3.  **Artifact Scan:** Flag any values that still say 'INSERT_HERE', 'EMPTY_PLACEHOLDER', or 'N/A'.

**Output:**
* If the file is **Valid**: Reply with 'PASSED: Your PNA file is valid and ready.'
* If there are **Errors**: List the specific errors (e.g., "Line 45: Missing Comma" or "Logic Error: Syllabus points to 'ch1' but content is 'chapter_1'").
* Provide the **corrected code block** for the broken section only.
