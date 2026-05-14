# Knowledge Tutor

English | [简体中文](./README_zh.md)

## Overview

Using AI tools comes with a real concern: **AI dominates the thinking, and you become an accessory.** You ask, it reasons. You copy-paste, it creates. Over time, you stop thinking deeply and become dependent.

But using AI *well* can make you grow faster. **The key is reflection and review.** When you figure out something you didn't understand through conversation with AI, that's great — but if you don't consolidate it, next time you'll be just as lost. If you reflect and internalize it, you become genuinely stronger.

`knowledge-tutor` does exactly this: it captures the knowledge from your AI conversations into a personal Markdown knowledge base, focusing on your weak spots. Review on your own schedule — the learning pace is yours to control. **AI stays a powerful tool, but you remain in charge.**

## Features

- **Restrained Extraction:** Lightweight pre-scan judges whether extraction is worth doing. Defaults to "no" — only acts on genuine technical depth. Never duplicates existing notes.
- **Adaptive Scanning:** Scan scope adjusts to conversation length. Long multi-turn conversations can yield multiple extractions, each on a distinct topic.
- **Manual Trigger:** Say "帮我总结", "提取知识", "记录一下", "save this", or "extract knowledge" to trigger extraction on demand.
- **Adaptive Language:** All user-facing output and knowledge base content adapts to the language you use in conversation.

## Install

```bash
mkdir -p ~/.gemini/antigravity/skills/knowledge-tutor
curl -o ~/.gemini/antigravity/skills/knowledge-tutor/SKILL.md \
  https://raw.githubusercontent.com/niyunsheng/knowledge-tutor/main/SKILL.md
```

*(Notes are stored in `~/knowledge_base/` by default. Tell the agent if you prefer a different path.)*

## Usage

- **Simply Chat:** Have deep technical discussions. The skill adaptively detects and saves knowledge, avoiding redundancy.
- **Manual Trigger:** Say "extract knowledge" or "save this" to trigger extraction at any moment.
- **Self-Paced Review:** Browse `~/knowledge_base/` anytime. Set a cron job or calendar reminder to review on your own schedule.

## Universal Prompt Template

Don't want to install anything? Paste this into any chatbot. Replace the bracketed parts.

```
Generate knowledge base notes from our conversation.
My background: [your role, focus areas, e.g. AI Infra engineer working on training/inference systems, GPU clusters, MLOps].
Output: Markdown, in the same language as the conversation.
```

## License

[MIT](./LICENSE)
