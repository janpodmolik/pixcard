# 02 - Technologický stack

> Rozhodnuté technologie pro frontend, backend a hosting

---

## 🎨 Frontend

### Builder UI

```yaml
Framework: Svelte 5 (NE SvelteKit)
  - Static build pro PHP hosting
  - Menší bundle než React/Vue
  - Migrace na Kit možná později

Routing: tinro (4kb lightweight)

Build: Vite + TypeScript

Styling: Plain CSS + CSS Variables
  - Svelte scoped styles
  - Pixel-art custom design
```

### Game Runtime

```yaml
Engine: Phaser 3.90+
  Bundle: ~350 KB
  
  Proč Phaser:
    ✅ Hotový prototyp (Elusse) = 40-60h saved
    ✅ Physics, animations, camera ready
    ✅ TypeScript support
  
  Optimalizace:
    - Lazy load (jen při preview/runtime)
    - Builder UI bez Phaseru
```

---

## 🔧 Backend

```yaml
Server: PHP 8.2
  - WebGlobe Ultra native support
  - Jednoduchá CRUD API

Database: MySQL 8.0
  - WebGlobe included
  - JSON column support
  - Tables: users, portfolios

Auth: Supabase Auth
  - Free tier: 50,000 MAU
  - Google OAuth + Email/password
  - JWT tokens
  - Alternativa: Clerk (10k MAU)
```

---

## 🌐 Hosting

```yaml
Provider: WebGlobe Ultra
  Cost: ~100-300 Kč/měsíc
  
  Features:
    ✅ Wildcard subdomain (*.pixcard.me)
    ✅ PHP 8.2 + MySQL 8.0
    ✅ Let's Encrypt SSL
  
  Proč:
    - Český support
    - Subdomain support kritický
    - Levné pro start

Routing:
  username.pixcard.me → PHP dynamic routing

Future scale (>5k users):
  - VPS (Hetzner 5-10€/měsíc)
  - CDN pro assets (Cloudflare/Bunny)
```

---

## 🔐 Security

```yaml
Frontend:
  - XSS protection (sanitize input)
  - CSRF tokens
  - No sensitive data v localStorage

Backend:
  - Prepared statements (SQL injection)
  - Input validation
  - Rate limiting (10 req/s per IP)
  - JWT expiration (24h)
  - HTTPS only

Database:
  - Limited privileges
  - Daily backups
```

---

## 🛠️ Development Tools

```yaml
Git: GitHub (private → public later?)

Code Quality:
  - ESLint + Prettier
  - TypeScript strict mode

Testing (Future):
  - Vitest (unit tests)
  - Playwright (E2E)

Monitoring (Future):
  - Simple view counter (MVP)
  - Sentry (error tracking)
  - UptimeRobot (uptime alerts)
```

---

## 🎯 Summary

```yaml
Frontend: Svelte 5 + Phaser 3 + TypeScript + Vite
Backend: PHP 8.2 + MySQL 8.0
Auth: Supabase (OAuth + JWT)
Hosting: WebGlobe Ultra

Bundle Size:
  Landing: ~30 KB
  Builder: ~80 KB
  Game: ~350 KB (lazy loaded)
```

---

## 🔄 Future Upgrade Path

```yaml
Svelte → SvelteKit (SSR)
PHP → Node.js/Bun (full TypeScript)
MySQL → PostgreSQL (lepší JSON)
WebGlobe → VPS (Hetzner)

Architecture umožňuje postupný upgrade
```

---

## 📚 See Also

- **Architecture** → [03-architecture.md](./03-architecture.md)
- **Database schema** → [04-database-schema.md](./04-database-schema.md)

---

**Next:** [Architektura systému →](./03-architecture.md)
