# 🪐 Siddhantic Sky-Map · Navagraha Dṛśya

> An interactive sky-map powered by **classical Indian astronomy (Siddhānta)** — computing true planetary positions using the same mathematics found in texts like the *Sūrya Siddhānta*, written over 1,500 years ago.

---

## ✨ Features

| Feature | Description |
|---|---|
| **Ahargana Time Engine** | Calculates the civil day count from the Kali Yuga epoch (18 Feb 3102 BCE) for any chosen date |
| **Madhyama (Mean Motion)** | Derives mean planetary longitudes using Mahāyuga revolution constants |
| **Spaṣṭa (True Longitude)** | Applies two-epicycle corrections (Manda + Śīghra) to get the true position of each graha |
| **Interactive Sky-Map** | A circular canvas rendering all 9 planets (Navagraha) on the zodiac wheel |
| **Navagraha Cards** | Live cards showing the longitude and rāśi of each planet |
| **Birth Chart Predictions** | Enter a date of birth to get a personalised planetary reading based on Siddhāntic positions |

---

## 🔭 The Nine Grahas (Navagraha)

| Glyph | Sanskrit | Western Equivalent |
|:---:|---|---|
| ☀ | Sūrya | Sun |
| ☽ | Chandra | Moon |
| ♂ | Maṅgala | Mars |
| ☿ | Budha | Mercury |
| ♃ | Guru | Jupiter |
| ♀ | Śukra | Venus |
| ♄ | Śani | Saturn |
| ☊ | Rāhu | North Lunar Node |
| ☋ | Ketu | South Lunar Node |

---

## 📂 Project Structure

```
IKS Project/
├── index.html          # Main application shell — layout, panels, and sky-map canvas
├── style.css           # Dark-theme styling with gold accents
└── js/
    ├── ahargana.js     # Time Engine — calculates day count from Kali Yuga epoch
    ├── madhyama.js     # Mean Motion — computes mean longitudes via revolution constants
    ├── spashta.js      # Correction Engine — applies Manda & Śīghra epicycle corrections
    ├── predictions.js  # Birth Chart — interprets planetary positions for a birth date
    ├── skymap.js       # Canvas Renderer — draws the zodiac wheel and planet glyphs
    └── main.js         # Bootstrap — wires all modules together, handles UI events
```

> **Script load order matters.** The HTML loads scripts in dependency order:  
> `ahargana` → `madhyama` → `spashta` → `predictions` → `skymap` → `main`

---

## 🚀 Getting Started

This is a **pure front-end application** — no server, build tool, or installation required.

1. **Clone or download** this repository.
2. Open `index.html` in any modern web browser (Chrome, Firefox, Edge).
3. Use the **date picker** to choose any date, or click **◉ NOW** to load today's sky.
4. Click any planet button or glyph on the map to inspect its details.
5. Scroll to the **Birth Chart Predictions** section and enter a date of birth to get a personalised reading.

---

## 🧮 How the Astronomy Works

The calculations follow the classical Siddhāntic pipeline:

```
Date Input
    ↓
Ahargana  — Convert the Gregorian date to a count of days since the
            Kali Yuga epoch (Julian Day Number method)
    ↓
Madhyama  — Multiply Ahargana by each planet's daily mean motion
            (derived from Mahāyuga revolution counts) to get mean longitude
    ↓
Spaṣṭa   — Apply the Manda (slow, centre-of-orbit) epicycle correction,
            then for inferior/superior planets apply the Śīghra (fast,
            synodic) epicycle correction to get the true longitude
    ↓
Display   — Convert longitude → Rāśi (sign) + Nakṣatra + degree in sign
```

---

## 🎨 UI Overview

The app is divided into three panels and one full-width section:

- **Left Panel** — Time Engine controls (date picker, NOW button), Ahargana counter, and Navagraha summary cards.
- **Centre** — The zodiac wheel canvas. Aries sits at the top; positions increase counter-clockwise (traditional Siddhāntic convention).
- **Right Panel** — Selected planet detail view, planet selector buttons, colour legend, and methodology notes.
- **Bottom Section** — Birth Chart Predictions panel with a date-of-birth input and a full planetary interpretation table.

---

## 🏛️ Background — Indian Knowledge Systems (IKS)

This project is part of an **Indian Knowledge Systems (IKS)** initiative. The Siddhānta tradition of mathematical astronomy is one of India's most significant scientific contributions. Texts such as the *Sūrya Siddhānta*, *Āryabhaṭīya*, and *Brahmasphutasiddhānta* described planetary motion with remarkable accuracy — centuries before equivalent models appeared elsewhere. This application makes those algorithms accessible and interactive for a modern audience.

---

## 📜 License

This project is for **educational purposes** as part of an IKS curriculum. Feel free to study, adapt, and share with attribution.
