# 05 - MVP Scope

> Co dělat a co NE

---

## ✅ MVP Features

### 1. Landing Page
```yaml
- Hero + CTA "Create Portfolio"
- How it works (3 steps)
- FAQ
- Footer
```

### 2. Builder
```yaml
Username:
  - Input + real-time check
  - 3-50 znaků, a-z0-9-
  - Blacklist (admin, api, vulgarismy)

Character: 3 postavy (orange, white, black cat)

Background: 3 pozadí (forest, desert, city)

Dialogy:
  - Min 1, max 5 (free tier)
  - Text CS + EN
  - Pozice (X) + šířka
  - Add/Edit/Delete
```

### 3. Preview
```yaml
- Button "Preview"
- Iframe s Phaser game
- Live updates (postMessage)
- Close button
```

### 4. Publish
```yaml
1. Click "Publish"
2. Sign up (Google OAuth přes Supabase)
3. Save do DB
4. Redirect → username.pixcard.me
5. Share buttons (Twitter, LinkedIn, copy link)
```

### 5. Game Runtime
```yaml
Z Elusse prototypu:
  - Movement (A/D, arrows, jump)
  - Touch controls (mobile)
  - Parallax background
  - Dialog triggers
  - Speech bubbles
  - Camera follow

Nové:
  - Load config z API
  - Dynamic dialogy
  - View counter
```

### 6. Edit Mode
```yaml
- pixcard.me/builder → auto-load pokud logged in
- Edit existing portfolio
- Auto-save draft (každých 10s)
- "Publish Changes" button
- View stats (total views)
```

### 7. Analytics
```yaml
MVP:
  - View counter (total)
  - Last viewed timestamp

Display:
  - "123 views" v dashboardu
```

---

## ❌ NOT in MVP

```yaml
Premium features:
  - Monetization
  - Custom domain
  - Unlimited dialogy

Advanced:
  - More characters/backgrounds (>3)
  - Custom CSS/fonts
  - Sound effects

Analytics:
  - Unique visitors
  - Referrer tracking
  - Heatmaps

Social:
  - Gallery/discover page
  - Likes/comments
  - Follow users

Export/Import:
  - Download portfolio
  - Backup/restore
```

### 🚀 Future Vision (v3+)

```yaml
Visual Editor:
  - Drag&drop dialog positioning
  - Visual map preview
  - Platform builder (vlastní platformy, obstacles)
```

---

## 🎯 User Stories

### Story 1: Vytvoření portfolia
```
User:
  1. Google sign up
  2. Pick username, character, background
  3. Add 3-5 dialogy
  4. Preview
  5. Publish
  6. Share link

Time: <10 minut
```

### Story 2: Zobrazení portfolia
```
Visitor:
  1. Open username.pixcard.me
  2. Game loads (<3s)
  3. Control character
  4. Read dialogy
  5. Works on desktop + mobile

No signup required
```

### Story 3: Editace
```
Returning user:
  1. Login
  2. Dashboard loads portfolio
  3. Edit fields
  4. Preview draft
  5. Publish changes
  6. Live immediately
```

---

## ✅ Definition of Done

```yaml
✅ Google OAuth works
✅ Username check works
✅ Character + background picker works
✅ Dialog editor (add/edit/delete)
✅ Preview works
✅ Publish works
✅ username.pixcard.me loads portfolio
✅ Mobile + desktop works
✅ Edit existing portfolio works
✅ View counter works
✅ <3s load time
✅ Chrome, Firefox, Safari OK
✅ No critical bugs
```

**When all ✅ → MVP DONE 🎉**

---

## 📚 See Also

- **Architecture** → [03-architecture.md](./03-architecture.md)
- **Database** → [04-database-schema.md](./04-database-schema.md)
- **UI Components** → [10-ui-components-TODO.md](./10-ui-components-TODO.md)
- **Error handling** → [08-error-handling.md](./08-error-handling.md)

---

**Next:** [Otevřené otázky →](./06-open-questions.md)
