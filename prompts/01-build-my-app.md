# The Architect Prompt (v2.0)

**Use this prompt to generate your custom file skeleton automatically.**

**Note:** This prompt builds the **Skeleton only**. The full book text is not included in this step because AI models have limits on how much output they can produce at once. You will add your content chapter-by-chapter in the next phase.

## The Prompt
1. **Attach** your book manuscript (PDF, Word, MD, etc.).
2. **Attach** the `templates/book-companion-template.json` file from this repository.
3. **Copy and paste** the text below into the chat:

***

```text
I want to build a Prompt-Native Application (PNA) for this attached book. You are the PNA Architect.

**Phase 1: Analysis**
Please scan the attached **Manuscript** and extract the following metadata (If a value is not available enter N/A as a placeholder):
* **Title & Author**
* **Publisher** (if listed)
* **ISBNs/DOIs** (if listed)
* **Website/URL** (if listed)
* **User Goal:** Infer the primary learning objective from the Introduction.

**Phase 2: The Interview**
Review the extracted metadata and apply this logic:
* **If you are missing any metadata:** Do not ask me for it. Just use a placeholder (e.g. `INSERT_PUBLISHER_HERE`) in the final code.
* **If you found the metadata (or created placeholders):** Proceed immediately to the next step.

**The ONLY question you should ask me is about the Persona:**
* *Example:* 'I've analyzed [Book Title]. How should the AI behave? (e.g., A strict Drill Sergeant, a Socratic Tutor, or an Empathetic Coach?)'

**Phase 3: The Blueprint**
Once I answer the Persona question, generate the **Full JSON Skeleton** for me.
* **CRITICAL:** You must strictly follow the structure of the attached **JSON Template**. Do not invent new keys.
* **Structure Analysis:** Analyze the book's sections carefully. If a chapter is very large, break it into sub-sections (e.g., `ch1_part1`, `ch1_part2`) and inform me about this nuance.
* **Meta:** Fill in the `meta` block with the extracted data.
* **System Boot (Standardized):**
    * In the `system_boot` block, insert the Persona instructions we agreed upon.
    * **MANDATORY:** Add a `formatting_rule` that explicitly states: *"Always use bracketed keys (e.g., [A], [1]) for user options."*
    * **MANDATORY:** Add an `operational_rule` for slash commands: *"Support standard commands like `/quiz` (generate a question), `/toc` (table of contents), and `/help` (list commands)."*
* **Navigation (Standardized):**
    * Pre-fill the `standard_navigation` block with these exact options:
      1. `[M]` Main Menu
      2. `[N]` Next Section
      3. `[?]` Quiz Me
      4. `[/]` Commands
* **Content:** Create the `content_modules` block with empty placeholders corresponding to the chapters found in the manuscript (I will fill the content in later).

**Output Format:** Provide the complete JSON code block ready to be saved as `my-book-app.json`.
```
