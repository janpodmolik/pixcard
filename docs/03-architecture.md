# 03 - Architektura

> Jak aplikace funguje - high-level přehled

---

## 🎯 Základní Princip

```yaml
3 hlavní části:

1. Builder (pixcard.me/builder)
   - Svelte UI pro vytvoření portfolia
   - Username, postava, pozadí, dialogy
   - Preview a publish

2. Runtime (username.pixcard.me)
   - Phaser game který zobrazí portfolio
   - Načte config z DB
   - Interaktivní experience

3. Backend (PHP + MySQL)
   - API pro CRUD portfolií
   - Auth přes Supabase
   - Subdomain routing
```

---

## 🔄 Jak to Funguje

### Vytvoření portfolia

```
User → Vyplní builder → Preview → Sign up → Publish → Live na username.pixcard.me
```

**Co se děje:**
1. Builder: User nastaví postavu, pozadí, napíše dialogy
2. Preview: Iframe ukáže jak to vypadá (Phaser game)
3. Publish: Uloží config do MySQL (přes PHP API)
4. Subdomain: WebGlobe routing vytvoří username.pixcard.me

### Zobrazení portfolia

```
Visitor → johndoe.pixcard.me → PHP načte config z DB → Phaser game → Interaktivní portfolio
```

**Co se děje:**
1. WebGlobe routing: subdomain → username
2. PHP: Načti config z MySQL
3. HTML: Inject config jako JavaScript
4. Phaser: Načti assety, vytvoř scénu, zobraz dialogy

4. Phaser: Načti assety, vytvoř scénu, zobraz dialogy

### Editace portfolia

```
Logged user → Builder → Načti draft → Edit → Publish → Update live site
```

**Co se děje:**
1. Auth: JWT token v localStorage
2. API: GET /api/portfolio/mine (vrátí draft)
3. Edit: Auto-save do localStorage
4. Publish: PUT /api/portfolio (draft → published)

---

## 💾 Data Structure

### Portfolio Config (JSON v MySQL)

```yaml
Co se ukládá:
  - Metadata: jméno, bio
  - Character: orange/white/black
  - Background: forest/desert/city
  - Dialogs: [{pozice, text_cs, text_en}]
  - Settings: jazyk, controls

Dvě verze:
  - config_draft: rozpracovaná (auto-save)
  - config_published: live na subdoméně
```

---

## 🔐 Auth & Routing

### Supabase OAuth

```yaml
Sign up/Login:
  1. Google OAuth přes Supabase
  2. Vrátí JWT token
  3. Uložíme do localStorage
  4. Přidáme do každého API requestu

Backend validuje:
  - JWT v Authorization header
  - Extrahuj user_id
  - Check permissions
```

### Subdomain Routing

```yaml
WebGlobe .htaccess:
  username.pixcard.me → /runtime/index.php?username=XXX

PHP Runtime:
  - Extrahuj username
  - Načti config z MySQL
  - 404 pokud neexistuje/unpublished
  - Inject config do HTML
  - Load Phaser game
```

---

## 🎮 Phaser Integration

### Z Elusse Prototypu

```yaml
Co přepoužijeme:
  - GameScene (preload, create, update)
  - Player class (physics, animations)
  - Dialog trigger system
  - Camera follow
  - Parallax background

Co změníme:
  - Config loading (dynamic z MySQL místo hardcoded)
  - Character/background switching
  - Dialog positions z config
```

### Runtime Flow

```yaml
1. HTML načte config: window.__PORTFOLIO_CONFIG__
2. Phaser init s config
3. Preload jen potřebné assety (character + bg z config)
4. Create scene: player, triggers, dialogs
5. User controls → walk → trigger dialog
```

---

## 📡 API Endpoints

**Detailní specifikace** → [09-api-endpoints-TODO.md](./09-api-endpoints-TODO.md)

```yaml
Základní struktura:
  GET /api/portfolio/:username - Public view
  GET /api/portfolio/mine - User's portfolio
  POST /api/portfolio - Create new
  PUT /api/portfolio - Update existing
  DELETE /api/portfolio - Delete

Auth: JWT token v Authorization header
Response: JSON format
Rate limit: TBD
```

---

## ⚡ Performance Strategy

```yaml
Bundle sizes:
  Landing: 30 KB (landing page jen HTML/CSS)
  Builder: 80 KB (lazy load Svelte app)
  Game: 350 KB (lazy load Phaser při preview/runtime)

Optimalizace:
  - Lazy loading (načti jen co potřebuješ)
  - Asset caching (sprites, backgrounds)
  - Load jen used assety (ne všechny postavy)
  - LocalStorage auto-save (nemusíme ping API)

Cache headers:
  - Assets: 1 rok
  - Game bundle: 1 den
  - API: no-cache
```

---

## 🛠️ Tech Stack Recap

```yaml
Frontend Builder: Svelte 5 + Vite
Game Runtime: Phaser 3 (z Elusse)
Backend: PHP 8.2 + MySQL 8.0
Auth: Supabase (Google OAuth)
Hosting: WebGlobe Ultra (subdomain support)
```

---

## 📚 See Also

- **Database schema** → [04-database-schema.md](./04-database-schema.md)
- **API endpoints** → [09-api-endpoints-TODO.md](./09-api-endpoints-TODO.md)
- **Tech stack** → [02-tech-stack.md](./02-tech-stack.md)
- **Error handling** → [08-error-handling.md](./08-error-handling.md)

---

**Next:** [Databázové schema →](./04-database-schema.md)
