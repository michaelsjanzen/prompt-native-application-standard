# The Publisher Prompt

**Use this prompt to generate the "User Manual" for your readers.**

## The Prompt
1. **Attach** your final, validated `my-book-app.json` file.
2. **Copy and paste** the text below into the chat.

***

"I am ready to publish my Prompt-Native Application (PNA). I need you to write the `READ_ME_FIRST.txt` file that I will include in the download for my readers.

**Your Goal:**
Read the attached JSON file (specifically the `meta`, `system_boot`, and `content_modules`) and write a clear, exciting User Guide.

**The Guide must include:**
1.  **The Hook:** A 1-paragraph explanation of what this file is (e.g., 'This isn't just a file; it's an interactive version of [Book Title]...').
2.  **Compatibility:** A note that this works with Claude, ChatGPT, and Gemini.
3.  **Setup Instructions:** A simple 2-step guide:
    * Step 1: Upload this file.
    * Step 2: Paste the 'Activation Command'.
4.  **The Activation Command:** Create a clearly distinct code block with the standard startup prompt:
    * *'Please analyze the attached file. Initialize the [Persona Name] persona and say hello.'*
5.  **Starter Questions:** Extract 5 interesting topics or questions from the `content_modules` that the reader can ask immediately.

**Tone:** Professional, encouraging, and exciting.
**Format:** Markdown (optimized for a text file)."
