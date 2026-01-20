# Claude Code Instructions

## Projektöversikt

Detta är en interaktiv utställningsdisplay för Wexoe (svensk industriautomations- och IT-infrastrukturdistributör) som visas på Shape-mässan. Wexoe är Rockwell Automations huvudpartner i Sverige.

## Teknisk kontext

- **Single-page HTML** – All kod (HTML, CSS, JS) ligger i `index.html`
- **Ingen build-process** – Rå HTML som serveras direkt
- **Offline-kapabel** – Alla assets är lokala (inga CDN-beroenden)
- **Hosting:** Vercel (auto-deploy från GitHub main branch)

## Målskärm

- **Typ:** Stående Android-skärm (digital roll-up/totem)
- **Upplösning:** 1488 x 3840 px (32:9 portrait)
- **Webbläsare:** Chrome eller Fully Kiosk Browser
- **Input:** Touchscreen

## Design-regler

1. **Videon måste behålla 16:9** – Använd `aspect-ratio: 16/9` och `object-fit: contain` för att undvika svarta kanter eller beskärning
2. **Ingen scrollning** – Allt innehåll måste synas utan scroll (overflow: hidden)
3. **Touch-vänligt** – Knappar/kort ska vara minst 44px klickyta
4. **Wexoe-blå:** `#11325D` är primärfärgen
5. **Videor är mutade** – Mässmiljö, `muted` attributet är kritiskt

## Filstruktur

```
index.html      # All kod här
Logos/          # PNG-logotyper, filnamn = företagsnamn.png (lowercase)
Videos/         # MP4-videor, exakta filnamn viktiga (se videos-array i JS)
```

## Viktiga kodsektioner i index.html

### CSS-sektioner (i ordning)
- Reset och grundläggande body-styling
- `.container` – Flexbox kolumn för hela layouten
- `.header` – Wexoe-logga
- `.video-section` – Videospelaren
- `.logo-cluster` – Rockwell + partners
- `.video-controls` – Videokorten längst ner

### JavaScript
- `videos` array – Lista med {file, title} för varje video
- `createVideoCards()` – Genererar DOM för videokort
- `playVideo(index)` – Byter video och uppdaterar aktiv-status

## Vanliga uppdateringsscenarier

### Lägg till video
1. Lägg till objekt i `videos`-arrayen
2. Se till att filnamnet matchar exakt (case-sensitive)

### Lägg till partnerlogga
1. Lägg till `<img src="Logos/namn.png" alt="Namn">` i `.partner-logos`
2. Om >8 loggor, överväg att justera `grid-template-columns`

### Ändra proportioner
Layouten använder flexbox med `flex: 1` för logo-cluster (tar kvarvarande utrymme). Header, video och controls har `flex-shrink: 0` och fasta/aspect-ratio-baserade höjder.

### Testa lokalt
Använd Chrome DevTools device toolbar med 1488x3840 för att simulera målskärmen.

## Kontaktperson

Lucas på Wexoe (marknad) – hanterar marknadsautomation, CRM, web och content.
