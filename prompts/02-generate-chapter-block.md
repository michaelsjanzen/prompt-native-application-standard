# The Generator Prompt

**Use this prompt to turn your raw chapter text into a code block. If your content blocks (chapters) are large use an AI with a large context window, like Gemini.**

## Prompt and Instructions
1. **Copy and paste** the prompt text below into a the same chat.
2. **Wait** for the AI to ask for your text.
3. **Open** the `my-book-app.json` file (created by the Architect) in a text editor so you are ready to swap in the content.

***

"I am building a Prompt-Native Application (PNA) using the 'Surgical Swap' method. I have a JSON skeleton, and now I need to generate the code blocks for the content.

**Your Goal:**
Convert the manuscript text I provide into a clean JSON object. Reproduce the content verbatim, so that the provided content is perfectly rpreserved without any loss.

**Instructions:**
1. Ask me which **Section ID** this is for (e.g., `preface`, `forward`, `introduction`, `chapter_1`, `chapter_2`, `chapter_etc`, `afterword`, `appendix`, `biliography`).
2. Ask me to paste or attach the **Text Content** if I have not already made that available.
3. Add line breaks /n/n to the content where you see paragraphs breaks in the source content.
4. Generate the JSON block strictly following the schema below, but do not add additional enclosing brackets since this is a block of JSON code, not a complete JSON file.
5. If you believe this is the very last section of the content source, ask the human if this is true and STOP and wait for their response.
6. If this is the last section, do not include the comma at the end of the block.
7. Include an explanation to the human informating them that to maintain proper file syntax that final comma should be omitted.
8. Also inform them to look carefully through their file for line breaks, and explain why this will break the file.

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
},
