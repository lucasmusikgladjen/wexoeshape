# Wexoe Shape Exhibition Display

En interaktiv utställningsdisplay byggd för Shape-mässan med ca 300 besökare. Visar Rockwell Automation och partnervideos på en stående digital skylt.

## 🖥️ Skärmspecifikation

- **Format:** 32:9 stående (portrait)
- **Upplösning:** 1488 x 3840 px
- **Enhet:** Android-baserad "digital roll-up" skärm
- **Webbläsare:** Chrome eller Fully Kiosk Browser

## 📐 Layout (uppifrån och ner)

1. **Header** – Wexoe-logga på mörkblå bakgrund (#11325D)
2. **Videospelare** – 16:9 video som loopar, tar full bredd
3. **Logo cluster** – Rockwell Automation centrerad, partners runt om
4. **Videokort** – Klickbara kort för att byta video, aktiv video highlightas

## 📁 Mappstruktur

```
Shape/
├── index.html          # Huvudsidan
├── README.md           # Denna fil
├── claude.md           # Instruktioner för Claude Code
├── Logos/              # Partnerlogotyper (PNG)
│   ├── logo.png        # Wexoe
│   ├── rockwell.png
│   ├── amci.png
│   ├── autonox.png
│   ├── hardy.png
│   ├── hms.png
│   ├── irinox.png
│   ├── prosoft.png
│   └── wittenstein.png
└── Videos/             # Produktvideos (MP4)
    ├── ArmorBlock 5000.mp4
    ├── Emulate RA plant.mp4
    ├── Micro800 Control System.mp4
    ├── Modernize SLC 500 to CompactLogix 5380.mp4
    ├── OTTO Delivers.mp4
    ├── PointMax I_O.mp4
    └── Unlock your Full Robotics Potential.mp4
```

## 🚀 Hosting

Projektet hostas på Vercel via GitHub-integration. Push till `main` triggar automatisk deploy.

## 💻 Lokal utveckling

1. Klona repot
2. Öppna `index.html` i webbläsare
3. Tryck F12 → Device toolbar → Sätt upplösning till 1488 x 3840 för att simulera skärmen

## 🎨 Färger

| Användning | Färgkod |
|------------|---------|
| Header & knappar | `#11325D` |
| Knapp hover | `#1a4a8a` |
| Bakgrund | `#ffffff` |
| Kontrollsektion | `#f5f5f5` |

## ✏️ Vanliga ändringar

### Lägga till en ny video
1. Lägg MP4-filen i `Videos/`
2. Öppna `index.html`
3. Lägg till i `videos`-arrayen i `<script>`-sektionen:
```javascript
{ file: "Nytt filnamn.mp4", title: "Titel på kortet" }
```

### Lägga till en ny partnerlogga
1. Lägg PNG-filen i `Logos/`
2. Lägg till `<img>`-tagg i `.partner-logos`-sektionen

### Ändra header-färg
Sök efter `#11325D` i CSS och byt ut.
