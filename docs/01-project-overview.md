# 01 - Přehled projektu

## 🎯 Základní koncept

**Pixcard** je webová služba pro tvorbu interaktivních 2D herních portfolií.

### Co to je?

No-code platforma, kde si uživatel vytvoří **herní 2D portfolio** – malou interaktivní scénu s postavičkou, která představuje autora formou dialogů:
- CV a zkušenosti
- Reference a projekty
- Kontaktní informace
- Ukázky práce

### Jak to funguje?

```
1. User vybere postavu + pozadí
2. Nastaví dialogy (texty, pozice)
3. Získá subdoménu: username.pixcard.me
4. Sdílí portfolio jako interaktivní hru
```

---

## 🎨 Inspirace

**Podobné služby:**
- **card.co** - Digital business cards (statické)
- **Linktree** - Link-in-bio (seznam odkazů)
- **About.me** - Personal landing pages

**Pixcard rozdíl:**
- ✅ Interaktivní & hravé (ne jen statická karta)
- ✅ Pixel-art aesthetic (nostalgický, populární)
- ✅ Storytelling přes gameplay
- ✅ Originální & zapamatovatelné
- ✅ Rychlé (10 min setup), Free to start

---

## 👥 Cílová skupina

```yaml
1. Game developers (indie devs)
   - Chtějí ukázat své projekty hravě
   - Portfolio jako mini-hra = meta

2. Pixel artists & illustrátoři
   - Portfolio v jejich stylu (pixel-art)
   - Ukázka skills přímo v portfoliu

3. Game designers & kreativci
   - Interaktivní storytelling
   - Chcí se odlišit od konkurence
```

---

## 🌟 Konkurenční výhoda

| Feature | card.co | Linktree | About.me | **Pixcard** |
|---------|---------|----------|----------|--------------|
| **Interaktivita** | ❌ | ❌ | ❌ | ✅ Hra |
| **Customizace** | Medium | Low | Medium | ✅ High |
| **Free tier** | ❌ Trial | ✅ Ano | ✅ Ano | ✅ Ano |
| **Custom domain** | ✅ Premium | ✅ Premium | ✅ Premium | ✅ Premium |
| **Free subdoména** | ❌ | ✅ | ✅ | ✅ |
| **Zapamatovatelnost** | Low | Low | Medium | ✅ High |
| **Gaming focus** | ❌ | ❌ | ❌ | ✅ Ano |

**Klíčový diferenciátor:**  
→ Jediná platforma kde je **portfolio samo o sobě interactive experience**

---

## 💰 Business model

### MVP Approach:

```yaml
FREE (forever):
  - 1 portfolio
  - 3 postavy na výběr
  - 3 pozadí na výběr
  - Max 5 dialogů
  - Subdoména: username.pixcard.me
  - Basic analytics (view count)

Future monetization (Post-MVP):
  - Premium tier TBD based on user feedback
  - Features to consider:
    - Unlimited portfolia
    - Více postav a pozadí
    - Unlimited dialogy
    - Custom doména
    - Advanced analytics
```

## 📊 Market Research

```yaml
Game industry:
  - Indie game development booming
  - Portfolio > CV v creative fields

Pixel art trend:
  - Nostalgie za retro hrami
  - Active community (itch.io, r/PixelArt)

Portfolio platforms:
  - Behance, Dribbble = statické
  - Linktree = jen odkazy
  - Gap = interaktivní game portfolia
```

---

## 🎮 User Journey

```
1. User najde Pixcard (Google / Reddit)
2. Klikne "Create Portfolio"
3. Vybere username, postavu, pozadí
4. Přidá dialogy (představení, projekty, kontakt)
5. Preview → Publish → Sign up (Google)
6. Hotovo! username.pixcard.me is live
7. Sdílí na soc. sítích, tracking views

Visitor flow:
→ Enters: username.pixcard.me
→ Loading screen
→ Game starts, character walks
→ Triggers dialogs (info o autorovi)
→ Contacts creator
```

---

## 🌍 Go-to-market

```yaml
Soft Launch:
  - Beta test s 10-20 users
  - Reddit (r/gamedev, r/webdev)
  - Czech game dev communities

Public Launch:
  - Product Hunt
  - Twitter (#pixelart, #gamedev)
  - YouTube tutorial
```

---

## ⚠️ Risks & Mitigation

### Risk 1: Low adoption
```
Risk: Nikdo to nepoužije
Mitigation:
  - Free tier attractive
  - Early user feedback
  - Pivot možný (use Phaser base for other projects)
```

### Risk 2: Tech complexity
```
Risk: Phaser + PHP + Svelte = složité
Mitigation:
  - Máme prototyp (Elusse)
  - Modular architecture
  - MVP scope clear
```

### Risk 3: Competition
```
Risk: Někdo udělá clone
Mitigation:
  - First mover advantage
  - Community building
  - Unique aesthetic & UX
```

---

## 📚 See Also

- **Tech stack** → [02-tech-stack.md](./02-tech-stack.md)
- **MVP scope** → [05-mvp-scope.md](./05-mvp-scope.md)
- **Architecture** → [03-architecture.md](./03-architecture.md)
- **Open questions** → [06-open-questions.md](./06-open-questions.md)

---

**Next:** [Technologický stack →](./02-tech-stack.md)
