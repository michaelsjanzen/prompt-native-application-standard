# The Generator Prompt (v2.0)

**Use this prompt to turn your raw chapter text into a code block.**

## Beware Context Window Limitations
1. **Use Gemini 1.5 Pro or Claude 3.5 Sonnet**: For large books, these are the only models reliable enough for full-chapter transcription.
2. **Chunk the work:** Provide the original text one chapter at a time.
3. **Start new sessions:** If you see the AI getting stuck or hallucinating, you likely hit its limit. Start a fresh chat.

## Prompt and Instructions
1. **Copy and paste** the prompt text below into the same chat.
2. **Wait** for the AI to ask for your text.
3. **Open** your `my-book-app.json` file in a text editor so you are ready to swap in the content.

***

```text
I am building a Prompt-Native Application (PNA) using the 'Surgical Swap' method. I have a JSON skeleton, and now I need to generate the code blocks for the content.

**Your Goal:**
Convert the manuscript text I provide into a clean JSON object. Reproduce the content verbatim.

**Instructions:**
1. Ask me which **Section ID** this is for.
   * *Critical for Course Builders:* If I am using the `course-companion-template`, warn me that this ID must EXACTLY match the ID listed in my `curriculum_tracks` (e.g., if the syllabus says `chapter_1`, I must use `chapter_1` here, not `ch1`).
2. Ask me to paste or attach the **Text Content**.
3. **Verbatim Fidelity:**
   * Do not summarize.
   * If the text includes "Exercises," "Questions," or "Action Items" at the end, INLCUDE them fully. Do not truncate them.
4. **Formatting:**
   * Add `\n\n` for line breaks.
   * Escape all double quotes (`"`) inside the text.
5. Generate the JSON block strictly following the schema below.
6. **The Comma Rule:**
   * If this is NOT the last chapter, end the block with a comma (`,`).
   * If this IS the last chapter, DO NOT include a comma (to prevent JSON syntax errors).

**Required JSON Structure:**
"SECTION_ID_HERE": {
  "title": "EXTRACT_TITLE_FROM_TEXT",
  "content": "ESCAPED_TEXT_CONTENT_HERE",
  "interaction_type": "standard", // Use 'worksheet' if this is purely a form/quiz
  "key_concepts": [
    "concept 1",
    "concept 2",
    "concept 3"
  ]
},
