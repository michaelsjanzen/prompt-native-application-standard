# Prompt-Native Application (PNA) Construction Guide

**Version:** 3.0.0 (Unified Standard)
**Philosophy:** Agile Symbiosis

## 1. What is a PNA?

A **Prompt-Native Application (PNA)** is a complete software application contained entirely within a single text file. It transforms a standard Large Language Model (LLM) from a passive chatbot into a structured, reliable, and interactive engine.

Unlike a standard prompt, a PNA v3.0.0 includes:
* **The Reading Engine:** Forces the AI to read verbatim (printer mode) rather than hallucinating summaries.
* **The Handshake Protocol:** Enforces transparency between the Model (Silicon) and the Persona (Carbon).
* **Universal Navigation:** A standardized UI (`[N] Next`, `[C] Course`, `[R] Read`) for consistent user experience.
* **Active Curriculum:** Built-in grading rubrics and learning tracks.

---

## 2. The Core Architecture (v3.0.0)

Your PNA is a single JSON file containing 7 distinct blocks. Understanding them helps you debug and design better apps.

| Block | Function | The "Agile Symbiosis" Logic |
| :--- | :--- | :--- |
| **`meta`** | Versioning | Tracks the file evolution. |
| **`system_boot`** | The Brain | Contains the **Handshake Protocol**. Defines the Persona and the "Carbon/Silicon" relationship. |
| **`standard_navigation`** | The Interface | Defines the buttons (`[N]`, `[M]`, `[C]`). Standardizes the User Experience. |
| **`reading_engine`** | The Printer | **New in v3.0:** Forces "Strict Verbatim" output and handles intelligent pagination (splitting long chapters). |
| **`curriculum_tracks`** | The Teacher | Contains the "Crash Course" and "Deep Dive" logic. If empty, the app acts as a standard book. |
| **`content_modules`** | The Library | The raw text of your book or course, stored in Markdown format. |
| **`progress_tracking`** | The Memory | Stores the user's current location, track, and grade. |

---

## 3. The Construction Workflow

We have provided a suite of "Builder Prompts" in the `/prompts/` folder to automate the coding process.

### Step 1: Build the Skeleton
**Goal:** Create the valid JSON structure (v3.0.0) without the heavy content.
1.  Open **`prompts/01-build-my-app.md`**.
2.  Copy the prompt block.
3.  Paste it into a capable LLM (Claude 3.5 Sonnet, GPT-4o, Gemini 1.5 Pro).
4.  **Result:** You will get a `json` template tailored to your specific book/course.

### Step 2: Ingest Content
**Goal:** Convert your raw text (Word, PDF, Text) into JSON modules.
1.  Open **`prompts/02-generate-chapter-block.md`**.
2.  Copy the prompt.
3.  Paste it into the LLM, followed by **one chapter** of your text.
4.  **Result:** The LLM will output a formatted `content_module` block.
5.  **Action:** Copy this block and paste it into the `content_modules: [ ... ]` array in your skeleton file.
6.  *Repeat for all chapters.*

### Step 3: Design the Persona
**Goal:** Tune the "System Boot" to sound like the author.
1.  Open **`prompts/03-design-interaction.md`**.
2.  Input your Author Name and Book Title.
3.  **Result:** A refined `system_boot` block including the **Initialization Handshake** (e.g., *"I am Claude, operating under the command of the Sun Tzŭ Persona"*).

### Step 4: Validate the Code
**Goal:** Ensure there are no syntax errors before launch.
1.  Open **`prompts/04-validate-my-code.md`**.
2.  Paste your *entire* JSON file after the prompt.
3.  **Result:** The LLM will act as a debugger, finding missing commas or structure errors.

### Step 5: Generate Documentation
**Goal:** Create a README for your users.
1.  Open **`prompts/05-generate-readme.md`**.
2.  **Result:** A professional Markdown file explaining your app's features to the world.

---

## 4. Best Practices & Troubleshooting

### The "Comma Trap"
JSON is strict. The most common error is a **missing comma** between blocks.
* **Wrong:**
    ```json
    "system_boot": { ... }
    "standard_navigation": { ... }
    ```
* **Right:**
    ```json
    "system_boot": { ... },  <-- COMMA HERE
    "standard_navigation": { ... }
    ```

### The "Context Window"
If your book is massive (>500 pages), do not try to paste the entire thing into one JSON file unless you are using a model with a huge context window (like Gemini 1.5 Pro or Claude 3 Opus).
* **Solution:** For standard models, break your book into 2-3 PNA files (e.g., "Volume 1", "Volume 2").

### The "Updates"
If you need to upgrade an old v1.0 or v2.0 file to this new standard:
* Use **`prompts/06-upgrade-v1-to-v3.md`**. It will automatically inject the `reading_engine` and update the navigation logic for you.

---

**Ready to build? Start with `prompts/01-build-my-app.md`.**
