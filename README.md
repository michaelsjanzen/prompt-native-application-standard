# The Prompt-Native Application (PNA) Standard

**The Open Standard for Distributing Interactive AI Editions of Books and Educational Materials.**

## Mission
The **Prompt-Native Application** format was developed to bridge the gap between static literature and active cognitive engagement. While Large Language Models (LLMs) provide the reasoning engine, authors and educators lack a standardized, portable method to distribute "interactive exercises" that travel with their content.

This repository establishes a **Publisher-Agnostic Standard** for bundling what are essentially a "cognitive cartridge" (JSON file) with books, courses, and training materials. It allows a reader to upload a single file and instantly transform a generic AI chat into an interactive book, specialized tutor, simulator, or diagnostic tool specific to the author's methodology.

## Prior Art & Acknowledgments
The PNA standard stands on the shoulders of recent innovation in "Structured Context" engineering. We gratefully acknowledge and align with the following architectural precedents:
* **Microsoft Declarative Agents** & **OpenAI System Fingerprints:** For pioneering the concept of "System Instructions" as a control layer.
* **Single-File Agents (SFA):** For establishing the utility of lightweight, portable scripts.
* **JSON Prompting:** For the industry-wide discovery that rigid syntax reduces hallucination.

**Differentiation:**
While the above standards focus on *Enterprise Automation*, the PNA Standard focuses on **Educational Encapsulation**—creating a "Walled Garden" where the model acts as a focused teacher or simulator, strictly grounded in the context provided in the file.

## Who is this for?
* **Authors:** Include a `book_companion.json` alongside your ebook or course that lets readers chat with the book, leverage tools (e.g. prompts) from the text, and explore the book's insights more deeply.
* **Corporate Trainers:** Distribute "Scenario Simulators" for sales objection handling, leadership role-play, or AI adoption workflows without needing a Learning Management System (LMS).
* **University Educators:** Share a "Socratic Tutor" file that forces the AI to ask students questions rather than giving answers.

## Use Case Examples
* **The Interactive Book:** Instead of a static digital file, the reader receives an executable file. This allows them to not only read the theory from a book but immediately run the frameworks and tools found in the book with their own data within the an AI chat session. It transforms the author from a narrator into an active consultant.
* **The Living Corporate Playbook:** An organization evolves its static 50-page "Strategy PDF" or "Employee Handbook" with a PNA. Employees can query the document for specific answers ("What is our policy on AI usage?") or run specific workflows ("Help me draft a project brief using our Q3 Strategic Pillars") ensuring strict alignment with leadership’s intent. The "cognitive cartridge" also helps reduce risk by keeping the content inside one easily distributed file.
* **The Intelligent Course Syllabus:** An educator packages their entire semester’s curriculum—readings, assignments, and grading rubrics—into a single file. The file acts as a 24/7 tutor that can quiz students on specific chapters, guide them through homework assignments using the educator’s specific methodology, and provide feedback before they submit their work. The "walled-garden" also helps focus the students on the curriculum while learning to effectively use AI.

## Origin & Backstory
The **Prompt-Native Application** standard was originally developed to publish a single book *Agile Symbiosis: When AI Dissolves Your Job, Design a Better One*, by Michael Janzen. It's a guide for knowledge workers adapting to the Age of AI Synthesis.

Because the book's core thesis is about folding AI into human workflows, it was logical to use AI itself as a delivery mechanism for the content. The first "cognitive cartridge" was built to prove that a static text could become an active partner in the reader's learning journey.

Once that architecture was stable, Michael reverse-engineered the code into this open-source standard. The goal is to empower any author or educator to publish their own "cognitive cartridge" without needing to reinvent the technical wheel.

## Architecture

The PNA standard utilizes a **Monolithic Context Architecture (MCA)**. Unlike traditional software that relies on a complex stack of databases and servers, a PNA bundles the Logic (Tools), Content (Knowledge Base), and Interface (Menu System) into a single, portable JSON file.

Technically, this is a form of Bootstrapped CAG (Cache-Augmented Generation).
* **Traditional RAG:** Searches for relevant pages in a database and sends only those pages to the AI.
* **PNA (CAG):** "Pre-loads" the entire book into the AI's active RAM (Context Window). This allows the model to "think" with the whole book in mind, rather than just a few retrieved snippets.

### Comparative Analysis
How this standard compares to the three dominant AI architectures:

| Feature | **PNA / CAG (This Standard)** | **Standard RAG (Vector Search)** | **GraphRAG (Knowledge Graph)** |
| :--- | :--- | :--- | :--- |
| **Core Concept** | **Memory:** The model loads the full "Monolithic Context" into active RAM. | **Search:** The model looks up keywords in a database ("Disk"). | **Map:** The model navigates a web of relationships (Nodes/Edges). |
| **Retrieval** | **Instant:** No search step. The model "sees" the entire "knowledge base" simultaneously via attention. | **Similarity:** Retrieves chunks that *sound* like the query (Vector Math). | **Relational:** Retrieves chunks that are *connected* to the query. |
| **Reasoning** | **Holistic:** Best for "synthesize the themes of the whole book" or connecting distant ideas. | **Fragmented:** Good for finding specific facts, but misses the "big picture". | **Structured:** Excellent for complex multi-hop reasoning (e.g., "How does A affect B?"). |
| **Infrastructure** | **Zero-Dependency:** Runs in a chat window. No servers, APIs, or Python required. | **High-Dependency:** Requires hosting, vector databases (Pinecone/Milvus), and embedding models. | **Heavy-Dependency:** Requires Graph DBs (Neo4j) and complex pre-processing. |

## Limitations

While powerful, this architecture is constrained by the physics of Large Language Models:

**Context Window Volatility:**
This standard requires an LLM with a large context window (128k+ tokens). As of January 2026, it works flawlessly on frontier models like **Gemini 1.5 Pro** and **Claude 3.5 Sonnet**, but may struggle on smaller models (e.g., GPT-4o Mini), which can "forget" early chapters if the conversation exceeds their limit.

**The "Lost in the Middle" Phenomenon:**
In extremely long sessions, models sometimes prioritize information at the very beginning (System Prompt) and the very end (Latest User Query), occasionally blurring details in the middle of the `knowledge_base`.
*Mitigation: The PNA standard includes "re-grounding" instructions in every tool to remind the model of its source data.*

**Ephemeral State:**
The "State Machine" is simulated within the chat session. If the user closes the chat window or starts a new thread, the "OS" shuts down and all user data is lost. It does not have a persistent database.

**Hallucination Risk:**
While the standard uses a "Walled Garden" instruction block to forbid outside knowledge, the underlying model can still occasionally hallucinate facts if the user explicitly pushes it off-rails.

## 🤖 Compatibility

This standard creates a generic JSON file (`.json`) compatible with major LLMs.

*(Table updated: Jan 2026)*

| Model | Compatibility | Note |
| :--- | :--- | :--- |
| **Claude (Anthropic)** | ⭐⭐⭐⭐⭐ | Excellent. Handles massive files (200k+ tokens) easily. |
| **Gemini (Google)** | ⭐⭐⭐⭐⭐ | Excellent. Largest context window (1M+ tokens). |
| **ChatGPT (OpenAI)** | ⭐⭐⭐⭐ | Good, but very large books (>80k words) may hit context limits. |
| **Local LLMs** | ⭐⭐⭐ | Depends on your local hardware constraints. |

## Getting Started

You can build a PNA in two ways. Choose the path that fits your workflow.

### Path 1: The Automated Way (Recommended)
Use the **Replit Agent** to build the file for you using the AI code tools at Replit.com. You upload your manuscript, and the AI Architect interviews you, writes the code, and assembles the JSON file.
* **Best for:** Speed, non-coders, and standard books.
* **Start Here:** [**Automated Build Guide**](GUIDE-REPLIT.md)

### Path 2: The Manual Way
Build the file yourself using the "Surgical Swap" method. You generate components one by one using standard AI chats (ChatGPT/Claude) and paste them into a template.
* **Best for:** Precision, privacy (no uploading to Replit), or complex custom structures.
* **Start Here:** [**Manual Build Guide**](GUIDE.md)

## License
This standard is released under the **MIT License**. You are free to build commercial PNAs using this format.
