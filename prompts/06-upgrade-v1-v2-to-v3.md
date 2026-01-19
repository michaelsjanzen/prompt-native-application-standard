# Upgrade Guide: v1.0/v2.0 -> v3.0.0

Use this prompt if you have an older PNA file and want to bring it up to the current Unified Standard.

**Usage:**
Paste your old JSON file after this prompt.

```text
**Your Goal:**
Refactor this legacy PNA JSON file to the v3.0.0 Unified Standard.

**The Upgrade Steps:**
1. **Meta:** Update version to "3.0.0".
2. **Reading Engine:** Insert the standard `reading_engine` block (Verbatim + Pagination).
3. **Navigation:**
   - Change "Continue" to `[N]` (Universal Next).
   - Ensure `[R]` and `[C]` keys are present.
4. **System Boot:**
   - Inject the "Initialization Handshake" protocol.
   - Add the "Printer vs. Writer" rule for Read Mode.
5. **Structure:** Ensure `curriculum_tracks` and `progress_tracking` blocks exist.

**The Old File:**
[PASTE OLD JSON HERE]

**Output:**
The fully refactored v3.0.0 JSON file.
```
