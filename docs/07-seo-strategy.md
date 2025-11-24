# 08 - SEO Strategie

> Plán pro optimalizaci viditelnosti portfolií a hlavního webu

**Status:** Post-MVP (připravit během vývoje, implementovat po launchi)

---

## 🎯 Cíle

### Co chceme dosáhnout:

```yaml
1. User portfolia najitelná na Google
   - Vyhledávání: "john doe portfolio"
   - Vyhledávání: "john doe game developer"

2. Landing page viditelnost
   - "interactive portfolio"
   - "game developer portfolio"
   - "pixel art portfolio builder"

3. Organický růst
   - Featured portfolia jako showcase
   - Social sharing optimalizace
```

---

## 📋 MVP Requirements (Must Have)

### 1. Základní Meta Tags

**Pro každé portfolio (PHP generuje):**
```yaml
Essential:
  - <title> - Jméno uživatele + "Pixcard Portfolio"
  - <meta description> - Bio z config
  - <link canonical> - URL portfolia

Open Graph (social sharing):
  - og:title, og:description, og:type, og:url
  - og:image - Link na screenshot nebo placeholder

Twitter Card:
  - twitter:card, twitter:title, twitter:description
  - twitter:image
```

### 2. Robots.txt

```yaml
Povoleno:
  - Všechna portfolia (*.pixcard.me)
  - Landing page

Zakázáno:
  - /api/
  - /admin/

Sitemap: https://pixcard.me/sitemap.xml
```

### 3. Sitemap

```yaml
Generování:
  - PHP endpoint: /api/sitemap.php
  - Načte všechna published portfolia z DB
  - XML formát (Google standard)
  
Update:
  - Cron job: regenerace každý den 2:00
  - Nebo on-demand při publish nového portfolia

Submit:
  - Google Search Console po launchi
```

---

## 🚀 Post-MVP Vylepšení

### 4. OG Image Generation (Month 2)

**Problém:** Portfolia nemají screenshot pro social sharing

**Řešení A (levné):**
```yaml
Static template:
  - PHP vygeneruje PNG z GD library
  - Background + character sprite + text overlay
  - Cache na disk
  
Endpoint: /api/og-image/{username}
```

**Řešení B (dražší):**
```yaml
Puppeteer screenshot:
  - Real screenshot z běžící hry
  - Vyžaduje Node.js nebo service
  - Kvalitnější výsledek
  
Post-MVP: Pokud budget dovolí
```

### 5. Structured Data (Schema.org)

```yaml
Portfolio stránky:
  Type: "Person"
  Properties: name, description, url, image
  
Landing page:
  Type: "WebApplication"
  Properties: name, description, offers (free tier)

Benefit:
  - Rich results v Google
  - Better indexing
```

### 6. Landing Page SEO

```yaml
Meta optimization:
  - Keyword-focused title
  - Compelling description
  - Structured data (WebApplication)

Content sections:
  - H1, H2 headings (keywords)
  - Alt text na obrázky
  - Internal linking
```

### 7. Content Marketing (Month 3+)

```yaml
Blog sekce:
  - /blog/how-to-create-game-portfolio
  - /blog/best-indie-game-portfolios
  - /blog/pixel-art-portfolio-guide

Showcase:
  - /showcase (featured portfolios)
  - User stories
  
Benefit:
  - Backlinks
  - Long-tail keywords
  - Social sharing
```

---

## 📊 Performance SEO

### Core Web Vitals (Google ranking factor)

```yaml
Metriky:
  LCP (Largest Contentful Paint): < 2.5s
  FID (First Input Delay): < 100ms
  CLS (Cumulative Layout Shift): < 0.1

Optimalizace:
  - Lazy load Phaser (už máme)
  - Preload critical assets
  - Optimalizované obrázky (WebP)
  - CDN pro assets (future)
```

### Mobile-First

```yaml
Google indexuje primárně mobile:
  ✅ Responsive design (MVP má)
  ✅ Touch controls (MVP má)
  ⏳ Mobile builder (post-MVP)
```

---

## 🔍 Google Search Console

### Po launchi:

```yaml
1. Verifikace domény
   - DNS TXT record method

2. Submit sitemap
   - URL: https://pixcard.me/sitemap.xml

3. Monitoring
   - Coverage report (indexování)
   - URL Inspection tool (debug)
   - Performance tracking (klíčová slova)
```

---

## 📈 Analytics

### Doporučení:

```yaml
Option A: Google Analytics 4
  - Free
  - Full features
  - Komplexní tracking

Option B: Plausible
  - €9/měsíc
  - GDPR-friendly (no cookies)
  - Jednodušší interface
  - Privacy-focused
```

### Co trackovat:

```yaml
Organic traffic:
  - Odkud users přišli (Google, social, direct)
  - Klíčová slova (Search Console data)
  
Conversion:
  - Visit → Sign up rate
  - Visit → Portfolio created
  - Social shares
```

---

## 🎯 Keyword Strategie

### Primary Keywords

```yaml
Landing page target:
  High-intent:
    - "game developer portfolio builder"
    - "interactive portfolio maker"
    - "pixel art portfolio"
  
  Mid-intent:
    - "how to create game portfolio"
    - "best portfolio for game developers"
  
  Brand:
    - "pixcard"
```

### Long-tail Keywords

```yaml
Auto-generované z portfolií:
  - "[username] game developer"
  - "[username] pixel artist"
  
Přirozené díky user metadata
```

---

## ✅ SEO Checklist

### MVP (Před/při launchi):

```yaml
✅ Basic meta tags (title, description, canonical)
✅ Open Graph tags (social sharing)
✅ Robots.txt
✅ Sitemap generování
✅ Submit Google Search Console
✅ Mobile responsive
```

### Post-MVP (Month 1-3):

```yaml
⏳ OG image generation
⏳ Structured data (Schema.org)
⏳ Analytics setup
⏳ Performance optimization
⏳ Content marketing start
```

---

## 🚨 Anti-Patterns (Vyhnout se)

```yaml
❌ Duplicate content
   - Každé portfolio unikátní meta description
   
❌ Keyword stuffing
   - Přirozený jazyk, ne "game developer game portfolio game"
   
❌ Slow load times
   - Monitor Core Web Vitals
   
❌ Broken links
   - 404s škodí rankingu
   - Redirect deleted portfolios → homepage
```

---

## 📅 Implementation Timeline

```yaml
Launch Day:
  - Basic meta tags ✅
  - Robots.txt ✅
  - Sitemap ✅

Week 1:
  - Search Console setup
  - Analytics setup

Month 1:
  - OG image generation
  - Performance audit

Month 2-3:
  - Structured data
  - Content marketing
  - Featured portfolios section
```

---

---

## 📚 See Also

- **MVP scope** → [05-mvp-scope.md](./05-mvp-scope.md)
- **Architecture** → [03-architecture.md](./03-architecture.md)
- **Open questions** → [06-open-questions.md](./06-open-questions.md)

---

**Next:** Implementovat během MVP vývoje podle priority
