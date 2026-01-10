# How to Build Your Book Cartridge (The "Surgical Swap" Method)

Building a Prompt-Native Application (PNA) is like assembling a LEGO kit. You don't need to write code; you just need to swap out the generic blocks for your specific content.

**⚠️ The Golden Rule:** Never press "Enter" inside a text block in the code. Line breaks break the file. Let the AI handle the formatting for you.

---

## Phase 1: Create the Skeleton
1. Open the file `templates/book-companion-template.json`.
2. Copy the entire content.
3. Paste it into a text editor (Notepad, TextEdit, VS Code). **Do not use Word.**
4. Save it as `my-book-app.json`.

You will see blocks that look like this:
```json
"chapter_1": {
  "_INSTRUCTION": "SELECT THIS ENTIRE BLOCK (from { to }) AND REPLACE",
  "status": "EMPTY_PLACEHOLDER"
},
