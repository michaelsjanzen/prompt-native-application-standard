# The Chapter Generator Prompt

**Use this prompt to convert your text into code.**

## The Prompt
Copy and paste the text below into your AI chat:

***

"I need to generate the JSON block for **Chapter [X]**.

**Input:** [Paste your Chapter Text Here]

**Instructions:**
1. Take the text I provided.
2. Format it into a valid JSON object with the key `"chapter_[X]"`.
3. **CRITICAL:** Escape all double quotes.
4. **CRITICAL:** Do NOT use a list of strings for the content. Use a single string with `\n\n` to represent paragraph breaks.
5. Output **only** the code block.

**Target Output Format:**
```json
"chapter_1": {
   "title": "The Beginning",
   "content": "Paragraph one text.\n\nParagraph two text.",
   "key_takeaways": ["Point 1", "Point 2"]
}
