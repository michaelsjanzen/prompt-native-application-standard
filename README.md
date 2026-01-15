# The Prompt-Native Application (PNA) Standard

**The Open Standard for Distributing "Active Documents" and Interactive AI Editions.**

## Mission
The **Prompt-Native Application (PNA)** format standardizes the shift from **Static Documents** (which you read) to **Active Documents** (which you interact with).

While Large Language Models (LLMs) provide the reasoning engine, authors and educators have lacked a standardized, portable method to distribute "interactive exercises" and "structured curriculums" that travel with their content.

This repository establishes a **Publisher-Agnostic Standard** for bundling what the community calls a "**Cognitive Cartridge**" (JSON file) with books, courses, and training materials. It allows a reader to upload a single file and instantly transform a generic AI chat into an interactive book, specialized tutor, simulator, or diagnostic tool specific to the author's methodology.

## Prior Art & Acknowledgments
The PNA Standard is not a new invention; it is the productization of specific "Context Engineering" techniques. We explicitly acknowledge and stand on the shoulders of the following lineages:

* **Microsoft Declarative Agents & OpenAI System Fingerprints:** We credit the enterprise architects who pioneered the concept of "System Instructions" as a control layer, validating the need for structured constraints in generative AI.
* **The "Active Document" Theorists:** We align with the theory that the future of information is executable—transforming the author from a narrator into an active consultant.
* **The "System Architect" & "Context Engineering" Communities:** We credit the open-source experimenters who first established the utility of JSON-based "Operating Systems" and the "Cognitive Cartridge" metaphor for LLMs, proving that static files can effectively govern dynamic AI behavior.

## Who is this for?
* **Authors:** Include a `book_companion.json` alongside your ebook.
* **Corporate Trainers:** Distribute "Scenario Simulators" for sales objection handling or leadership role-play without needing a Learning Management System (LMS).
* **University Educators:** Share a "Socratic Tutor" file that forces the AI to ask students questions rather than giving answers.

## Use Case Examples
* **The Active Book:** Instead of a static digital file, the reader receives an executable file. This allows them to not only read the theory but immediately run the frameworks found in the book with their own data.
* **The Living Corporate Playbook:** A PNA replaces the static "Employee Handbook." Employees can query the document ("What is our policy on AI usage?") or run workflows ("Draft a project brief using our Q3 Strategic Pillars"), ensuring alignment with leadership’s intent.
* **The Intelligent Course Syllabus:** An educator packages their entire curriculum—readings, assignments, and rubrics—into a single file. The file acts as a 24/7 TA that quizzes students and guides them through homework using the educator’s specific methodology.

## Architecture: Monolithic Context Architecture (MCA)

The PNA standard utilizes a **Monolithic Context Architecture (MCA)**. Unlike traditional software that relies on a complex stack of databases, a PNA bundles four distinct layers into a single file:

1.  **The Kernel (System Boot):** Defines the Persona, boundaries, and formatting rules.
2.  **The Logic (Library):** Contains the executable tools, prompts, and calculators users can run (e.g., `[REVIEW]`, `[QUIZ]`, `[APPLY]`).
3.  **The Pedagogy (Curriculum):** Defines the learning tracks, grading rubrics, and assignments (Optional).
4.  **The Content (Knowledge Base):** The full manuscript or course material.

Technically, this is a form of **Bootstrapped CAG (Cache-Augmented Generation)**.
* **Traditional RAG:** Searches for relevant pages in a database ("Disk").
* **PNA (CAG):** "Pre-loads" the entire book into the AI's active RAM (Context Window). This allows the model to "think" with the whole book in mind.

### Comparative Analysis

| Feature | **PNA / CAG (This Standard)** | **Standard RAG (Vector Search)** | **GraphRAG (Knowledge Graph)** |
| :--- | :--- | :--- | :--- |
| **Core Concept** | **Memory:** The model loads the full "Monolithic Context" into active RAM. | **Search:** The model looks up keywords in a database. | **Map:** The model navigates a web of relationships. |
| **Retrieval** | **Instant:** No search step. The model "sees" the entire "knowledge base" simultaneously. | **Similarity:** Retrieves chunks that *sound* like the query. | **Relational:** Retrieves chunks that are *connected* to the query. |
| **Reasoning** | **Holistic:** Best for "synthesize the themes of the whole book." | **Fragmented:** Good for finding specific facts. | **Structured:** Excellent for complex multi-hop reasoning. |
| **Infrastructure** | **Zero-Dependency:** Runs in a chat window. No servers required. | **High-Dependency:** Requires hosting and vector databases. | **Heavy-Dependency:** Requires Graph DBs and pre-processing. |

## Limitations

**Context Window Volatility:**
This standard requires an LLM with a large context window (128k+ tokens). As of January 2026, it works flawlessly on frontier models like **Gemini 1.5 Pro** and **Claude 3.5 Sonnet**.

**The "Lost in the Middle" Phenomenon:**
In extremely long sessions, models may prioritize information at the beginning (System Prompt) and the end (Latest Query). *Mitigation: The PNA standard includes "re-grounding" instructions in every tool.*

## 🤖 Compatibility

*(Table updated: Jan 2026)*

| Model | Compatibility | Note |
| :--- | :--- | :--- |
| **Claude (Anthropic)** | ⭐⭐⭐⭐⭐ | Excellent. Handles massive files (200k+ tokens) easily. |
| **Gemini (Google)** | ⭐⭐⭐⭐⭐ | Excellent. Largest context window (1M+ tokens). |
| **ChatGPT (OpenAI)** | ⭐⭐⭐⭐ | Good, but very large books (>80k words) may hit context limits. |

## Getting Started

### Path 1: The Automated Way (Recommended)
Use the **Replit Agent** to build the file for you.
* **Start Here:** [**Automated Build Guide**](GUIDE-REPLIT.md)

### Path 2: The Manual Way
Build the file yourself using the "Surgical Swap" method.
* **Start Here:** [**Manual Build Guide**](GUIDE.md)

## License
This standard is released under the **MIT License**. You are free to build commercial PNAs using this format.
