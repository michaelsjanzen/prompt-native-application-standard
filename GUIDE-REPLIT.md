# How to Build a PNA with Replit Agent

**OBJECTIVE:**
Use the Replit Agent to convert a manuscript into a **Prompt-Native Application (PNA)**—a single JSON data file.

**CRITICAL WARNING:**
Replit is designed to build Web Apps. **We are building a Data File.** You must strictly follow the setup below to prevent the Agent from building a website you don't need.

---

## STEP 1: THE SETUP (Do this first)

1.  **Create a New Project** in Replit.
2.  **Upload Your Manuscript** (PDF, DOCX, or MD) to the root folder.
3.  **Create a New File** named `PNA_BUILDER_INSTRUCTIONS.md`.
4.  **Paste** the content of the "PNA Master Instructions" into that file.

---

## STEP 2: THE WAKE-UP COMMAND

**Copy and paste this EXACT text into the Replit Agent chat window.**

> "I have uploaded my manuscript and a file called `PNA_BUILDER_INSTRUCTIONS.md`.
>
> **CRITICAL INSTRUCTION:**
> Do not act as a web developer. Read the `PNA_BUILDER_INSTRUCTIONS.md` file immediately. Adopt the **PNA Architect** persona defined inside it.
>
> Your goal is to generate Data Files (JSON), not an Application.
>
> Please confirm you have read the instructions and are ready to begin **Phase 1: The Architect**."

---

## STEP 3: THE PROCESS OVERVIEW

Once the Agent accepts the command, it will guide you through these 6 phases.

### Phase 1: The Architect (Analysis)
* **What happens:** The Agent scans your book and proposes a "File Manifest" (a list of chapters to build).
* **Your Job:** Review the list. Ensure every chapter and appendix is listed. If something is missing, tell it: *"You missed Appendix B. Please add it."*

### Phase 2: The Interaction Designer (Interview)
* **What happens:** The Agent asks you about the "Soul" of the book (Persona) and how the "Home Screen" should look.
* **Your Job:** Answer the questions. Decide if your Appendices should be interactive tools (e.g., `/tool_name`) or just text.

### Phase 3: The Generator (Transcription)
* **What happens:** The Agent writes JSON files to the `pna_components/` folder.
* **Your Job:**
    * **Verify Batch 1:** It will stop after Chapter 1. Open the file `pna_components/chapters/01_....json`. Check that the text is **verbatim** and paragraph breaks are `\n\n`.
    * **Approve:** If it looks good, say *"Approved. Generate the rest."*

### Phase 4: The Assembler (Python Script)
* **What happens:** The Agent writes a Python script (`build_pna.py`) to merge the components into one valid file.
* **Your Job:** Watch it run. It should output a file in the `deliverables/` folder.

### Phase 5: The Publisher (Docs)
* **What happens:** The Agent generates a `README.md` and `LICENSE.txt`.
* **Your Job:** Review the README to ensure the "Activation Command" is clear.

### Phase 6: The Reviewer (Verification)
* **What happens:** The Agent builds a simple HTML viewer so you can check your work.
* **Your Job:** Click "Open in New Tab" to see the viewer.
    * **Download** the final `.json` file.
    * **Test** it by uploading it to Claude or ChatGPT.

---

## TROUBLESHOOTING

**If the Agent starts writing HTML/React code early:**
* **Say:** "STOP. You are ignoring the `PNA_BUILDER_INSTRUCTIONS.md`. You are a Data Architect, not a Web Developer. Delete the web code and return to Phase 1."

**If the Agent summarizes your text:**
* **Say:** "STOP. You are summarizing. I need verbatim transcription. Please re-read the 'Generator Logic' in the instructions file."

**If the JSON file is broken/invalid:**
* **Say:** "Do not try to fix the JSON manually. Update the `build_pna.py` script to handle the encoding error and run the script again."
