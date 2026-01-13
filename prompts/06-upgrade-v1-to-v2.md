# The Migration Assistant (v1.0 to v2.0)

**Use this prompt to upgrade an existing PNA file with Course capabilities.**

## The Prompt
1. **Attach** your existing `book-app-v1.json` file.
2. **Copy and paste** the text below into the chat.

***

```text
I have a v1.0 Prompt-Native Application (PNA) that acts as a standard book companion. I want to upgrade it to v2.0 by adding the "Curriculum Engine" (Course Tracks).

**Your Goal:**
Analyze my existing content and generate the code blocks needed to transform this from a "Passive Reference" into an "Active Course."

**The Workflow:**

**Step 1: Content Analysis**
* Scan the `content_modules` in my attached file.
* Propose 2 distinct "Learning Tracks" based on the actual book text:
    1.  **The Crash Course:** Which 2-3 chapters cover the 80/20 of the main idea?
    2.  **The Deep Dive:** What is the logical sequence for a full mastery course?
* *Stop and ask me to approve or refine these tracks.*

**Step 2: The Assessment Design**
* Once tracks are approved, draft 3 example "Assignments" for the Deep Dive.
* Create a "Grading Rubric" based on the specific themes of this book (e.g., "An 'A' grade requires citing the specific metaphor used in Chapter 4...").
* *Stop and ask me to approve the rubric.*

**Step 3: The Code Generation**
Generate the following JSON blocks for me to copy/paste. **Do NOT regenerate the content modules.**

1.  **The New `system_boot`:** Update my existing boot block to include the v2.0 "Pedagogy Rules" (e.g., "If in course mode, do not skip ahead").
2.  **The `standard_navigation`:** Update the menu to include `[C] Course Tracks`.
3.  **The `curriculum_tracks`:** Generate the full JSON block containing the Rubric, Crash Course, and Deep Dive tracks we agreed upon.

**Step 4: Installation Instructions**
Tell me exactly where to paste these blocks in my file to complete the upgrade.
