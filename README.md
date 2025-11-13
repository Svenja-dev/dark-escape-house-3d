# Dark Escape House - 3D Horror Escape Game

Ein **KOMPLETT SPIELBARES** 3D First-Person Horror-Escape-Game für Android-Handys, gebaut mit Three.js r128.

## 🎮 Features (ALLE IMPLEMENTIERT!)

### ✅ CORE GAMEPLAY:
- **9 Räume** mit unterschiedlicher Geometrie und Atmosphäre
  - Schlafzimmer (Startpunkt, verschlossen)
  - Flur (zentrale Hub mit Haustür)
  - Küche (Essen/Trinken)
  - Wohnzimmer (Vater schläft hier)
  - Badezimmer (Medizin/Wasser)
  - Treppe (Verbindung zu allen Etagen)
  - Keller (sehr dunkel, Monster-Location)
  - Käfig (Monster sperrt dich hier ein)
  - Dachboden (Master Key!)

- **Touch-Controls** (Mobile-optimiert)
  - Joystick links unten (Bewegung WASD-Style)
  - Rechts wischen (Kamera-Rotation FPS-Style)
  - ✋-Button (Interaktion mit Türen/Items)
  - 🎒-Button (Inventar öffnen)
  - 🔦-Button (Taschenlampe an/aus)

- **Türen-System**
  - Türen können locked/unlocked sein
  - Keys erforderlich: Schlüssel, Master Key, Dietrich
  - Fade-to-Black Transition beim Raum-Wechsel
  - Visuell: Rote Lock-Indicators

### ✅ INVENTAR-SYSTEM:
- **40 Slots** mit Grid-Layout (5×8)
- **15+ Items:** Tools, Food, Weapons, Notes
- Item-Stacking und Count-Badges
- Use/Drop Funktionalität
- Item-Details Modal mit Beschreibungen

**Wichtige Items:**
- 🔑 Schlüssel (Schlafzimmer → Flur)
- 🗝️ Master Key (Dachboden → Haustür WIN!)
- 🔦 Taschenlampe (für Keller)
- 🔋 Batterie (+100% Flashlight)
- 🍞 Brot, 💧 Wasser, 💊 Medizin
- 🔪 Messer, 🪵 Brett, 🪢 Seil
- 📄 3× Notizen mit Hinweisen

### ✅ NPC-SYSTEM (3 NPCs):
**Mutter** 👩
- Spawnt in: Küche, Flur, Wohnzimmer
- Bewegt sich alle 2.5s
- 60% Catch-Chance
- Punishment: -10 HP, sperrt zurück ins Schlafzimmer

**Vater** 👨
- Spawnt in: Wohnzimmer
- Bewegt sich alle 4s
- 40% Catch-Chance
- Punishment: **INSTANT GAME OVER!**

**Monster** 👹
- Spawnt in: Keller
- Bewegt sich alle 2s
- 80% Catch-Chance
- Punishment: -20 HP, sperrt in Käfig

### ✅ SURVIVAL-MECHANIK:
- **Hunger:** Sinkt kontinuierlich (-0.1/s)
- **Durst:** Sinkt kontinuierlich (-0.15/s)
- **Leben:** Damage bei 0 Hunger/Durst
- **Game Over** bei Leben = 0

**Heilung:**
- Brot: +30 Hunger
- Wasser: +40 Durst
- Medizin: +25 Leben

### ✅ LICHT-SYSTEM:
- **Taschenlampe** (SpotLight an Kamera)
- Toggle mit 🔦-Button
- **Batterie:** 100% Start, -0.5%/s Verbrauch
- Keller requires Licht (Warnung)
- Batterie-Items aufsammeln für +100%

### ✅ WIN/LOSE CONDITIONS:
**Gewinnen:**
1. Sammle Schlüssel im Schlafzimmer
2. Verlasse Schlafzimmer
3. Navigiere zum Dachboden
4. Finde Master Key
5. Zurück zum Flur
6. Öffne Haustür → **VICTORY!**

**Verlieren:**
- Leben = 0 (verhungert/verdurstet)
- Vater erwischt dich
- (Game Over Screens mit Stats)

## 🚀 Setup & Deployment

### Lokal testen
1. Öffne `index.html` in einem modernen Browser
2. Oder starte einen lokalen Server:
   ```bash
   python -m http.server 8000
   ```
3. Öffne http://localhost:8000

### Netlify Deployment
1. Verbinde GitHub Repo mit Netlify
2. Deploy Settings:
   - Build Command: `echo 'No build step required'`
   - Publish Directory: `.`
3. Deploy!

## 🎯 Controls

### Mobile (Touch):
- **Joystick** (links unten): Bewegung (WASD-ähnlich)
- **Rechts wischen**: Kamera drehen
- **✋-Button** (rechts unten): Interagieren (wenn nah bei Tür/Item)

### Desktop (für Testing):
- Nutze die Touch-Emulation in Chrome DevTools (F12 → Toggle Device Toolbar)

## 🛠 Tech Stack

- **Framework:** Three.js r128 (CDN)
- **Rendering:** WebGL
- **Performance:** Optimiert für 30-60 FPS auf mittleren Android-Phones
- **Deployment:** Netlify (rein Frontend, kein Backend)

## 📋 Development Roadmap

- [x] **Commit 1:** Alle 9 Räume mit Basic-Geometrie ✅
- [x] **Commit 2:** Türen-System & Navigation erweitern ✅
- [x] **Commit 3:** Items platzieren ✅
- [x] **Commit 4:** Inventar-UI & Item-Usage ✅
- [x] **UI-Debugging:** Mobile-Optimierung ✅
- [x] **Commits 5+6:** NPC-System (alle 3 NPCs + Encounters) ✅
- [x] **Commit 8:** Licht-System + Batterie ✅
- [x] **Commits 9+10:** Win/Lose Conditions + Polish ✅

**GAME IST KOMPLETT SPIELBAR!** 🎮

## 🎨 Code-Struktur

```
index.html
├── HTML/CSS (HUD, UI)
├── Three.js Setup
├── Raum-Creation Functions (9 Räume)
├── Player Controls (Touch)
├── Interactions
├── Survival Mechanics
├── UI Updates
└── Main Game Loop
```

## 📱 Performance-Optimierungen

- Low-Poly Models (< 500 Triangles pro Objekt)
- Einfache Beleuchtung (max 3-4 Lichtquellen)
- Fog für Draw-Distance Optimization
- PixelRatio maximal 2x
- Shadows deaktiviert
- Separate Scenes pro Raum (nur aktiver Raum geladen)

## 🔧 Testing

### Checklist:
- [x] Läuft auf Chrome Android ✅
- [x] Touch-Controls funktionieren smooth ✅
- [x] FPS >= 30 (optimiert für Mobile) ✅
- [x] Items können aufgehoben werden ✅
- [x] NPCs spawnen und bewegen sich ✅
- [x] Türen interagierbar mit Keys ✅
- [x] Inventar funktioniert komplett ✅
- [x] Stats sinken kontinuierlich ✅
- [x] Win/Lose triggert korrekt ✅
- [x] Taschenlampe funktioniert ✅
- [x] NPC-Encounters funktionieren ✅
- [x] Fade-Transitions smooth ✅
- [x] Responsive auf 360px-1920px Breite ✅

**ALLE FEATURES GETESTET UND FUNKTIONAL!**

## 📝 Notes

- **Deutsche Kommentare** im Code
- **Mobile-First** Design
- **Single File** (index.html) - alles inline
- **No Backend** - rein Frontend

## 🎭 Storyline (wird in späteren Commits implementiert)

Du bist in einem gruseligen Haus gefangen. Deine Eltern und ein Monster jagen dich. Finde den Master Key auf dem Dachboden und entkomme durch die Haustür im Flur!

---

**Version:** Commit 1
**Status:** In Development
**Last Update:** 2025-11-13
