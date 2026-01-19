# The Prompt-Native Application (PNA) Standard
**Version:** 3.0.0 (Unified Standard)

> "The goal is not to automate the human out of the loop, but to augment the human with silicon intent." — *Agile Symbiosis*

## 📚 What is a PNA?
A **Prompt-Native Application (PNA)** is a complete software application contained entirely within a single JSON text file.

When pasted into a Large Language Model (like Claude, ChatGPT, or Gemini), this file transforms the AI from a passive chatbot into a structured, reliable **Course Engine** or **Book Companion**.

**Key Features of v3.0.0:**
* **The Reading Engine:** Forces the AI to act as a "Verbatim Printer," preventing hallucinations and summaries.
* **Universal Navigation:** A standardized UI (`[N] Next`, `[C] Course`, `[R] Read`) for consistent user experience.
* **The Handshake Protocol:** Enforces transparency—the AI explicitly identifies itself as a model operating under a specific Persona.
* **Active Curriculum:** Supports "Crash Course" and "Deep Dive" learning tracks with built-in grading.

---

## 🚀 Quick Start
You don't need to write code. You just need to run our **Builder Prompts**.

1.  **Get the Prompts:** Go to the `/prompts/` folder.
2.  **Build the Skeleton:** Copy `01-build-my-app.md` into your favorite AI.
3.  **Add Your Content:** Use `02-generate-chapter-block.md` to convert your text.
4.  **Launch:** Paste the final JSON into a fresh chat.

👉 **[Read the Full Construction Guide](GUIDE.md)**

---

## 📂 The Repository Structure

### `/prompts/` (The Toolkit)
The actual prompts you paste into an LLM to build your app.
* `01-build-my-app.md` - Generates the JSON skeleton.
* `02-generate-chapter-block.md` - Converts raw text to JSON modules.
* `03-design-interaction.md` - Creates the Persona and Handshake.
* `04-validate-my-code.md` - Debugs your file.
* `05-generate-readme.md` - Build a README.
* `06-upgrade-v1-v2-to-v3.md` - Upgrade from older versions.

### `/examples/` (Case Studies)
Reference implementations to see the standard in action.
* `sun-tzu-the-art-of-war-pna-v3.json` 
* `homer-the-odyssey-pna-v3.json` 
* `taylor-scientific-management-pna-v3.json` 

### `/templates/`
* `pna-v3-unified-template.json` - The blank master file for starting from scratch.

---

## 🛠 Why "Prompt-Native"?
Traditional software requires a stack: Database, Backend, Frontend, Hosting.
A **PNA** requires zero infrastructure. It "lives" inside the context window of the AI session.

**The Philosophy: Agile Symbiosis**
We believe AI should not replace human judgment ("Carbon") but act as a force multiplier ("Silicon"). 

---

*Licensed under MIT. Open for contribution.*
