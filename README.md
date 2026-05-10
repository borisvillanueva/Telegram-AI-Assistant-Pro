# Telegram AI Assistant Pro

AI-powered Telegram assistant built with n8n using modular AI agents, external tools, search orchestration, observability logging, and safety-controlled actions.

---

# Features

- Telegram AI assistant with conversational interface
- Modular subworkflow architecture
- AI-powered web search orchestration
- Wikipedia integration
- Hacker News integration
- SerpAPI live web search
- Voice transcription pipeline
- Google Sheets observability logging
- Email safety confirmation workflow
- Calendar integration
- Contact retrieval/storage support
- X/Twitter posting workflow support
- Memory-enabled conversations
- Human-readable AI summarization
- Safe tool orchestration design

---

# Architecture Overview

## Main Workflow

File:
`workflows/Telegram_AI_Assistant_Pro.json`

### Responsibilities

- Telegram message intake
- Voice vs text routing
- Input normalization
- AI orchestration
- Tool routing
- Logging and observability
- Telegram response delivery

---

## Search Subworkflow

File:
`workflows/TAAP_Search_Agent.json`

### Responsibilities

- Web search orchestration
- Multi-source retrieval
- News summarization
- Search result formatting
- Human-readable responses

---

# Workflow Screenshots

## 1. Main Workflow Architecture

Shows the full orchestration architecture of the Telegram AI assistant.

![Main Workflow](./screenshots/1-Main%20Workflow%20Architecture.png)

---

## 2. Telegram Conversation — Anthropic News Query

Example of live AI-powered news retrieval using the Search Agent.

![Anthropic News Query](./screenshots/2-Telegram%20Conversation%20Anthropic%20news%20query.png)

---

## 3. Telegram Conversation — Safe Email Handling

Example of controlled email safety behavior requiring recipient verification and confirmation before sending.

![Safe Email Handling](./screenshots/3-Telegram%20AI%20Conversation%20%E2%80%94%20Safe%20Email%20Handling.png)

---

## 4. Google Sheets Logging / Observability

Execution logging architecture used for observability and debugging.

![Google Sheets Logging](./screenshots/4-Google%20Sheets%20Logging%20-%20Observability.png)

---

## 5. Search Subworkflow Architecture

Dedicated modular AI search orchestration workflow.

![Search Workflow](./screenshots/5-Search%20Subworkflow%20Architecture.png)

---

# AI Safety Design

The assistant includes controlled behaviors for sensitive actions.

## Email Safety Workflow

The assistant never sends emails immediately.

Before sending emails:
1. Verifies recipient information
2. Requests missing email addresses
3. Drafts the email first
4. Shows the draft to the user
5. Requires explicit confirmation
6. Sends only after approval

---

# Tool Routing Rules

The assistant uses specialized tools depending on the task:

| Task | Tool |
|---|---|
| Live news | Search Agent |
| Weather | Search Agent |
| Web search | Search Agent |
| Calendar management | Calendar Tool |
| Contacts | Contact Agent |
| Email drafting | Email Agent |
| Social posting | X Posts Tool |

---

# Observability

The workflow includes execution logging using Google Sheets.

Logged data includes:
- Timestamp
- User message
- AI response
- Tool used
- Execution status

This improves:
- debugging
- traceability
- AI monitoring
- workflow validation

---

# Voice Mode

Voice pipeline architecture is included but currently disabled.

The architecture supports:
- Telegram voice ingestion
- audio transcription
- AI response generation
- voice response generation

Voice mode was intentionally disabled for stability and cost optimization.

---

# Technologies Used

- n8n
- OpenAI
- Telegram Bot API
- SerpAPI
- Wikipedia API
- Hacker News API
- Google Sheets API

---

# Project Structure

```text
Telegram-AI-Assistant-Pro/
│
├── README.md
│
├── workflows/
│   ├── Telegram_AI_Assistant_Pro.json
│   └── TAAP_Search_Agent.json
│
├── screenshots/
│   ├── 1-Main Workflow Architecture.png
│   ├── 2-Telegram Conversation Anthropic news query.png
│   ├── 3-Telegram AI Conversation — Safe Email Handling.png
│   ├── 4-Google Sheets Logging - Observability.png
│   └── 5-Search Subworkflow Architecture.png
│
└── assets/
    └── optional-future-assets
```

---

# Notes

- Credentials and internal deployment metadata were removed from exported workflows.
- The workflows are designed for educational and portfolio purposes.
- Some integrations require user-provided credentials before execution.

---

# Author

Boris Villanueva

GitHub:
https://github.com/borisvillanueva
