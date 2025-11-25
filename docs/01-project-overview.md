# 01 - Přehled projektu

> **⚠️ NAMING UPDATE:** Projekt byl přejmenován z "PixCard" na **"PixFolio"** kvůli právním rizikům (aktivní trademark v Brazílii). V dokumentaci zatím zůstává PixCard, finální rename proběhne po oficiálním rozhodnutí.

## 🎯 Základní koncept

**PixFolio** (dříve PixCard) je webová služba pro tvorbu interaktivních 2D herních portfolií.

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
3. Získá subdoménu: username.pixfolio.me
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

### Srovnání s existujícími nástroji

| Feature | Linktree | About.me | Carrd | Bento | **Pixcard** |
|---------|----------|----------|-------|-------|--------------|
| **Interaktivita** | ❌ Statické linky | ✅ AI chatbot | ❌ Statická stránka | 🟡 Rich embeds | ✅ **Interaktivní hra** |
| **Customizace** | 🟡 Témata, barvy | 🟡 Templates | ✅ Vysoká | ✅ Vysoká | ✅ **Vysoká + pixel-art** |
| **Free tier** | ✅ Ano (unlimited links) | ✅ Ano (základní page) | ✅ Ano (3 sites) | ✅ Ano | ✅ **Ano** |
| **Free subdoména** | ✅ linktr.ee/user | ✅ about.me/user | ✅ user.carrd.co | ✅ bento.me/user | ✅ **pixfolio.me/user** |
| **Custom domain** | ✅ Premium ($7.5+/mo) | ✅ Pro ($9/mo) | ✅ Pro ($19/yr) | ✅ Premium | ✅ **Premium (v2)** |
| **Analytics** | ✅ Základní free | ❌ Ne ve free | ✅ Pro only | 🟡 Limited | ✅ **View count** |
| **Target audience** | Influencers, všichni | Professionals | Web designers | Creatives | 🎮 **Game devs, artists** |
| **Zapamatovatelnost** | Low | Low | Low | Medium | ✅ **High (gameplay!)** |
| **Setup čas** | ~5 min | ~10 min | ~15 min | ~10 min | ✅ **~10 min** |

### Co dělá Pixcard unikátní?

**1. Gaming-first approach**
- Portfolio není jen "stránka s odkazy" – je to **mini-hra**
- Návštěvník nejen čte, ale **hraje si** a objevuje obsah
- Perfektní pro game dev community (portfolio = ukázka tvých skills)

**2. Pixel-art aesthetic**
- Nostalgický retro styl – obrovská popularita (viz itch.io, /r/PixelArt)
- Visual identity která okamžitě vyčnívá
- Atraktivní pro ilustrátory a pixel artists

**3. Storytelling mechanika**
- Dialog system = kreativnější než seznam odkazů
- Můžeš vyprávět příběh své kariéry
- Interaktivní způsob prezentace projektů

**4. Zero konkurence v game dev segmentu**
- Linktree/About.me/Bento = generické pro všechny
- Behance/Dribbble = statická portfolia
- **Gap v trhu:** Interaktivní game portfolia neexistují

**Klíčový diferenciátor:**  
→ Jediná platforma kde je **portfolio samo o sobě interactive gaming experience**  
→ Meta-prvek: Tvoje portfolio je ukázka tvého game dev vkusu

---

## 💰 Business model

### MVP Approach:

```yaml
FREE (forever):
  - 1 portfolio
  - 3 postavy na výběr
  - 3 pozadí na výběr
  - Max 5 dialogů
  - Subdoména: username.pixfolio.me
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
6. Hotovo! username.pixfolio.me is live
7. Sdílí na soc. sítích, tracking views

Visitor flow:
→ Enters: username.pixfolio.me
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
