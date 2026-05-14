---
name: knowledge-tutor
description: "Extracts technical knowledge from conversations into a personal Markdown knowledge base. Triggered by on_message (adaptive pre-scan) or manual keywords."
version: 1.1.0
author: niyunsheng
homepage: https://github.com/niyunsheng/knowledge-tutor
license: MIT
triggers:
  - on_message
  - manual
manual_trigger_keywords:
  - "帮我总结"
  - "提取知识"
  - "记录一下"
  - "save this"
  - "extract knowledge"
  - "summarize for knowledge base"
---

# Core Directives
1. **Language:** Internal reasoning and tool calls in English. All user-facing output and knowledge base content in the user's language.
2. **Focus on weak spots:** Only capture what the user didn't already know — concepts they struggled with, misconceptions they corrected, or non-obvious insights they discovered.
3. **Stay minimal:** Default to no extraction. Only act when there is genuine technical depth. A short, precise note is better than a long document.

---

## Knowledge Extraction (Triggers: `on_message`, `manual`)

Two entry points:
- **Automatic (`on_message`):** Pre-scan first, extract only when warranted.
- **Manual (`manual`):** User keyword triggers extraction directly, skipping pre-scan.

### Step 0: Entry Point Routing
- `manual` trigger → skip to Step 3.
- `on_message` trigger → proceed to Step 1.

### Step 1: Adaptive Pre-Scan (minimal tokens)
- Scan scope adapts to conversation length: 1-2 turns for short exchanges, broader for long multi-turn discussions.
- Stop if none of these are true:
  - The user learned a non-trivial technical concept or corrected a misconception
  - A complex bug was diagnosed with non-obvious root cause
  - A design/architecture decision was discussed with trade-offs
  - The user expressed confusion or asked for clarification on a technical point
- **Default is NO.** Most routine interactions should yield no extraction.
- Multiple extractions are allowed across a long conversation, as long as each covers a distinct topic (enforced by Step 2).

### Step 2: Overlap Check
- List existing files in the knowledge base directory and scan filenames.
- If the topic is already covered, briefly check the existing file (e.g., headings only).
- Only proceed if the new information is genuinely additive.

### Step 3: Extraction & Formatting
- Extract the core concept, context, and resolution.
- Keep it brief — one well-written paragraph plus 2-3 key takeaways.
- Format as structured Markdown in the user's conversational language.

### Step 4: File Operations
- Ensure the target directory exists (default: `~/knowledge_base/`, or a user-configured custom path).
- File naming: `<target_dir>/YYYY-MM-DD_TopicName.md`.
- If a similar file exists: merge only new insights, append `## Update History`.
- If not: create a new file.
