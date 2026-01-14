# GUIDE-REPLIT.md

## How to Build a Prompt-Native Application (PNA) with Replit Agent

A Prompt-Native Application (PNA) is a single, portable text file built on **Monolithic Context Architecture**. It bundles Content (a manuscript), Logic (executable tools), and Interface (navigation menus) into a self-contained package.

**Note on Technology:** This automated builder leverages the "Context Injection" techniques pioneered by the "Boot Kernel" community to create a "Walled Garden" for your content.

### THE SHORT VERSION:
1.  Drag & Drop your manuscript and the instructions file into Replit.
2.  Paste the command below.
3.  Answer the Agent's questions.

---

## STEP 1: PREPARATION

Before opening Replit, ensure you have these two files on your computer:

1.  **Your Manuscript:** (PDF, DOCX, or MD).
2.  **The System Instructions:** A file named `replit-agent-instructions.md` (This is the "Brain" you downloaded from this repository).

---

## STEP 2: THE KICKOFF (The Only Technical Step)

1.  Open Replit and click "New Agent" (or Create Project).
2.  Drag and Drop BOTH files (your manuscript + replit-agent-instructions.md) into the chat window.
3.  Paste the command below and hit Enter.

### Copy/Paste This Command:
```plaintext
I have attached my manuscript and the system instructions (replit-agent-instructions.md).

CRITICAL INSTRUCTION:
Do not act as a web developer. Read the attached replit-agent-instructions.md file immediately. Adopt the "PNA Architect" persona defined inside it.

Your goal is to generate Data Files (JSON), not an Application.

Please confirm you have read the instructions and are ready to begin Phase 1.
