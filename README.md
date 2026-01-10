# The Prompt-Native Application (PNA) Standard

**The Open Standard for Distributing "Text-Based Software" with Educational Materials.**

## 🎯 Mission
The **Prompt-Native Application** format was developed to bridge the gap between static literature and active cognitive engagement. While Large Language Models (LLMs) provide the reasoning engine, authors and educators lack a standardized, portable method to distribute "interactive exercises" that travel with their content.

This repository establishes a **Publisher-Agnostic Standard** for bundling "Cognitive Cartridges" (JSON files) with books, courses, and training materials. It allows a reader to upload a single file and instantly transform a generic AI chat into a specialized tutor, simulator, or diagnostic tool specific to the author's methodology.

## 🤝 Prior Art & Acknowledgments
The PNA standard stands on the shoulders of massive innovation in "Structured Context" engineering. We gratefully acknowledge and align with the following architectural precedents:
* **Microsoft Declarative Agents** & **OpenAI System Fingerprints:** For pioneering the concept of "System Instructions" as a control layer.
* **Single-File Agents (SFA):** For establishing the utility of lightweight, portable scripts.
* **JSON Prompting:** For the industry-wide discovery that rigid syntax reduces hallucination.

**Differentiation:**
While the above standards focus on *Enterprise Automation*, the PNA Standard focuses on **Educational Encapsulation**—creating a "Walled Garden" where the model acts as a focused teacher or simulator using *only* the context provided in the file.

## 📚 Who is this for?
* **Non-Fiction Authors:** Include a `book_companion.json` that lets readers "chat with the book."
* **Corporate Trainers:** Distribute a "Sales Simulator" file for new hires to practice objection handling.
* **University Educators:** Share a "Socratic Tutor" file that forces the AI to ask students questions rather than giving answers.

## 🚀 Getting Started
1. **Download** the `templates/book-companion-template.json` file.
2. **Follow** the instructions in [GUIDE.md](GUIDE.md) to fill it with your content.
3. **Distribute** the file alongside your ebook or course material.

## License
This standard is released under the **MIT License**. You are free to build commercial PNAs using this format.
