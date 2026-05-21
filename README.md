# AI Code Assistant — GitHub Models

An automated code review assistant powered by GitHub Models (GPT-4.1), running entirely inside GitHub Actions.

## Features

| Feature | Trigger |
|---------|---------|
| Automatic PR code review | Open or update a Pull Request |
| Answer coding questions | Comment `/ai your question` on any issue |

## Setup

1. **No secrets needed** — uses `GITHUB_TOKEN` automatically provided by GitHub Actions.
2. Push this repository to GitHub.
3. Make sure your repository has **Actions** enabled.

## Usage

### Automatic PR Review
Open a Pull Request → the bot posts a review comment automatically.

### Ask a Question
On any issue, comment:
```
/ai How do I fix a SQL injection vulnerability in Python?
```
The bot will reply with an AI-generated answer.

## Workflow Files

```
.github/
├── workflows/
│   └── code-assistant.yml   # Main workflow
└── prompts/
    └── code-review.prompt.yml  # Reusable prompt with evaluations
```

## Model Used
- **openai/gpt-4.1** via `https://models.github.ai/inference`
- No API key required — authenticated via `GITHUB_TOKEN` with `models: read` permission
