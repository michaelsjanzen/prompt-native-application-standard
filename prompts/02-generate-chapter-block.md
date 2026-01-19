# Step 2: Generate Content Modules

This prompt helps you convert raw text (chapters, articles, transcripts) into the specific JSON format required by the PNA.

**Usage:**
1. Copy the text of ONE chapter or section you want to add.
2. Paste the prompt below into the AI, followed by your text.

```text
**Your Goal:**
Convert the raw text below into a single, valid PNA `content_module` JSON object.

**Constraints:**
1. **ID:** Create a short, unique ID (e.g., "ch1", "module_alpha").
2. **Title:** Use the exact title from the text.
3. **Content Field:**
   - You act as a TRANSCRIPTIONIST.
   - Preserve ALL original formatting using Markdown (bold `**`, italics `*`, headers `#`).
   - Escape all double quotes inside the text (`\"`).
   - Use `\n\n` for paragraph breaks.
   - DO NOT summarize. Keep every word.
4. **Metadata:** Extract 3-5 "key_concepts" from the text.

**The Raw Text:**
[PASTE YOUR TEXT HERE]
```
