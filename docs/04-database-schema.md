# 04 - Databáze

> Co se ukládá a jak

---

## 📊 Přehled

```yaml
System: MySQL 8.0
Tabulky: users, portfolios
Charset: utf8mb4
```

---

## 👤 Tabulka: users

```yaml
Sloupce:
  id: Primary key
  email: Email z Supabase
  supabase_id: ID z Supabase Auth
  created_at: Kdy se registroval
  updated_at: Poslední update

Proč:
  - Propojení s Supabase Auth
  - Jeden user = jedno portfolio (MVP)
```

---

## 📄 Tabulka: portfolios

```yaml
Základní info:
  id: Primary key
  user_id: Komu patří (→ users.id)
  username: Subdoména (johndoe)
  
Vzhled:
  character_skin: orange | white | black
  background_id: forest | desert | city
  
Config (JSON):
  config_draft: Rozpracovaná verze
  config_published: Live verze (NULL = není publikováno)
  
Stav:
  published: true/false
  published_at: Kdy publikováno
  
Meta:
  created_at: Kdy vytvořeno
  updated_at: Poslední edit
  view_count: Počet zobrazení
```

---

## 📦 Config JSON Struktura

```json
{
  "metadata": {
    "name": "John Doe",
    "bio": "Game developer"
  },
  "character": "orange",
  "background": "forest",
  "dialogs": [
    {
      "id": "dialog_1",
      "x": 200,
      "width": 150,
      "text": {
        "cs": "Ahoj, jsem John!",
        "en": "Hi, I'm John!"
      }
    }
  ],
  "settings": {
    "language": "en",
    "showControls": true
  }
}
```

**Proč JSON:**
- Flexibilní struktura
- Snadno se přidávají fieldy
- Atomic update

---

## 🔍 Typické Dotazy

### Načíst portfolio (public view)

```sql
SELECT config_published, view_count
FROM portfolios
WHERE username = 'johndoe' AND published = TRUE;
```

### Načíst draft (logged user)

```sql
SELECT p.config_draft, p.config_published
FROM portfolios p
JOIN users u ON p.user_id = u.id
WHERE u.supabase_id = 'xxx-xxx';
```

### Check username volný?

```sql
SELECT COUNT(*) FROM portfolios 
WHERE username = 'johndoe';
-- 0 = volný
```

### Zvýšit view counter

```sql
UPDATE portfolios 
SET view_count = view_count + 1
WHERE username = 'johndoe';
```

---

## ✅ Validace

### Username pravidla

```yaml
Formát: 
  - 3-50 znaků
  - Jen a-z, 0-9, pomlčka
  - Lowercase

Blacklist:
  - admin, api, www, help, support
  - pixcard, pixfolio
  - Vulgarity (fuck, shit, etc.)
```

### Free tier limity

```yaml
Max dialogy: 5
Max text: 500 znaků per dialog
```

---

## 🔐 Security

```yaml
SQL injection:
  - Vždy prepared statements
  - NIKDY $query = "WHERE user = '$input'"

User isolation:
  - Validuj JWT → user_id
  - WHERE user_id = :authenticated_user_id

XSS:
  - htmlspecialchars() před uložením
```

---

## 💾 Backup

```bash
# Denní záloha
mysqldump pixcard_db | gzip > backup_$(date +%Y%m%d).sql.gz

# Restore
gunzip < backup.sql.gz | mysql pixcard_db
```

---

## 🚀 Indexy (pro rychlost)

```yaml
portfolios.username: UNIQUE (subdomain lookup)
portfolios.user_id: INDEX (najdi portfolio usera)
portfolios.published: INDEX (filtruj published)
users.supabase_id: INDEX (auth lookup)
```

---

## 📈 Future (Post-MVP)

```yaml
Premium tier:
  - users.tier (free/premium)
  - portfolios.dialog_limit (5 nebo unlimited)

Analytics:
  - portfolio_views tabulka (detailed tracking)
  - portfolio_stats_daily (agregované stats)
```

---

## 📚 See Also

- **Architecture** → [03-architecture.md](./03-architecture.md)
- **API endpoints** → [09-api-endpoints-TODO.md](./09-api-endpoints-TODO.md)
- **MVP scope** → [05-mvp-scope.md](./05-mvp-scope.md)

---

**Next:** [MVP Scope →](./05-mvp-scope.md)
