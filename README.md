# ADK Blog Editor

An AI-powered blog editor built with [Google ADK](https://google.github.io/adk-docs/). It improves writing quality while preserving the author's original voice — not a grammar fixer, but a full editorial pass that sharpens clarity, structure, and impact.

Built for the [Visionary Vectors](https://the-visionary-vectors-website.vercel.app/) blog.

---

## What it does

The editor agent acts as an editor-in-chief. Give it a draft and it will:

- Preserve the author's conversational, insight-driven voice
- Improve clarity, structure, and flow
- Strengthen hooks and closing lines
- Remove redundancy without stripping personality
- Format content for readability
- Return an edited version with a short summary of changes

---

## How it works

The agent is built on Google ADK and uses a custom `editor-skills` skill set loaded from the `skills/` directory.

```
editor_agent/
├── agent.py              # Root agent definition
└── skills/
    └── editor-skills/
        ├── SKILL.md      # Skill instructions and editing steps
        └── references/
            └── example.md   # Before/after examples for hooks, clarity, explanations, insights, formatting, and anti-patterns
```

The agent uses `gemini-2.5-flash` and follows a structured 8-step editing process defined in `SKILL.md`.

---

## Setup

**Requirements:** Python 3.11+, [uv](https://docs.astral.sh/uv/)

```bash
git clone https://github.com/ayushisahu222/adk-blog-editor.git
cd adk-blog-editor
uv sync
```

Set your Gemini API key:

```bash
export GOOGLE_API_KEY=your_api_key_here
```

Run the agent in terminal:

```bash
uv run adk run editor_agent
```

Run the agent in web:
```bash
adk web
```

---

## Editing modes of the agent

| Mode | When to use |
|---|---|
| `light_edit` | Draft is strong, needs minor polish |
| `deep_edit` | Draft is messy, needs clarity and structure work |
| `publish_ready` | Full editorial pass before publishing |

---

## Author

Built by [Ayushi Sahu](https://github.com/ayushisahu222)
