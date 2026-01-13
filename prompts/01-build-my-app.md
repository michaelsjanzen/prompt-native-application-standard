# The Architect Prompt (v2.1)

**Use this prompt to generate your custom file skeleton automatically.**

**Note:** This prompt builds the **Skeleton only**. The full book text is not included in this step because AI models have limits on how much output they can produce at once. You will add your content chapter-by-chapter in the next phase.

## The Prompt
1. **Attach** your book manuscript (PDF, Word, MD, etc.).
2. **Attach** the JSON template you wish to use from the `templates/` folder:
   * Use `book-companion-template.json` for a standard reference tool (Simple).
   * Use `course-companion-template.json` for an active course with grading (Advanced).
3. **Copy and paste** the text below into the chat:

***

```text
I want to build a Prompt-Native Application (PNA) for this attached book. You are the PNA Architect.

**Phase 1: Analysis**
Please scan the attached **Manuscript** and extract the following metadata (If a value is not available enter N/A):
* **Title & Author**
* **Publisher & Links**
* **User Goal:** Infer the primary learning objective from the Introduction.
* **Pedagogy Scan:** Look for "Exercises," "Reflection Questions," or "Action Items" at the end of chapters. Note these for later.

**Phase 2: The Interview**
Review the extracted metadata and the attached **JSON Template**, then ask me:
1.  **The Strategy:** "I see you attached the [Standard/Course] template. Do you want to treat this strictly as a reference tool, or should I design a specific 'Learning Path' for the reader?"
2.  **The Persona:** "How should the AI behave? (e.g., A strict Drill Sergeant, a Socratic Tutor, or an Empathetic Coach?)"

**Phase 3: The Blueprint**
Once I answer, generate the **Full JSON Skeleton** for me.
* **CRITICAL:** You must strictly follow the keys of the attached **JSON Template**.
* **Meta:** Fill in the `meta` block with the extracted data.
* **System Boot:** Insert the Persona instructions we agreed upon.
    * **MANDATORY:** Add a `formatting_rule`: *"Always use bracketed keys (e.g., [A], [1]) for user options."*
* **Curriculum (If Course Template is used):**
    * **Tracks:** Create two tracks in `curriculum_tracks`:
        1.  `crash_course`: Link only to the Introduction and Conclusion chapters.
        2.  `mastery_course`: Link to all chapters sequentially.
    * **Rubric:** Generate a `grading_rubric` that rewards critical thinking and penalizes hallucinations.
    * **Assignments:** If you found "Exercises" in Phase 1, insert them into the `assignment` fields for the relevant modules.
* **Content:** Create the `content_modules` block with empty placeholders for every chapter found in the manuscript.

**Output Format:** Provide the complete JSON code block ready to be saved as `my-book-app.json`.
