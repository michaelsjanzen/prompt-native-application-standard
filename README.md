# The Prompt-Native Application (PNA) Standard

**The Open Standard for Distributing Interactive AI with Books and Educational Materials.**

## Mission
The **Prompt-Native Application** format was developed to bridge the gap between static literature and active cognitive engagement. While Large Language Models (LLMs) provide the reasoning engine, authors and educators lack a standardized, portable method to distribute "interactive exercises" that travel with their content.

This repository establishes a **Publisher-Agnostic Standard** for bundling "Cognitive Cartridges" (JSON files) with books, courses, and training materials. It allows a reader to upload a single file and instantly transform a generic AI chat into an interactive book, specialized tutor, simulator, or diagnostic tool specific to the author's methodology.

## Prior Art & Acknowledgments
The PNA standard stands on the shoulders of massive innovation in "Structured Context" engineering. We gratefully acknowledge and align with the following architectural precedents:
* **Microsoft Declarative Agents** & **OpenAI System Fingerprints:** For pioneering the concept of "System Instructions" as a control layer.
* **Single-File Agents (SFA):** For establishing the utility of lightweight, portable scripts.
* **JSON Prompting:** For the industry-wide discovery that rigid syntax reduces hallucination.

**Differentiation:**
While the above standards focus on *Enterprise Automation*, the PNA Standard focuses on **Educational Encapsulation**—creating a "Walled Garden" where the model acts as a focused teacher or simulator, strictly grounded in the context provided in the file.

## Who is this for?
* **Authors:** Include a `book_companion.json` alongside your ebook or course that lets readers chat with the book, leverage tools (e.g. prompts) from the text, and explore the book's insights more deeply.
* **Corporate Trainers:** Distribute "Scenario Simulators" for sales objection handling, leadership role-play, or AI adoption workflows without needing a Learning Management System (LMS).
* **University Educators:** Share a "Socratic Tutor" file that forces the AI to ask students questions rather than giving answers.

## Origin & Backstory
The **Prompt-Native Application** standard was originally developed to publish *Agile Symbiosis*, a guide for knowledge workers adapting to the AI era.

Because the book's core thesis is about folding AI into human workflows, it was logical to use AI itself as the delivery mechanism for the content. The first "Book Cartridge" was built to prove that a static text could become an active partner in the reader's learning journey.

Once that architecture was stable, the code was reverse-engineered into this open-source standard. The goal is to allow any author to publish their own "interactive edition" without needing to reinvent the technical wheel.

## Getting Started
1. **Download** the `templates/book-companion-template.json` file.
2. **Follow** the instructions in [GUIDE.md](GUIDE.md) to fill it with your content.
3. **Distribute** the file alongside your ebook or course material.

## License
This standard is released under the **MIT License**. You are free to build commercial PNAs using this format.
