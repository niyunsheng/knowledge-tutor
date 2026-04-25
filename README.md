# Knowledge Tutor

English | [简体中文](./README_zh.md)

## The Philosophy: Don't Let AI Make You Dumber

Using AI tools comes with a real concern: **AI dominates the thinking, and you become an accessory.** You ask, it reasons. You copy-paste, it creates. Over time, you stop thinking deeply and become dependent — the human is no longer in charge.

But using AI *well* can actually make you grow faster. **The key is reflection and review.** You encounter a problem you don't understand, and through conversation with AI you figure it out — great. But if you don't consolidate that knowledge, next time you'll be just as lost. If you do reflect and internalize it, you become genuinely stronger.

That's exactly what this skill does: it automatically captures the knowledge from your AI conversations and actively quizzes you later to make sure you truly learned it. **AI stays a powerful tool — your personalized tutor — but you remain in charge, and you keep getting smarter.**

## Project Overview

`knowledge-tutor` seamlessly integrates into your daily chat interactions, acting as both an active listener and a proactive teacher. It builds a highly personalized Markdown knowledge base dedicated to your specific knowledge gaps. You can view, edit, and review these Markdown files directly at any time.

It performs two core functions:
1. **Passive Knowledge Extraction:** Monitors your chat sessions for valuable technical insights and quietly structures them into your personal Markdown knowledge base, focusing specifically on areas where you showed room for improvement.
2. **Active Spaced Repetition:** Utilizes scheduled tasks to review your knowledge base and proactively quizzes you using Socratic questioning, ensuring you actively recall and retain complex technical concepts.

## Features

- **Automated Note-Taking:** Extracts core concepts and solutions from your conversations without manual intervention, saving them in Markdown format.
- **Socratic Quizzing:** Tests your understanding through guided, open-ended questions rather than simple multiple-choice.
- **Adaptive Language:** The skill's internal logic and reasoning are driven by English for optimal LLM instruction adherence. However, **all user interactions and stored knowledge base notes will automatically adapt to the language you use during the conversation**.

## Install

### Google Antigravity

```bash
mkdir -p ~/.gemini/antigravity/skills/knowledge-tutor
curl -o ~/.gemini/antigravity/skills/knowledge-tutor/SKILL.md \
  https://raw.githubusercontent.com/niyunsheng/knowledge-tutor/main/SKILL.md
```

*(Note: Ensure the agent has necessary file system permissions to read and write to the target directory. By default, notes are stored in a `knowledge_base` folder. You can easily change this by simply telling the agent your preferred path in the chat!)*

## Usage

- **Simply Chat:** Have deep technical discussions with your agent. The skill will automatically detect and save the knowledge.
- **Daily Reviews:** The agent will automatically initiate a tutoring session daily at 15:00 (3:00 PM) to test your knowledge. *(You can customize this time by modifying the `cron_schedule` in `SKILL.md` or asking the agent to change it).*

## License

[MIT](./LICENSE)
