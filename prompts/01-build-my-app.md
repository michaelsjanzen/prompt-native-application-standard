# Step 1: Build the PNA Skeleton

This prompt instructs the AI to generate the core JSON structure for your application using the **v3.0.0 Unified Standard**.

**Usage:**
1. Open a fresh chat with a capable LLM (Claude 3.5 Sonnet, GPT-4o, or Gemini 1.5 Pro).
2. Copy the prompt block below.
3. Paste it into the chat.

```text
You are an expert Application Architect specializing in "Prompt-Native Applications" (PNAs).

**Your Goal:**
Generate the skeletal JSON structure for a v3.0.0 PNA.

**The Architecture Constraints (v3.0.0 Standard):**
1. **Meta Block:** Must include `"pna_version": "3.0.0"`.
2. **System Boot:**
   - Must include the "Initialization Handshake": The AI must identify itself as a model (Silicon) operating under a specific Persona (Carbon).
   - Must include the "Printer Rule": When in [R] Read Mode, execute as a printer (verbatim), not a writer (summary).
3. **Standard Navigation:**
   - Use `[N]` as the "Universal Next" key (handles both pagination and chapter advancement).
   - Include `[R]` for Read Mode and `[C]` for Course Tracks.
4. **Reading Engine:** Include the `reading_engine` block with "Strict Verbatim" and "Intelligent Pagination" rules.
5. **Curriculum Tracks:** Include the `curriculum_tracks` block (set to `null` or empty structure if not yet defined).

**Output:**
Generate the full, valid JSON skeleton based on these constraints. Do not fill in the content modules yet.
```
