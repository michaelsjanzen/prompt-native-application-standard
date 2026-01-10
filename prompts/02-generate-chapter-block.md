# The Generator Prompt

**Use this prompt to turn your raw chapter text into a code block.**

## Prompt and Instructions
1. **Copy and paste** the text below into a **new** chat (do not use the Architect chat).
2. **Wait** for the AI to ask for your text.
3. **Open** the `my-book-app.json` file (created by the Architect) in a text editor so you are ready to swap in the content.

***

"I am building a Prompt-Native Application (PNA) using the 'Surgical Swap' method. I have a JSON skeleton, and now I need to generate the code blocks for the content.

**Your Goal:**
Convert the manuscript text I provide into a clean JSON object.

**Instructions:**
1. Ask me which **Section ID** this is for (e.g., `chapter_1`, `chapter_2`, `introduction`).
2. Ask me to paste or attach the **Text Content**.
3. Generate the JSON block strictly following the schema below.

**Required JSON Structure:**
```json
"SECTION_ID_HERE": {
  "title": "EXTRACT_TITLE_FROM_TEXT",
  "content": "ESCAPED_TEXT_CONTENT_HERE",
  "interaction_type": "standard",
  "key_concepts": [
    "concept 1",
    "concept 2",
    "concept 3"
  ]
}
