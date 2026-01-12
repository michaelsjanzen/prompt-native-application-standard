# The Generator Prompt

**Use this prompt to turn your raw chapter text into a code block.** 

Note: The reduce errors caused by **context window limitations**, it is best to provide the original text one chapter at a time. If your text blocks (chapters) are very large use an AI with a large context window, like Gemini. If the AI has trouble building the blocks you may have discovered the AI's limits. In this case, the AI will attempt to chunk the content into smaller sections.

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
3. If the content for a content block I provide is very large, you may need to chunk the text into sub-sections and break the content block into separate chunks. If this happens, tell me if I need to do anything differently.
4. Add line breaks /n/n to the content where you see paragraphs breaks in the source content.
5. Generate the JSON block strictly following the schema below, but do not add additional enclosing brackets since this is a block of JSON code, not a complete JSON file.
6. If you believe this is the very last section of the content source, ask the me if this is true and STOP and wait for my response.
7. If this is the last section, do not include the comma at the end of the block to prevent JSON errors.
8. Include an explanation informating me that to maintain proper file syntax that final comma should be omitted.
9. Also inform me to look carefully through the file for line breaks, and explain why these will break the file.

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
