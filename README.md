# Transcribe Tool

Een **privacy-first transcriptietool** die audio en video omzet naar tekst — volledig in de browser, zonder server en zonder API-sleutel. Bedoeld voor onderzoekers, docenten en studenten die opnames willen uittypen zonder dat hun bestanden de eigen computer verlaten.

Onderdeel van de tools van **AIGovernanceofficer.nl**.

---

## Inhoud

- [Wat het doet](#wat-het-doet)
- [Hoe het werkt](#hoe-het-werkt)
- [Vereisten](#vereisten)
- [Gebruik](#gebruik)
- [Online zetten](#online-zetten)
- [Toevoegen aan de app store](#toevoegen-aan-de-app-store)
- [Privacy](#privacy)
- [Licentie](#licentie)

---

## Wat het doet

- Audio- of videobestand uploaden (slepen of bladeren)
- Automatische spraak-naar-tekst-transcriptie
- Live meelezen terwijl de tekst verschijnt
- Een geschiedenis van eerdere transcripties in de browser
- Transcriptie downloaden als tekstbestand

---

## Hoe het werkt

De tool gebruikt een AI-spraakmodel (Whisper) dat **lokaal in de browser** draait via WebAssembly/WebGPU. Het audiobestand wordt dus niet naar een server gestuurd; alle verwerking gebeurt op het apparaat van de gebruiker zelf.

De eerste keer dat iemand de tool gebruikt, wordt het model eenmalig in de browser gedownload. Daarna blijft het in de browsercache staan, zodat een volgende keer sneller gaat.

---

## Vereisten

- Een moderne browser. **Chrome of Edge** werken het best (die ondersteunen WebGPU, wat de tool als eerste probeert). In andere browsers valt de tool terug op de langzamere processor-modus.
- Een **internetverbinding** bij het eerste gebruik, om het model te downloaden.
- Voldoende werkgeheugen. Het model is groot; op apparaten met weinig geheugen kan de eerste keer traag zijn.

---

## Gebruik

1. Open de tool in de browser.
2. Sleep een audio- of videobestand naar het uploadvak, of klik om te bladeren.
3. Wacht tot het model is geladen (alleen de eerste keer) en de transcriptie verschijnt.
4. Download de tekst of bekijk eerdere transcripties in de geschiedenis.

---

## Online zetten

De map met gebouwde bestanden (`index.html`, de map `assets`, en `favicon.svg` / `icons.svg`) is een statische website. Zo publiceer je hem op GitHub Pages:

1. Upload **de inhoud** van de map (niet een zip-bestand) naar een repository.
2. Ga naar **Settings → Pages**, kies *Deploy from a branch*, branch `main`, map `/ (root)`.
3. Wacht 1–2 minuten; de live-link verschijnt bovenaan de Pages-instellingen.

De paden zijn relatief, dus het werkt ongeacht de naam van de repo of de submap waarin je het plaatst.

---

## Toevoegen aan de app store

Wil je de tool als app in je bestaande app store opnemen:

1. Zet de inhoud van de tool in een submap, bijvoorbeeld `transcribe/`.
2. Voeg in de `APPS`-lijst van je app store een blokje toe dat ernaar verwijst:

```javascript
{ name:"Transcribe Tool", cat:"Onderzoek", icon:"🎙️", bg:"var(--peach)",
  desc:"Privacy-first transcriptietool — zet audio en video lokaal om naar tekst.",
  url:"transcribe/index.html", status:"live" },
```

De "Terug"-knop in de tool gaat een stap terug in de browsergeschiedenis, dus terug naar de app store.

---

## Privacy

De tool is privacyvriendelijk van opzet: audio- en videobestanden worden **lokaal in de browser** verwerkt en niet naar een server verstuurd of daar opgeslagen. Transcripties en geschiedenis blijven in de browser van de gebruiker.

Let op: het AI-model wordt bij het eerste gebruik wel van het internet gedownload. Daarna werkt de verwerking lokaal.

---

## Licentie

[![Licentie: CC BY-NC-ND 4.0](https://img.shields.io/badge/Licentie-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.nl)

© 2026 **AIGovernanceofficer.nl**

Dit werk valt onder een **Creative Commons Naamsvermelding-NietCommercieel-GeenAfgeleideWerken 4.0 Internationaal-licentie** (CC BY-NC-ND 4.0).

- 🏷️ **Naamsvermelding** — vermeld de maker en plaats een link naar de licentie.
- 🚫 **NietCommercieel** — niet voor commerciële doeleinden gebruiken.
- 🚫 **GeenAfgeleideWerken** — gewijzigde versies niet verspreiden.

Volledige tekst: <https://creativecommons.org/licenses/by-nc-nd/4.0/legalcode.nl>
