# Lokales Hosting & Anpassung deiner Website

Dieses Paket enthält eine lokal lauffähige Version deiner gespeicherten Website.
Ich habe folgende Anpassungen vorgenommen:

1. **Externe Template-CSS entfernt** (`/templates/tricoma_energy/css/tricoma_energy.css`), da diese lokal nicht vorhanden ist.
2. **Hero-Bild** `/templates/tricoma_energy/Labels/hero2.png` wurde auf ein vorhandenes Bild geändert: `./test_files/Software_Nutzung.png`.
3. Eine **`custom.css`** wurde eingebunden (`./test_files/custom.css`), damit du Designänderungen zentral machen kannst.

## So startest du die Seite lokal

### Option A – Python (ohne Installation von Tools)
1. Öffne ein Terminal im Ordner: `/mnt/data/energy_site_local/_energy_tmp (3)/energy_tmp`
2. Starte einen kleinen Webserver:
   ```bash
   python -m http.server 8000
   ```
3. Öffne im Browser: http://localhost:8000/index_local.html

### Option B – VS Code Live Server
1. Ordner `/mnt/data/energy_site_local/_energy_tmp (3)/energy_tmp` in VS Code öffnen
2. Erweiterung **Live Server** installieren
3. Rechtsklick auf `index_local.html` → **Open with Live Server**

## Online Hosten (statische Seite)
- **GitHub Pages** (kostenlos), **Netlify** (sehr einfaches Drag&Drop) oder klassisches **Webhosting** (z. B. IONOS, All-inkl).
- Lade den Inhalt aus `/mnt/data/energy_site_local/_energy_tmp (3)/energy_tmp` hoch. Als Startdatei kannst du `index_local.html` oder `test2.html` festlegen.

## Styling & Inhalte anpassen

- Farben/Abstände/Buttons: in **`test_files/custom.css`** ändern (empfohlen).
- Texte/Struktur: in **`index_local.html`** (oder `test2.html`) bearbeiten.
- Bilder: unter **`test_files/`** austauschen oder neue ablegen und die `src`-Pfade im HTML anpassen.

### Häufige Stolpersteine und Lösungen

- **Fehlende Bilder/CSS mit `/templates/...`-Pfad** → diese stammen von der Online-Seite. Ersetze die Pfade durch lokale Dateien unter `./test_files/...` oder lade die Originaldateien herunter und speichere sie lokal.
- **Schriften (Google Fonts)** → bleiben online über `fonts.googleapis.com` erreichbar. Wenn du komplett offline sein willst, lade die Schriftfamilie herunter und binde sie lokal ein.
- **JS von CDNs (jQuery, Splide, Typed.js)** → funktionieren online. Für Offline-Betrieb kannst du die `.js`-Dateien herunterladen und lokal referenzieren.

## Tipps zum sauberen Arbeiten

- Bearbeite **nur `custom.css`** für Design: so bleibt ein Update der Originaldateien einfach.
- Nutze **Semver-Kommentare** in `custom.css` (z. B. `/* v1.0 - Buttonradius geändert */`), damit du Änderungen rückverfolgen kannst.
- Lege ein `assets/`-Unterverzeichnis an, wenn du viele eigene Bilder/Logos ergänzen möchtest.

Viel Erfolg! Wenn du willst, passe ich dir Farben, Logo und Hero-Section direkt nach deinen CI-Vorgaben an.