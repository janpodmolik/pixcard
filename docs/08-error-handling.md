# 09 - Error Handling Strategy

> Jak aplikace zvládá chyby a poskytuje fallback experiences

---

## 🎯 Základní Principy

```yaml
1. Fail gracefully
   - Nikdy white screen of death
   - Vždy nějaká UI response

2. Clear messaging
   - User ví co se stalo
   - Jasná next akce

3. Recovery options
   - Retry button kde má smysl
   - Alternativní cesta

4. Silent recovery
   - Minor errory řešit automaticky
   - Retry logic na pozadí

5. Track errors
   - Logovat pro debugging
   - Monitoring kritických chyb
```

---

## 🔴 Kritické Scénáře (Must Handle)

### 1. Game Runtime Load Failure

**Problém:** Phaser bundle se nepodaří načíst nebo inicializovat

**Fallback:**
```yaml
Static portfolio view:
  - Zobraz jméno a bio
  - Vypíš všechny dialogy jako text karty
  - "Interactive portfolio temporarily unavailable"
  - Retry button
  - Link na support email

UI:
  - Pixel-art error icon
  - Friendly message (ne technical jargon)
  - Clear call-to-action
```

**Tracking:**
- Logovat error do backend
- Track: asset URL, browser, error message

---

### 2. Portfolio Not Found (404)

**Problém:** User navštíví neexistující subdomain

**Custom 404 page:**
```yaml
Obsah:
  - "Portfolio Not Found"
  - Friendly message (double-check URL)
  - CTA: "Go Home" button
  - CTA: "Create Your Own" button
  - Help text pro hledání správného URL

Design:
  - Pixel-art cat mascot
  - Consistent s hlavním designem
  - Ne generic Apache 404
```

---

### 3. API Request Failures

**Problém:** Network error, server down, 500 response

**Retry Strategy:**
```yaml
Network errors:
  - Auto-retry 3× s exponential backoff
  - 1s, 2s, 4s delay
  
Client errors (4xx):
  - No retry (bad request, unauthorized)
  - Show specific error message
  
Server errors (5xx):
  - Retry 3×
  - Show "Server error, try again" message
```

**User Feedback:**
```yaml
Loading state:
  - Spinner nebo loading bar
  - "Saving..." message

Error state:
  - Toast notification (ne blocking modal)
  - Specific error messages:
    - 409: "Username already taken"
    - 401: "Session expired, log in again"
    - 500: "Server error, try again"
  - Retry button

Success state:
  - Green checkmark toast
  - "Saved! ✅" message
```

---

### 4. Asset Loading Failures

**Problém:** Character sprite nebo background se nenačte

**Handling:**
```yaml
Detection:
  - Phaser load error event
  - Track které assety failnou

Fallback:
  - Placeholder sprite (basic colored rectangle)
  - Error message overlay
  - "Failed to load assets. Please refresh."
  - Retry button

Prevention:
  - Test all asset URLs při publish
  - Fallback CDN (future)
```

---

### 5. Database Connection Failure

**Problém:** MySQL server nedostupný

**503 Maintenance Page:**
```yaml
Obsah:
  - "We'll be right back"
  - Friendly maintenance message
  - Retry button
  - Status updates link (Twitter)
  - No technical details (user-facing)

Backend:
  - Log critical error
  - Alert admin (email/SMS)
  - Auto-recovery pokud možné
```

---

## 🟡 Non-Critical Errors (Graceful Degradation)

### 6. Analytics Tracking Failure

**Handling:**
```yaml
Silent fail:
  - Analytics NIKDY nesmí shodit app
  - Try-catch všude
  - Log warning (ne error)

Offline queue:
  - Pokud offline, queue events
  - Send při reconnect
```

---

### 7. Preview Mode Issues

**Problém:** postMessage mezi iframe a parent selže

**Fallback:**
```yaml
Option A:
  - Reload iframe s config v query params
  - Slower ale funguje

Option B:
  - localStorage communication
  - Iframe polluje localStorage

User feedback:
  - "Preview reloaded" toast
  - Seamless experience
```

---

### 8. Auto-Save Failures

**Problém:** localStorage full nebo disabled

**Handling:**
```yaml
Detection:
  - Try-catch při save
  - Quota exceeded error

Fallback:
  - Session storage
  - In-memory only (warning user)
  - "Unsaved changes" warning při close

User notification:
  - "Auto-save unavailable" banner
  - Manual save button highlighted
```

---

## 📱 Mobile-Specific

### 9. Touch Controls Not Working

**Fallback:**
```yaml
Detection:
  - No touch events po 5s
  - Timeout check

Alternative:
  - Show keyboard controls hint
  - "Use Arrow Keys or WASD"
  - Virtual D-pad overlay (future)
```

---

## 🔍 Error Logging & Monitoring

### Production Setup

```yaml
Frontend logging:
  - Global error handler (window.onerror)
  - Unhandled promise rejections
  - Custom trackError() funkce
  
Backend logging:
  - PHP error_log
  - Custom log file: /var/log/pixcard/errors.log
  
What to log:
  - Error type & message
  - URL & user agent
  - Timestamp
  - User ID (pokud logged in)
  - Stack trace (dev only)

Future monitoring:
  - Sentry (error tracking service)
  - Email alerts pro critical errors
```

---

## ✅ Error Handling Checklist

### MVP Must-Have:

```yaml
✅ Game load failure → Static fallback
✅ 404 page → Helpful message + CTA
✅ API errors → Retry logic + toast
✅ Database down → 503 page
✅ Asset load fail → Error message + retry
✅ Global error tracking → Log to backend
```

### Post-MVP:

```yaml
⏳ Offline mode detection
⏳ Service worker caching
⏳ Error dashboard (admin)
⏳ User bug reports ("Report issue" button)
⏳ Automatic recovery (background retries)
```

---

## 💬 Error Message Guidelines

### Dobré vs Špatné:

```yaml
✅ Good:
  - "Username already taken. Try: johndoe2, j-doe"
  - "Portfolio not found. Double-check the URL."
  - "Connection error. Check internet and retry."
  - "Session expired. Please log in again."

❌ Bad:
  - "Error 409"
  - "Network request failed"
  - "Unexpected token < in JSON"
  - "null is not an object"
```

### Pravidla:

```yaml
1. Explain what happened (no tech jargon)
2. Suggest next action (retry, go home, contact support)
3. Friendly tone (ne scary)
4. Actionable (button/link pro fix)
```

---

## 🎨 Error UI Components

### Komponenty k vytvoření:

```yaml
1. Toast notification
   - Success, error, info variants
   - Auto-dismiss (3-5s)
   - Close button

2. Error boundary (React-like)
   - Catch component errors
   - Show fallback UI
   - Track to monitoring

3. Loading states
   - Spinner
   - Skeleton screens
   - Progress bar (dlouhé operace)

4. Empty states
   - "No portfolios yet"
   - CTA pro create first

5. Offline banner
   - Detect navigator.onLine
   - Sticky top banner
   - Auto-hide při reconnect
```

---

## 📋 Testing Error Scenarios

### Před launch otestovat:

```yaml
Network:
  - Offline mode (DevTools)
  - Slow 3G (throttling)
  - Request timeout

Assets:
  - Missing sprite files
  - Broken image URLs
  - Large files (timeout)

API:
  - 401, 403, 404, 409, 500 responses
  - Network timeout
  - Malformed JSON

Database:
  - Connection timeout
  - Query errors
  - Constraint violations

Edge cases:
  - localStorage full
  - Cookies disabled
  - JavaScript disabled (basic fallback)
```

---

---

## 📚 See Also

- **Architecture** → [03-architecture.md](./03-architecture.md)
- **MVP scope** → [05-mvp-scope.md](./05-mvp-scope.md)
- **UI Components** → [10-ui-components-TODO.md](./10-ui-components-TODO.md)

---

**Next:** Implementovat error handling systematicky během vývoje
