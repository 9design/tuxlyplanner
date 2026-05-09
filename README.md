# Tuxly Planner

Een interactieve dagplanner als Windows achtergrond via [Lively Wallpaper](https://www.livelywallpaper.net/).

Gebouwd door [Van Der Ven Webdesign](https://www.jvdven.com).

## ✨ Features

- **Dag templates** — Doordeweeks, Weekend, Vakantie en meer. Zelf aanmaken via `+`
- **Kanban bord** — kaarten slepen tussen kolommen, volgorde aanpassen
- **Afvinken** — taken afvinken met statistieken
- **Bewerken** — dubbelklik op een kaarttitel om te bewerken
- **Toevoegen & verwijderen** — eigen kaarten per kolom
- **Notities** — notitieblok per dag
- **Right now** — ziet automatisch welk blok nu actief is
- **Klok + dagvoortgang** — live klok met progressiebalk
- **Cloud opslag** — via Supabase met localStorage als fallback
- **Reset dag** — fris begin elke ochtend

## 🚀 Installatie

### 1. Lively Wallpaper installeren
Download gratis via de [Microsoft Store](https://apps.microsoft.com/detail/9ntm2qc6qws7) of [GitHub](https://github.com/rocksdanister/lively).

### 2. Eigen Supabase database koppelen (aanbevolen)
Zie [docs/supabase-setup.md](docs/supabase-setup.md) voor stap-voor-stap instructies.

Zonder Supabase werkt de app ook via localStorage, maar data is dan niet persistent na een herstart van Lively.

### 3. Wallpaper instellen
1. Download `index.html`
2. Open Lively Wallpaper
3. Sleep `index.html` in het Lively venster
4. Klaar

## ⚙️ Aanpassen

### Eigen Supabase koppelen
Open `index.html` en vervang bovenin het script:

```js
const SB_URL = 'https://jouw-project-id.supabase.co';
const SB_KEY = 'jouw-anon-key';
```

### Eigen templates aanpassen
Pas de `DEFAULT_TEMPLATES` array aan in het script voor je eigen dagstructuur.

## 🔒 Beveiliging

> **Let op:** gebruik geen wachtwoorden of gevoelige informatie in de notities. De app gebruikt een publieke anon key om data op te slaan — dit is veilig genoeg voor dagelijkse taken en notities, maar niet voor privacygevoelige data.

De huidige versie gebruikt een UUID per gebruiker voor data-isolatie. Echte authenticatie (login) staat op de roadmap.

## 🗺 Roadmap

- [ ] Supabase Auth — echte gebruikersaccounts met login
- [ ] Row Level Security op basis van auth.uid()
- [ ] Google Calendar sync — afspraken van vandaag automatisch als kaarten
- [ ] Kolommen per template aanpasbaar
- [ ] Weekoverzicht — wat afgevinkt per dag
- [ ] Mobiele versie / browser versie

## 🛠 Tech

- Vanilla HTML/CSS/JS — geen build stap, geen dependencies
- [Supabase](https://supabase.com) voor cloud opslag
- [Inter](https://rsms.me/inter/) font via Google Fonts
- Werkt in elke moderne Chromium browser en Lively Wallpaper

## 📄 Licentie

MIT — gebruik, fork en pas aan naar eigen wens.

---

Made with ☕ by [Van Der Ven Webdesign](https://www.jvdven.com)
