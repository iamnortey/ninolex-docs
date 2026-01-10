# Ninolex Documentation

**Pronunciation infrastructure for AI voice applications**

[![Case Study](https://img.shields.io/badge/case%20study-portfolio-blue)](https://github.com/iamnortey/portfolio/blob/main/case-studies/ninolex.md)
[![Open Dictionary](https://img.shields.io/badge/open%20source-ninolex--gh-green)](https://github.com/iamnortey/ninolex-gh)

---

## Overview

Ninolex provides a cross-platform source of truth for how real-world entities should be pronounced in AI voice applications. TTS engines mispronounce brands, products, and names—Ninolex fixes that.

### The Problem

- TTS engines mispronounce brands: "BMW" becomes gibberish
- Product names are unpronounceable: "WH-1000XM5"
- Domain terminology is wrong: medical, legal, automotive terms
- Cultural names are butchered

### The Solution

**Pronunciation Resolution Pipeline:** Text → Normalize → Resolve → Export

Entity registry with IPA phonemes, exportable to ElevenLabs, AWS Polly, and Vapi formats.

---

## Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js |
| Backend | Next.js API Routes, Modal |
| Resolution | CMUdict, Phonemizer |
| Database | Supabase |
| Export | ElevenLabs, AWS Polly, Vapi |

---

## Architecture

See [Pipeline Architecture](./ARCHITECTURE.md) for diagrams and component details.

**Key patterns:**
- Two-tier resolution (CMUdict + Phonemizer fallback)
- Alphanumeric expansion ("WH-1000XM5" → "W H one thousand X M five")
- Vertical pack architecture (AutoLex, DineLex)
- API-first design with versioning

---

## Documentation

| Document | Description |
|----------|-------------|
| [Architecture](./ARCHITECTURE.md) | Pipeline design and data flow |
| [Case Study](./CASE_STUDY.md) | Full 12-section case study |
| [Security](./docs/security.md) | API authentication and access |
| [ADRs](./docs/adr/) | Architecture decision records |

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

Response includes IPA phonemes and downloadable dictionary file.

---

## Open Source Component

The [ninolex-gh](https://github.com/iamnortey/ninolex-gh) repository contains the open Ghanaian pronunciation dictionary—demonstrating the data format and linguistic approach.

---

## Metrics

| Metric | Value |
|--------|-------|
| TypeScript | 1.88M+ lines |
| Documentation | 39+ files |
| Export formats | 3 |
| Vertical packs | 2+ |

---

## Repo Access Note

The core implementation of Ninolex is in a **private repository** to protect intellectual property.

This repository contains:
- Architecture documentation
- API design documentation
- Pipeline diagrams
- Integration examples

For API access or technical discussions, please reach out via [LinkedIn](https://linkedin.com/in/inortey/).

---

## Related

- [Portfolio](https://github.com/iamnortey/portfolio)
- [Ninolex-GH (Open Source)](https://github.com/iamnortey/ninolex-gh)
- [Full Case Study](https://github.com/iamnortey/portfolio/blob/main/case-studies/ninolex.md)
