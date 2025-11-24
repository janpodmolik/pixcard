# 06 - Otevřené otázky

> Co ještě není rozhodnuto a vyžaduje diskuzi

---

## 🔴 KRITICKÉ (Před zahájením vývoje)

### 1. Domain Name - Finální rozhodnutí

```yaml
Option A: pixcard.me
  ✅ Card = business card asociace
  ✅ Short, memorable
  ✅ International reach

Option B: pixfolio.me
  ✅ Portfolio = long-term content
  ✅ Unique (zero konkurence na Google)
  ⚠️ Méně intuitivní

Aktuální preference: pixcard.me
```

**🚨 ACTION:** Registrovat doménu ASAP (než ji vezme někdo jiný)

**Checklist před registrací:**
```bash
# Zkontrolovat dostupnost
whois pixcard.me
whois pixfolio.me

# Zkontrolovat social handles
twitter.com/pixcard
instagram.com/pixcard
```

**🚨 ROZHODNUTÍ:** _____________ (URGENTNÍ)

---

## 🟡 DŮLEŽITÉ (Během vývoje)

### 2. Naming Conventions pro Assets

```yaml
Otázka: Jak pojmenovat sprite soubory?

Příklady možných konvencí:
  Option A: character-orange-idle.png
  Option B: orange_idle.png
  Option C: orange/idle.png
  
Složky:
  /assets/sprites/orange/
  /assets/backgrounds/forest/
  /assets/ui/

Co rozhodnout:
  - File naming pattern
  - Folder structure
  - Animation frame naming (idle_01, idle_02...)
```

**📝 TODO:** Definovat v [11-assets-guide-TODO.md](./11-assets-guide-TODO.md)

**🚨 ROZHODNUTÍ:** _____________ (Before asset production)

---

### 3. Color Palette & Design System

```yaml
Otázka: Jakou barevnou paletu použijeme?

Co definovat:
  - Primary colors (CTA buttons, links)
  - Background colors (light/dark mode?)
  - Text colors
  - Error/success/warning states
  - Border & shadow colors
  
Pixel-art style:
  - Limited palette (8-16 colors?)
  - Retro feel vs modern clean
  - Accessibility contrast ratios
```

**📝 TODO:** Vyřešit s designérem před UI implementací

**🚨 ROZHODNUTÍ:** _____________ (Before frontend sprint)

---

### 4. Custom Domains Support

```yaml
Otázka: Kdy přidat podporu custom domén?

MVP: Subdomain only (username.pixcard.me)

v2 Options:
  - Custom domain pointing (john.com → portfolio)
  - Premium feature
  - DNS + SSL setup required
  
Timeline: Po MVP launch?
```

**🚨 ROZHODNUTÍ:** _____________ (Can decide later)

---

## 🟢 NICE TO HAVE (Post-MVP)

### 5. Analytics Level

```yaml
MVP: Minimal tracking
  - Total view count
  - Last viewed timestamp
  
v2 Options:
  A) Detailed free
     - Unique visitors, referrers
     - Free pro všechny
  
  B) Detailed premium
     - Premium feature only
     - Monetization opportunity
  
  C) Privacy-first
     - No tracking vůbec (GDPR friendly)
     - Only basic counter
```

**🚨 ROZHODNUTÍ:** _____________ (After MVP user feedback)

---

### 6. Premium Pricing

```yaml
Otázka: Kolik bude stát premium tier?

Research:
  - Card.co: $6/měsíc (~150 Kč)
  - Linktree Pro: $5/měsíc
  - About.me: $8/měsíc

Návrh:
  Option A: 99 Kč/měsíc
  Option B: 149 Kč/měsíc
  Option C: 199 Kč/měsíc
  
Features:
  - Unlimited dialogy
  - More characters/backgrounds
  - Custom domain
  - Advanced analytics
  - No "Powered by" badge?
```

**🚨 ROZHODNUTÍ:** _____________ (After MVP launch + user feedback)

---

## 💼 Business & Legal

### 7. GDPR Compliance

```yaml
Potřebné dokumenty:
  - Privacy Policy
  - Terms of Service
  - Cookie Consent banner
  - Data export/delete functionality

Options:
  A) Legal template service (Termly, Iubenda)
  B) Lawyer consultation
  C) Copy from similar service (risky)

Kdy: Před public launch (Beta OK bez)
```

**🚨 ROZHODNUTÍ:** _____________ (WHO handles this?)

---

### 8. Support Model

```yaml
MVP Options:
  A) Email only (hello@pixcard.me)
     - Simple, manageable
     - Slow response time
  
  B) Discord community
     - Fast peer support
     - Community building
     - Moderation needed
  
  C) In-app chat (Intercom)
     - Professional
     - $$$$ expensive
     
Doporučení: Start s email (A), přidat Discord later
```

**🚨 ROZHODNUTÍ:** _____________ (Email confirmed for MVP?)

---

### 9. Marketing Launch Strategy

```yaml
Launch channels:
  [ ] Product Hunt
  [ ] Reddit (r/gamedev, r/webdev, r/SideProject)
  [ ] Twitter/X
  [ ] Czech game dev communities (FB, Discord)
  [ ] Indie Hackers
  [ ] Hacker News
  
Timing: Po MVP je stabilní
Budget: _____________
Odpovědná osoba: _____________
```

**🚨 ROZHODNUTÍ:** _____________ (WHO leads marketing?)

---

## 📋 Decisions Template

Po meetingu vyplň:

```yaml
KRITICKÉ:
  1. Domain name: [ ] pixcard.me [ ] pixfolio.me [ ] jiné: _____
     Deadline: ASAP

DŮLEŽITÉ:
  2. Asset naming: _____________
     Deadline: Before asset production
  
  3. Color palette: _____________
     Deadline: Before UI implementation
  
  4. Custom domains: [ ] MVP [ ] v2 [ ] v3+
     Deadline: Can wait

NICE TO HAVE:
  5. Analytics: [ ] Free detailed [ ] Premium [ ] Privacy-first
     Deadline: After MVP feedback
  
  6. Pricing: _____ Kč/měsíc
     Deadline: After MVP feedback

BUSINESS:
  7. GDPR: WHO? _____ HOW? _____
     Deadline: Before public launch
  
  8. Support: [ ] Email [ ] Discord [ ] Chat
     Deadline: MVP = Email OK
  
  9. Marketing: WHO? _____ BUDGET? _____
     Deadline: At MVP launch
```

---

## 🎯 Action Items

**Před začátkem vývoje:**
- [ ] **Registrovat doménu** (pixcard.me nebo pixfolio.me)
- [ ] Potvrdit asset naming convention
- [ ] Definovat color palette s designérem

**Během vývoje:**
- [ ] Rozhodnout custom domains timeline
- [ ] Připravit GDPR dokumenty (kdo?)

**Před launchem:**
- [ ] Marketing plán & odpovědná osoba
- [ ] Support email setup
- [ ] Beta testing skupina

---

## 📚 Related Docs

- **Tech stack** → [02-tech-stack.md](./02-tech-stack.md)
- **MVP scope** → [05-mvp-scope.md](./05-mvp-scope.md)
- **Architecture** → [03-architecture.md](./03-architecture.md)

---

**Last Updated:** 24.11.2025  
**Status:** ⚠️ Vyžaduje team meeting → pak update na ✅
