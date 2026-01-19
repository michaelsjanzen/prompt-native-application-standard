# Step 4: Validate the JSON

Before launching, use this prompt to check for common syntax errors, especially the "Comma Trap."

**Usage:**
Copy your entire JSON file content and paste it after this prompt.

```text
**Your Goal:**
Audit the attached JSON file for syntax errors and v3.0.0 compliance.

**The Checklist:**
1. **Syntax:** Are all commas correct? (Especially between top-level blocks and after the `content_modules` array).
2. **Structure:** Does it contain the 7 mandatory blocks?
   - `meta`
   - `system_boot`
   - `standard_navigation`
   - `reading_engine`
   - `curriculum_tracks`
   - `content_modules`
   - `progress_tracking`
3. **Logic:**
   - Does `standard_navigation` use the `[N]` key?
   - Does `reading_engine` have the "Strict Verbatim" rule?
   - Do the IDs in `curriculum_tracks` match the IDs in `content_modules`?

**The Code:**
[PASTE YOUR FULL JSON CODE HERE]

**Output:**
Report "PASS" or "FAIL". If FAIL, list specific line numbers and the required fix.
```
