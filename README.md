# Aurum Jet, a free Power BI report with no custom visuals

Aurum Jet is a fictional private jet operator. This is its full Power BI project: a Dashboard and a Flights page, a filter drawer, a New booking dialog, Light and Dark mode, native animations and photos that follow the data. 119 visuals, 168 DAX measures and not a single custom visual: no React, no JavaScript, nothing to install.

It was built from image mockups by an AI agent (Claude Code) working through the Power BI Desktop Bridge, then reviewed page by page.

Made by Omar Arrim, founder of ChartCraft: https://chartcraft.io

## Open it in 3 steps

You need Power BI Desktop for Windows, a 2026 release.

1. Unzip this folder to `C:\AurumJet`.
2. Open `AurumJet.pbip`.
3. Click **Refresh**. The data loads from the `data` folder.

Unzipped somewhere else? In Power BI Desktop, go to **Transform data > Edit parameters** and set `DossierDonnees` to the full path of the `data` folder, ending with a backslash (for example `D:\Projects\AurumJet\data\`). Then refresh.

In Desktop, hold **Ctrl** to click the report buttons (menu, filter drawer, New booking). Once published to the Power BI Service, a simple click works.

## What's inside

| Path | Content |
|---|---|
| `AurumJet.pbip` | The file to open |
| `AurumJet.Report/` | The report, in PBIR format (one JSON file per visual), with its theme, images and bookmarks |
| `AurumJet.SemanticModel/` | The model, in TMDL format: 17 tables, 5 relationships, 168 measures |
| `data/` | 7 Parquet files: 4,339 flights, 283 cancellations, 350 clients, 14 jets of 4 models, 35 airports |
| `images/` | The images of the report as separate files: the jet photos (each model, Light and Dark), the client portraits, the Flights page photos, the route map and the logo |

The report has two pages and three hidden ones: `Filters light` and `Filters dark` (the drawer opened by the funnel button, one per theme) and `Recette`, a check page with the key numbers.

## How it works

- **Every card is a DAX measure.** Each measure returns an SVG image, shown in a native card visual. The animations (bars that grow, the gauge, the jet flying along its route) are plain SVG animations.
- **Light and Dark.** Every colour is a measure that reads the Light / Dark slicer, so one click restyles the whole report.
- **Photos that follow the data.** The jet photos and the client portraits are stored in the model as text, split into chunks of 30,000 characters, and joined back by a measure. Pick an aircraft or switch the theme, and the photo changes.
- **Interactivity with native visuals.** Period pills, a flight picker, aircraft chips and the mode toggles are button slicers placed on top of the drawings. The filter drawer is a hidden page, the New booking dialog is a pair of bookmarks.

## Good to know

- The brand, the clients and every number are fictional. The data was generated, then calibrated to match the mockups.
- The report's "now" is fixed at **15 October 2026, 10:43**: "today", "this month" and the flight in progress are computed from that moment.
- The photos and portraits were generated with AI.
- The New booking dialog is a demo of where a Power Apps form would fit. It writes no data.

## License and credits

Aurum Jet is released under the [MIT License](LICENSE): use it, adapt it and share it, including in commercial and client work. Keep the copyright notice.

A few parts come from third parties and keep their own licences, listed in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md):

- Icons: [Lucide](https://lucide.dev), ISC License (see `LICENSES/lucide.txt`).
- France map: drawn from [france-geojson](https://github.com/gregoiredavid/france-geojson) (Etalab Open Licence 2.0) and the World Borders Dataset by thematicmapping.org (CC BY-SA 3.0). The map image is shared under CC BY-SA 3.0.
- World land of the Flights page: [Natural Earth](https://www.naturalearthdata.com), public domain.

---

# Aurum Jet, un rapport Power BI gratuit sans visuel personnalisé

Aurum Jet est une compagnie fictive de jets privés. Voici son projet Power BI complet : une page Dashboard et une page Flights, un tiroir de filtres, une boîte de dialogue New booking, un mode clair et un mode sombre, des animations natives et des photos qui suivent la donnée. 119 visuels, 168 mesures DAX et aucun visuel personnalisé : pas de React, pas de JavaScript, rien à installer.

Il a été construit à partir de maquettes par un agent IA (Claude Code) au travers du Power BI Desktop Bridge, puis relu page par page.

## L'ouvrir en 3 étapes

Il faut Power BI Desktop pour Windows, une version de 2026.

1. Décompressez ce dossier dans `C:\AurumJet`.
2. Ouvrez `AurumJet.pbip`.
3. Cliquez sur **Actualiser**. Les données se chargent depuis le dossier `data`.

Décompressé ailleurs ? Dans Power BI Desktop, ouvrez **Transformer les données > Modifier les paramètres** et donnez à `DossierDonnees` le chemin complet du dossier `data`, terminé par une barre oblique inverse (par exemple `D:\Projets\AurumJet\data\`). Puis actualisez.

Dans Desktop, maintenez **Ctrl** pour cliquer sur les boutons du rapport. Une fois publié dans le service Power BI, un simple clic suffit.

## Bon à savoir

- La marque, les clients et tous les chiffres sont fictifs.
- Le « maintenant » du rapport est fixé au **15 octobre 2026, 10 h 43**.
- Les photos et les portraits ont été générés par IA.
- Le dossier `images/` contient les images du rapport en fichiers séparés.
- Licence MIT (fichier `LICENSE`) : libre d'utiliser, d'adapter et de partager, y compris dans un travail commercial ou pour un client, en gardant la mention de copyright. Les icônes et la carte de France gardent leur propre licence (`THIRD-PARTY-NOTICES.md`).
