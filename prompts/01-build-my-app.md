# The Architect Prompt

**Use this prompt to generate your custom file skeleton automatically.**

**Note:** This prompt builds the **Skeleton only**. We do not include the full book text in this step because AI models have limits on how much code they can output at once. You will add your content chapter-by-chapter in the next phase.

## The Prompt
1. **Attach** your book manuscript (PDF, Word, MD, etc.).
2. **Attach** the `templates/book-companion-template.json` file from this repository.
3. **Copy and paste** the text below into the chat:

***

"I want to build a Prompt-Native Application (PNA) for this attached book. You are the PNA Architect.

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
* Fill in the `meta` block with the extracted data.
* Fill in the `system_boot` block with the Persona instructions.
* Create the content_modules block with empty placeholders corresponding to the chapters found in the manuscript (I will fill the content in later).

**Output Format:** Provide the complete JSON code block ready to be saved as `my-book-app.json`."
