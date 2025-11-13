# Dark Escape House - 3D Horror Escape Game

Ein 3D First-Person Horror-Escape-Game für Android-Handys, gebaut mit Three.js r128.

## 🎮 Features (Commit 1)

### Aktuell implementiert:
- ✅ **9 Räume** mit unterschiedlicher Geometrie und Atmosphäre
  - Schlafzimmer (Startpunkt)
  - Flur (zentrale Hub)
  - Küche
  - Wohnzimmer
  - Badezimmer
  - Treppe
  - Keller
  - Käfig
  - Dachboden

- ✅ **Touch-Controls**
  - Joystick links unten (Bewegung in alle Richtungen)
  - Rechts wischen (Kamera-Rotation)
  - ✋-Button rechts unten (Interaktion mit Objekten)

- ✅ **HUD**
  - Leben/Hunger/Durst Bars
  - Raum-Anzeige
  - Zeit-Anzeige
  - FPS Counter

- ✅ **Survival-Mechanik (Basic)**
  - Hunger & Durst sinken kontinuierlich
  - Damage wenn Stats auf 0

- ✅ **Raum-Navigation**
  - Türen als interagierbare Objekte
  - Raum-Wechsel durch Türen (wenn nicht verschlossen)

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

- [x] **Commit 1:** Alle 9 Räume mit Basic-Geometrie
- [ ] **Commit 2:** Türen-System & Navigation erweitern
- [ ] **Commit 3:** Items platzieren
- [ ] **Commit 4:** Inventar-UI & Item-Usage
- [ ] **Commit 5:** NPC-System (1 NPC)
- [ ] **Commit 6:** Alle 3 NPCs + Encounters
- [ ] **Commit 7:** Hausaufgaben-Minigames
- [ ] **Commit 8:** Licht-System + Batterie
- [ ] **Commit 9:** Win/Lose Conditions
- [ ] **Commit 10:** Polish + Bugfixes

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
- [ ] Läuft auf Chrome Android
- [x] Touch-Controls funktionieren
- [x] FPS >= 30
- [ ] Items können aufgehoben werden (noch nicht implementiert)
- [ ] NPCs bewegen sich (noch nicht implementiert)
- [x] Türen interagierbar
- [ ] Inventar funktioniert (noch nicht implementiert)
- [x] Stats sinken
- [ ] Win/Lose triggert (noch nicht implementiert)

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
