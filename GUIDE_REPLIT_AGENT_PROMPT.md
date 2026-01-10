# Replit Agent: PNA Builder Guide

**Build interactive book companion files automatically using Replit Agent.**

---

## What This Does

Converts your book manuscript into a JSON file that readers can upload to Claude, ChatGPT, or Gemini to have interactive conversations with your book's content.

**Output:** 3 files
- `[book-name].json` - Interactive companion
- `README.md` - User instructions
- `LICENSE.txt` - Copyright terms

---

## Quick Start

1. Open the Replit project with the PNA Builder Agent
2. Upload your manuscript (PDF, Word, Markdown, or plain text)
3. Answer 3 interview questions about the AI's behavior
4. Download generated files
5. Test in your preferred LLM
6. Return to Replit with refinements if needed

---

## The Process

### Phase 1: Analysis (Automatic)
Agent scans your manuscript and extracts:
- Metadata (title, author, ISBN, publisher)
- Structure (chapter count, sections)
- Learning objectives

Confirms findings with you before proceeding.

### Phase 2: Interview (3 Questions)
**Q1: Persona** - How should the AI behave? (e.g., Socratic tutor, supportive coach, neutral guide)

**Q2: Formatting** - Any special rules? (e.g., pause at exercises, show progress indicators)

**Q3: Navigation** - Keep default shortcuts (M/N/?) or customize?

### Phase 3: Approval
Agent shows you plain text draft of:
- Persona definition
- Content delivery protocol (prevents AI from improvising)
- Formatting rules
- Navigation options

Reply "Approved" or request changes.

### Phase 4: Generation
Agent builds the complete JSON file with:
- Full manuscript text (no summarization)
- Proper paragraph breaks (`\n\n`)
- Metadata and navigation
- Content delivery safeguards

### Phase 5: Deliverables
Agent generates:
- JSON file (book companion)
- README (setup instructions for readers)
- LICENSE (usage terms)

All saved to `output/` directory.

---

## File Structure Generated

```json
{
  "meta": {
    "app_name": "Your Book Title",
    "version": "1.0",
    "author": "Your Name",
    "publisher": "Publisher Name",
    "identifiers": { "isbn_print": "...", "isbn_ebook": "..." },
    "website": "your-website.com"
  },
  "system_boot": {
    "persona_override": "AI personality + Content Delivery Protocol",
    "formatting_rules": "Output formatting instructions"
  },
  "standard_navigation": {
    "options": [
      { "key": "M", "label": "Main Menu", "action": "return_to_root" },
      { "key": "N", "label": "Next Section", "action": "advance_sequential" },
      { "key": "?", "label": "Quiz Me", "action": "trigger_random_question" }
    ]
  },
  "content_modules": {
    "chapter_1": {
      "title": "Chapter Title",
      "content": "Full text with \\n\\n for paragraphs",
      "interaction_type": "standard",
      "key_concepts": ["concept 1", "concept 2"]
    }
  }
}
```

---

## Critical Features

### Content Preservation
- Every word from manuscript preserved
- No summarization or paraphrasing
- Paragraph breaks maintained with `\n\n`

### AI Safeguards
Built-in Content Delivery Protocol prevents the AI from:
- Rewriting your content
- Improvising "better" versions
- Summarizing when asked to "read"

Ensures readers get your exact words, not an AI's interpretation.

### Navigation
Single-key shortcuts readers can use:
- M = Main Menu
- N = Next Section
- ? = Quiz Me
- (Plus any custom options you add)

---

## Incremental Build (Large Manuscripts)

If your book is very large (80,000+ words), the agent uses an incremental approach:

1. **Phase A:** Generate skeleton (metadata, navigation, empty content slots)
2. **Phase B:** Generate chapters in groups of 3-5 with full text
3. **Phase C:** You paste each group into the growing file
4. **Phase D:** Final validation and deliverables

This ensures every word makes it into the final file without hitting output limits.

---

## Testing Your File

After downloading:

1. Upload JSON to Claude/ChatGPT/Gemini
2. Paste activation command from README
3. Test these prompts:
   - "Read me the preface" (should get verbatim text)
   - "What's chapter 2 about?" (can discuss concepts)
   - "Show me chapter 5" (should get exact text, not summary)

If AI improvises or rewrites content, return to Replit for refinement.

---

## Refinement Loop

Found issues during testing?

1. Return to Replit Agent
2. Describe needed changes
3. Agent makes surgical edits
4. Downloads as v1.1, v1.2, etc.
5. Test again

Examples of refinements:
- "Make the persona friendlier"
- "Add a /definitions command"
- "Chapter 3 key concepts are wrong"

---

## Technical Specifications

**Supported Input Formats:**
- PDF (text-extractable)
- Microsoft Word (.docx)
- Markdown (.md)
- Plain text (.txt)

**Compatible LLMs:**
- Claude (Anthropic) - Excellent (200k+ tokens)
- Gemini (Google) - Excellent (1M+ tokens)
- ChatGPT (OpenAI) - Good (128k tokens, may limit very large books)

**Typical File Sizes:**
- 50,000-word book: ~300-400 KB JSON
- 80,000-word book: ~500-700 KB JSON

---

## Quality Checklist

Before distributing to readers, verify:

- [ ] Full manuscript text present (compare word counts)
- [ ] Paragraph breaks working (text not running together)
- [ ] All chapters included
- [ ] Appendices included (if applicable)
- [ ] Metadata accurate (title, author, ISBN)
- [ ] Content Delivery Protocol present in persona_override
- [ ] README has correct activation command
- [ ] LICENSE reflects your copyright preferences

---

## Troubleshooting

**"Agent built a web app instead of JSON"**
- The prompt explicitly prevents this in latest version
- If it happens, restart with fresh session

**"Content is summarized, not full text"**
- Agent should auto-detect and restart
- Check word count: JSON should match manuscript ±5%

**"Paragraph breaks missing"**
- Should not occur with current prompt
- Agent validates `\n\n` presence before delivery

**"Missing chapters"**
- Likely hit output limit
- Agent should use incremental build automatically
- If not, request it explicitly

---

## Comparison to Manual Method

| Aspect | Replit Agent | Manual (Surgical Swap) |
|--------|--------------|------------------------|
| Time | 10-20 minutes | 2-4 hours |
| Technical skill | None required | Moderate JSON knowledge |
| Error risk | Low (auto-validated) | High (manual paste errors) |
| Customization | Standard structure | Can modify architecture |
| Best for | Authors wanting simple distribution | Developers building custom UX |

---

## Distribution to Readers

Once you have validated files:

**Include all 3 files:**
- `[book-name].json`
- `README.md` (essential - has activation instructions)
- `LICENSE.txt`

**Distribution methods:**
- Email as attachment
- Download link on website
- Include with ebook purchase
- GitHub repository

**Reader workflow:**
1. Read README.md
2. Upload JSON to preferred LLM
3. Paste activation command
4. Start interacting with book

---

## Next Steps

1. **Prepare manuscript** - Ensure clean text export
2. **Open Replit Agent** - Load the PNA Builder project
3. **Upload manuscript** - Agent will guide you through
4. **Test thoroughly** - Verify before distributing
5. **Gather feedback** - Improve based on reader experience

---

## Support

- **PNA Standard:** [github.com/michaelsjanzen/pna-standard](https://github.com/michaelsjanzen/pna-standard)
- **Documentation:** See main repository README
- **Issues:** Report via GitHub Issues

---

*Version 1.0 - January 2026*
