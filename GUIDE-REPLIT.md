# GUIDE_REPLIT.md

## How to Build a Prompt-Native Application (PNA) with Replit Agent

A Prompt-Native Application (PNA), is a single, portable text file built on Monolithic Context Architecture that bundles Content (a manuscript), Logic (executable tools), and Interface (navigation menus) into a self-contained package. It functions like a digital game cartridge: when uploaded to an LLM, it instantly transforms the general model into a specialized Operating System without requiring servers, installation, or code.


### THE SHORT VERSION:
1. Drag & Drop your manuscript and the instructions file into Replit.
2. Paste the command below.
3. Answer the Agent's questions.

---

## STEP 1: PREPARATION

Before opening Replit, ensure you have these two files on your computer:

1. **Your Manuscript:** (PDF, DOCX, or MD).
2. **The System Instructions:** A file named `replit-agent-instructions.md` (This is the "Brain" you downloaded from this repository from the folder named 'replit').

---

## STEP 2: THE KICKOFF (The Only Technical Step)

1. Open Replit and click "New Agent" (or Create Project).
2. Drag and Drop BOTH files (your manuscript + replit-agent-instructions.md) into the chat window.
3. Paste the command below and hit Enter.

### Copy/Paste This Command:
```plaintext
I have attached my manuscript and the system instructions (replit-agent-instructions.md).

CRITICAL INSTRUCTION:
Do not act as a web developer. Read the attached replit-agent-instructions.md file immediately. Adopt the "PNA Architect" persona defined inside it.

Your goal is to generate Data Files (JSON), not an Application.

Please confirm you have read the instructions and are ready to begin Phase 1.
```

---

## STEP 3: WHAT HAPPENS NEXT?

Once you hit Enter, the AI takes over. You do not need to manage the process; just follow the Agent's lead, and provide details when asked.

Here is a preview of the workflow the Agent will guide you through:

1. **The Analysis:** The Agent will read your book and show you a list of chapters it plans to build. Collaborate with the Agent to refine or clarify and when satisfied with the output, just say "Approved."
2. **The Interview:** The Agent will ask you 3-4 questions about the "Persona" (how the AI should behave) and the "Home Screen."
3. **The Build:** The Agent will generate the files. It might ask you to check the first one to ensure the formatting looks good.
4. **The Assembly:** The Agent will write a Python script to merge everything into a final file.
5. **The Review:** Finally, the Agent will show you a simple "Review Console" where you can review your PNA Book File, collaborate with the agent to refine, and once complete download your final `.json` file.

---

## Troubleshooting:

* If the Agent tries to build a website/app immediately, tell it: "STOP. Read the PNA_INSTRUCTIONS.md file again. You are building Data Files, not a Web App."
