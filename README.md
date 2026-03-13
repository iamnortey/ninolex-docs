# Ninolex

> Pronunciation infrastructure for AI voice applications.

[![Case Study](https://img.shields.io/badge/case%20study-read-blue)](https://github.com/iamnortey/portfolio/blob/main/case-studies/ninolex.md)
[![Open Dictionary](https://img.shields.io/badge/open%20source-ninolex--gh-green)](https://github.com/iamnortey/ninolex-gh)
[![Portfolio](https://img.shields.io/badge/portfolio-iamnortey-green)](https://github.com/iamnortey/portfolio)

---

## What It Does

Ninolex provides a cross-platform source of truth for how real-world entities should be pronounced in AI voice applications. TTS engines mispronounce brands, products, and names — Ninolex fixes that.

**Pronunciation Resolution Pipeline:** Text → Normalize → Resolve → Export

Entity registry with IPA phonemes, exportable to ElevenLabs, AWS Polly, and Vapi formats.

---

## The Problem

- TTS engines mispronounce brands: "BMW" becomes gibberish
- Product names are unpronounceable: "WH-1000XM5"
- Domain terminology is wrong: medical, legal, automotive terms
- Cultural names are consistently butchered

---

## Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | Next.js |
| **Backend** | Next.js API Routes, Modal |
| **Resolution** | CMUdict, Phonemizer |
| **Database** | Supabase |
| **Export** | ElevenLabs, AWS Polly, Vapi |

---

## Key Architecture Patterns

- **Two-tier resolution** — CMUdict primary, Phonemizer fallback
- **Alphanumeric expansion** — "WH-1000XM5" → "W H one thousand X M five"
- **Vertical pack architecture** — domain-specific packs (AutoLex, DineLex)
- **API-first design** with versioning

---

## API Example

```http
POST /api/v1/resolve
Content-Type: application/json

{
  "entities": ["BMW X5", "WH-1000XM5"],
  "format": "elevenlabs"
}
```

Response includes IPA phonemes and a downloadable dictionary file.

---

## Documentation

| Document | Description |
|----------|-------------|
| [Architecture](./ARCHITECTURE.md) | Pipeline design and data flow |
| [Case Study](./CASE_STUDY.md) | Full project overview |
| [Security](./docs/security.md) | API authentication and access |
| [ADRs](./docs/adr/) | Architecture decision records |

---

## Open Source Component

The [ninolex-gh](https://github.com/iamnortey/ninolex-gh) repository contains the open Ghanaian pronunciation dictionary — demonstrating the data format and linguistic approach used in the full platform.

---

## Access

The core implementation is in a **private repository** to protect intellectual property. This repository contains architecture documentation, API design docs, pipeline diagrams, and integration examples.

For API access or technical discussions: [LinkedIn](https://linkedin.com/in/inortey/)

---

## Related

- [Ninolex-GH (Open Source)](https://github.com/iamnortey/ninolex-gh) — open Ghanaian pronunciation dictionary
- [Portfolio](https://github.com/iamnortey/portfolio) — all case studies and architecture samples
- [Case Study](https://github.com/iamnortey/portfolio/blob/main/case-studies/ninolex.md) — full project deep-dive
