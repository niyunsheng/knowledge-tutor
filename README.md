# OpenClaw Skill: Knowledge Tutor

English | [简体中文](./README_zh.md)

## The Philosophy: Don't Let AI Make You Dumber

As Large Language Models (LLMs) become increasingly powerful, there is a real risk of cognitive offloading—humans might become "dumber" because we simply rely on AI to think for us. However, it doesn't have to be this way. LLMs can act as our personalized learning tutors, specifically targeting our weaknesses and helping us grow.

By using this skill, your collaboration with the LLM transforms into a targeted knowledge-building process. It ensures your abilities continuously improve, turning the AI into a tool that sharpens your mind rather than dulling it.

## Project Overview

`openclaw-skill-knowledge-tutor` seamlessly integrates into your daily chat interactions, acting as both an active listener and a proactive teacher. It builds a highly personalized Markdown knowledge base dedicated to your specific knowledge gaps. You can view, edit, and review these Markdown files directly at any time.

It performs two core functions:
1. **Passive Knowledge Extraction:** Monitors your chat sessions for valuable technical insights and quietly structures them into your personal Markdown knowledge base, focusing specifically on areas where you showed room for improvement.
2. **Active Spaced Repetition:** Utilizes scheduled tasks to review your knowledge base and proactively quizzes you using Socratic questioning, ensuring you actively recall and retain complex technical concepts.

## Features

- **Automated Note-Taking:** Extracts core concepts and solutions from your conversations without manual intervention, saving them in Markdown format.
- **Socratic Quizzing:** Tests your understanding through guided, open-ended questions rather than simple multiple-choice.
- **Adaptive Language:** The skill's internal logic and reasoning are driven by English for optimal LLM instruction adherence. However, **all user interactions and stored knowledge base notes will automatically adapt to the language you use during the conversation**.

## Installation

The easiest way to install this skill is to simply ask your OpenClaw agent to do it for you. Send the following message in your chat:

```text
please install the skill from https://github.com/niyunsheng/openclaw-skill-knowledge-tutor
```

Alternatively, you can manually clone this repository into your OpenClaw skills directory.

*(Note: Ensure the OpenClaw agent has necessary file system permissions to read and write to the target directory. By default, notes are stored in a `knowledge_base` folder next to your OpenClaw `memory` directory. You can easily change this by simply telling the agent your preferred path in the chat!)*

## Usage

- **Simply Chat:** Have deep technical discussions with your agent. The skill will automatically detect and save the knowledge.
- **Daily Reviews:** The agent will automatically initiate a tutoring session daily at 15:00 (3:00 PM) to test your knowledge. *(You can customize this time by modifying the `cron_schedule` in `SKILL.md` or asking the agent to change it).*
