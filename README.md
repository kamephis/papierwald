# Papierwald

Interaktive 3D-Visualisierung, die zeigt, wie viel Wald gedrucktes Papier kostet.
Ein Low-Poly-Wald aus 150 Bäumen (Fichten, Kiefern, Birken), davor ein animierter
Drucker. Für jede angefangenen **8’333 Blatt A4 (80 g/m²)** fällt ein Baum, und der
Wald weicht sichtbar zurück.

## Starten

Es gibt keinen Build-Schritt. Die ganze Anwendung ist eine einzige Datei: `index.html`.

- Lokal: `index.html` im Browser öffnen (Internetverbindung nötig, weil Three.js und die
  Schriften von CDNs geladen werden).
- GitHub Pages: Repository-Einstellungen → Pages → Branch `main`, Ordner `/ (root)`.
  Die Seite ist dann unter `https://<benutzer>.github.io/<repo>/` erreichbar.

## Bedienung

- Anzahl Seiten eingeben und **Drucken** klicken, oder einen Chip wählen
  (1 Ries · 500, 1 Karton · 2’500, 1 Büroplatz / Jahr · 10’000, 100 Büroplätze / Jahr · 1 Mio.).
  Aufträge addieren sich, bis **Wald aufforsten** alles zurücksetzt.
- 3D-Ansicht: Ziehen dreht die Kamera, Mausrad oder Pinch zoomt.
- Angezeigt werden Gesamtzahl, gefällte Bäume, verbleibender Wald, Fortschritt bis zum
  nächsten Baum (im Wald durch einen pulsierenden Ring markiert), Stapelhöhe, Gewicht und
  Anzahl Ries. Übersteigt ein Auftrag den Wald, wird in «Wälder dieser Grösse» umgerechnet.
- Helles und dunkles Farbschema folgen der Systemeinstellung (Tag / Dämmerung).

## Annahmen

| Grösse | Wert |
| --- | --- |
| Blatt pro Baum | 8’333 (Faustregel, ca. 17 Ries) |
| Gewicht pro Blatt | 5 g (A4, 80 g/m²) |
| Dicke pro Blatt | 0,1 mm (500 Blatt ≈ 5 cm) |
| Bäume im Wald | 150 |

Der Wert «Blatt pro Baum» schwankt je nach Baumart, Alter und Verfahren stark;
Recyclingfasern sind nicht berücksichtigt. Die Konstanten stehen am Anfang des Skripts
in `index.html` (`SHEETS_PER_TREE`, `TREE_COUNT`) und lassen sich dort anpassen.

## Technik

- [Three.js r128](https://threejs.org/) über cdnjs (WebGL, Schatten, Nebel)
- Schriften «Bricolage Grotesque» und «Manrope» über Google Fonts
- Reines HTML/CSS/JS, keine Abhängigkeiten zum Installieren
