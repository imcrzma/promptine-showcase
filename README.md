# Promptine — AI Automation Systems

> **Smart. Simple. Reliable.**  
> أنظمة أتمتة بالذكاء الاصطناعي للأعمال الناطقة بالعربية

Promptine builds AI automation for Arabic-speaking businesses: automated messaging, instant replies, lead capture and booking flows for clinics, car dealerships, salons and more.

This repository is a **showcase** of how our systems are designed. It documents architecture and design decisions only. Workflow exports, prompts and client configuration are **not** published here.

---

## Systems

| System | What it does | Docs |
|---|---|---|
| **AI Customer Service** | Multi-tenant Telegram assistant with persistent memory, a verified knowledge base, human handoff and automatic lead capture | [docs/customer-service.md](docs/customer-service.md) |
| **Error Monitoring** | Central error workflow that logs every failure and alerts the admin with a suggested fix | [docs/customer-service.md](docs/customer-service.md#error-monitoring) |
| **AI Content Radar** | Daily research agent that finds AI news and produces 10 ranked, bilingual (EN/AR) content ideas | [docs/content-radar.md](docs/content-radar.md) |

## Stack

`n8n` · `LLMs via OpenRouter` · `Claude API` · `Supabase` · `WhatsApp Business API` · `Telegram Bot API` · `Google Sheets`

## Design principles

- **Never invent facts.** Business answers come only from a verified knowledge base; if it is not there, the assistant escalates to a human.
- **Humans stay in control.** Complaints, sensitive topics and bookings are handed to a person, and the bot stops replying until they take over.
- **Treat all input as untrusted.** Customer text, history and knowledge entries are handled as data, never as instructions.
- **Fail loudly, recover quietly.** Every workflow has fallbacks, retries and an error handler that reports what broke and how to fix it.
- **Built for Arabic first.** Natural dialect-friendly replies, bilingual output and RTL-aware content.

---

© 2026 Promptine. All rights reserved. See [LICENSE](LICENSE).
