# The Publisher Prompt (v2.0)

**Use this prompt to generate the "User Manual" and License for your readers.**

## The Prompt
1. **Attach** your final, validated `my-book-app.json` file.
2. **Copy and paste** the text below into the chat.

***

```text
I am ready to publish my Prompt-Native Application (PNA). I need you to write the `READ_ME_FIRST.txt` file that I will include in the download for my readers.

**Your Goal:**
Read the attached JSON file (specifically `meta`, `system_boot`, `library`, and `content_modules`) and write a clear, exciting User Guide.

**The Guide must include:**
1.  **The Hook:** A 1-paragraph explanation of what this file is (e.g., 'This isn't just a file; it's an interactive version of [Book Title]...').
2.  **Compatibility:** A note that this works with Claude, ChatGPT, and Gemini.
3.  **Setup Instructions:** A simple 2-step guide:
    * Step 1: Upload this file.
    * Step 2: Paste the 'Activation Command'.
4.  **The Activation Command:** Create a clearly distinct code block with this exact text:
    * *'I have uploaded a book companion file. Please read the `system_boot` section, adopt the defined Persona, and begin the session.'*
5.  **The Toolbelt (Crucial):** Look at the `library` object in the JSON.
    * **List every tool found there** (e.g., `[REVIEW]`, `[QUIZ]`, `[APPLY]`).
    * For each tool, provide its Name and a 1-sentence description of what it does for the reader.
6.  **Starter Questions:** Extract 5 interesting topics from the `content_modules` that the reader can ask about immediately.
7.  **Legal & License:** Create a 'Copyright & Usage' section at the bottom.
    * Use the Author/Publisher name from the `meta` block.
    * **Default to:** 'Copyright [Year]. All Rights Reserved. For personal use only.' (Unless the file metadata explicitly says 'Creative Commons' or 'Open Source').

**Tone:** Professional, encouraging, and exciting.
**Format:** Markdown (optimized for a text file).
