# 🚀 Quick Reference

> Rychlý přehled klíčových informací o projektu Pixcard

---

## 📌 Základní Info

```yaml
Projekt: Pixcard
Typ: Interactive 2D Game Portfolio Builder
Status: Pre-development (dokumentace hotová)
Target: Game developers, pixel artists, kreativci
```

---

## 🔥 Rychlý Start

### Pro Nováčky (5 min read)
1. [01-project-overview.md](./01-project-overview.md) - Co je Pixcard?
2. [05-mvp-scope.md](./05-mvp-scope.md) - Co buildíme?
3. [06-open-questions.md](./06-open-questions.md) - Co ještě rozhodnout?

### Pro Vývojáře
```yaml
Tech Stack:
  Frontend: Svelte 5 + Phaser 3 + TypeScript
  Backend: PHP 8.2 + MySQL 8.0
  Auth: Supabase (Google OAuth)
  Hosting: WebGlobe Ultra

Dokumenty ke čtení:
  1. [02-tech-stack.md](./02-tech-stack.md)
  2. [03-architecture.md](./03-architecture.md)
  3. [04-database-schema.md](./04-database-schema.md)
```

---

## ✅ Rozhodnuté Věci

**Tech Rozhodnutí:**
- ✅ Svelte 5 (ne SvelteKit) - static build
- ✅ PHP backend (WebGlobe native)
- ✅ MySQL s JSON columns
- ✅ Dynamic routing (PHP načte z DB)
- ✅ Draft/Publish workflow
- ✅ Username-first auth flow
- ✅ Desktop-only builder (MVP)
- ✅ Lokalizace: CZ + EN

---

## ❓ Co Ještě Rozhodnout

**URGENTNÍ:**
- 🔴 **Domain name**: pixfolio.me (doporučeno kvůli legal)
- 🔴 **Registrovat ASAP!**

**Důležité:**
- 🟡 Asset naming conventions
- 🟡 Color palette & design system
- 🟡 Custom domains timeline (MVP vs v2)

**Nice to have:**
- 🟢 Premium pricing (99-199 Kč/měsíc)
- 🟢 Analytics level (minimal vs detailed)
- 🟢 GDPR docs (kdo řeší?)
- 🟢 Marketing strategy (kdo vede?)

→ Detaily: [06-open-questions.md](./06-open-questions.md)

---

## 📦 MVP Features

```yaml
Musí mít:
  ✅ Landing page + CTA
  ✅ Builder (username, character, background, dialogy)
  ✅ Preview (Phaser iframe)
  ✅ Google OAuth sign up
  ✅ Publish → username.pixfolio.me
  ✅ Edit mode (draft/publish)
  ✅ View counter
  ✅ Mobile viewing (ne mobile builder)

Nemá v MVP:
  ❌ Premium tier
  ❌ Custom domains
  ❌ More than 3 characters/backgrounds
  ❌ Advanced analytics
  ❌ Social features
```

→ Detaily: [05-mvp-scope.md](./05-mvp-scope.md)

---

## 🗄️ Database Quick Look

```sql
-- Dvě hlavní tabulky
users (id, email, supabase_id, created_at)
portfolios (
  id, user_id, username,
  character_skin, background_id,
  config_draft JSON,
  config_published JSON,
  published, view_count
)
```

→ Detaily: [04-database-schema.md](./04-database-schema.md)

---

## 🎨 Design Direction

```yaml
Style: Modern pixel art
  - Clean, professional
  - NOT retro/lo-fi nostalgia
  - Keyboard-inspired buttons
  - Limited color palette

Sprites: 32x32 pixels

UI Components:
  - Pixel-art aesthetic
  - Mechanical key look (buttons)
  - Terminal vibes
  - Accessibility-friendly
```

→ TODO: [11-ui-components-TODO.md](./11-ui-components-TODO.md)
→ TODO: [12-assets-guide-TODO.md](./12-assets-guide-TODO.md)

---

## 🔧 API Overview

```yaml
Základní endpoints:
  GET /api/portfolio/:username - Public
  GET /api/portfolio/mine - User's portfolio
  POST /api/portfolio - Create
  PUT /api/portfolio - Update
  DELETE /api/portfolio - Delete

Auth: JWT token (Supabase)
Format: JSON
Rate limiting: TBD
```

→ TODO: [10-api-endpoints-TODO.md](./10-api-endpoints-TODO.md)

---

## ⚡ Performance Targets

```yaml
Bundle sizes:
  Landing: ~30 KB
  Builder: ~80 KB
  Game: ~350 KB (lazy loaded)

Load time: < 3s
Mobile: Works perfectly (viewing only)
```

---

## 🎯 Action Items

**Před vývojem:**
- [ ] **Registrovat doménu** (URGENTNÍ!)
- [ ] Team meeting → vyplnit 06-open-questions.md
- [ ] Potvrdit asset naming convention
- [ ] Definovat color palette

**Během vývoje:**
- [ ] API specifikace → update 10-api-endpoints-TODO.md
- [ ] UI design session → update 11-ui-components-TODO.md
- [ ] Připravit GDPR docs

**Před launchem:**
- [ ] Marketing plán
- [ ] Support email setup
- [ ] Beta testing

---

## 🔗 Užitečné Odkazy

```yaml
Dokumentace:
  - Hlavní README: README.md
  - Changelog: CHANGELOG.md
  - Quick Ref: QUICK-REF.md (tento soubor)

Externí:
  - Elusse prototyp: [link TBD]
  - Design mockupy: [link TBD]
  - Project board: [link TBD]
```

---

## 📚 Kompletní Seznam Dokumentů

```
✅ Hotové:
  01 - Project Overview (196 lines)
  02 - Tech Stack (171 lines)
  03 - Architecture (216 lines)
  04 - Database Schema (221 lines)
  05 - MVP Scope (199 lines)
  06 - Open Questions (310 lines) ← zkráceno!
  07 - Decisions Log (126 lines)
  08 - SEO Strategy (346 lines)
  09 - Error Handling (401 lines)

⏳ TODO:
  10 - API Endpoints (62 lines placeholder)
  11 - UI Components (72 lines placeholder)
  12 - Assets Guide (90 lines placeholder)

📋 Meta:
  README.md (hlavní index)
  CHANGELOG.md (historie změn)
  QUICK-REF.md (tento soubor)
```

---

## 💡 Tipy

**Nový člen týmu?**
→ Čti v pořadí: 01 → 02 → 05 → 06

**Začínáš kódovat?**
→ Čti: 02 → 03 → 04 → 10 → 11

**Plánuješ featury?**
→ Čti: 05 → 06 → 07

**Řešíš design?**
→ Čti: 11 → 12 → 01

---

**Last Updated:** 24.11.2025  
**Maintained by:** GitHub Copilot + Team
