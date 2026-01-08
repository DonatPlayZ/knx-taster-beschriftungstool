# KNX Taster Beschriftungstool

Tool zur Konvertierung von Excel-Dateien für KNX-Beschriftungen und PDF-Generierung.

**Entwickelt für Gira Tastsensoren 3** - Optional auch für ältere Modelle verwendbar, da die Label-Größe bearbeitet werden kann.

## ✨ Features

### 🔄 Excel Konvertierung (Kann einzeln verwendet werden!)

**Besonders nützlich für Dokumentation!**

Das Excel-Konvertierungstool kann **einzeln** verwendet werden, um aus einem ETS-Report die Tastsensoren mit den jeweiligen Wippen und Funktionen/Beschriftungen zu exportieren. Perfekt für:
- Dokumentation von KNX-Installationen
- Übersicht über alle Tastsensoren und deren Funktionen
- Export von Wippen-Positionen und Beschriftungen

### 📄 PDF Generator

- **Automatische PDF-Erstellung**: Erstellt PDF-Beschriftungen mit Icons für verschiedene Varianten
- **Varianten-Verwaltung**: Anpassbare Varianten und Kategorien (z.B. Licht, Jalousie, etc.)
- **Icon-Zuordnung**: Flexible SVG-Icon-Zuordnung für verschiedene Varianten
  - **Gira-Icons verfügbar**: Offizielle Icons können von [Gira heruntergeladen](https://partner.gira.de/service/download/index.html?id=1040&lang=de) werden (WMF → SVG Konvertierung erforderlich)
  - **Ohne Icons möglich**: Das Tool funktioniert auch ohne Icons - PDFs werden dann nur mit Text erstellt
- **Automatische Erkennung**: Erkennt automatisch Tastsensoren (1-fach, 2-fach, 3-fach, 4-fach, etc.)
- **Optimierte Etikettengrößen**: Etikettengrößen sind um 0,5mm reduziert, damit sie besser ins Beschriftungsfeld passen
- **Hebelschneider-optimiert**: Die erstellte Beschriftung ist so angeordnet, dass sie mit einem Hebelschneider leicht geschnitten werden kann

**Beispiel:** Siehe PDF `Beschriftung_3fach.pdf` als Beispiel für die Anordnung.

## 📥 Download

Die neueste Version finden Sie in den [Releases](https://github.com/DonatPlayZ/knx-taster-beschriftungstool/releases/latest).

## 🚀 Installation

1. Laden Sie die neueste Release-Version herunter
2. Entpacken Sie die ZIP-Datei
3. Führen Sie die EXE-Dateien aus:
   - `Excel Konvertierungstool.exe` - Excel Konvertierung
   - `Beschriftungstool.exe` - PDF Generator

## 💻 Systemanforderungen

- Windows 10 oder höher
- ETS5 oder ETS6 (getestet mit ETS6)
- Microsoft Excel (für die Vorbereitung)
- Keine zusätzliche Installation erforderlich (alle Abhängigkeiten sind enthalten)

## 📖 Verwendung

### Schritt 1: Daten aus ETS exportieren

1. Öffnen Sie Ihr Projekt in **ETS5** oder **ETS6** (getestet mit ETS6)
2. Erstellen Sie einen Report von **"Gebäude"** mit aktivierten **"Objekten"**
3. Speichern Sie den Report als **CSV-Datei**

**Hilfe:** Bilder zur ETS-Export-Funktion finden Sie im Ordner `Readme/` der Release-Datei.

### Schritt 2: Excel-Datei vorbereiten

1. Öffnen Sie die CSV-Datei in **Microsoft Excel**
2. **Löschen Sie folgende Spalten:**(Selbst Prüfen falls bei euch die Aufteilung anders ist)
   - Spalte 1-3
   - Spalte 6
   - Spalte 7
   - Spalte 9-16
   - Spalte 19-20
3. Die Daten in Excel übernehmen und normal als **`.xlsx`** speichern

**Wichtig:** Die fertige Datei sollte ähnlich aussehen wie die "BeispielExcel".

### Schritt 3: Excel Konvertierung

1. Starten Sie `Excel Konvertierungstool.exe`
2. Wählen Sie die vorbereitete Excel-Datei aus
3. Wählen Sie den Speicherort für die konvertierte Datei
4. Klicken Sie auf "▶ Konvertieren"

**Ergebnis:** Es wird eine Datei erstellt (z.B. "BeispielExcelKonvertiert.xlsx")

### Schritt 4: Konvertierte Datei bearbeiten (optional)

Die konvertierte Datei kann nun nach Wunsch bearbeitet werden. Für das Beschriftungsprogramm sind alle Daten außer Spalte 6 "GA_Original" wichtig:

- **PhysAdr**: Physikalische Adressen (können hier angepasst werden)
- **Sensor**: Tastsensoren (automatisch erkannt, z.B. 3-fach)
- **Typ**: Automatisch erkannt (1fach, 2fach, 3fach, etc.)
- **Wippe**: Wippen-Nummer
- **Position**: Position der Wippe (oben, mitte, unten)
- **Beschriftung**: Die Beschriftung, die aus der GA exportiert wurde
  - Diese kann im Excel-Konvertierer eingestellt werden
  - Sollte etwas vergessen worden sein oder anders gewünscht, kann es hier nochmal verändert werden
- **GA_Original**: Nur für Vergleichszwecke da!

**Hinweis:** Das Tool ist derzeit auf **Wippen** begrenzt, nicht auf Einzeltasten. Falls Sie Einzeltasten benötigen, öffnen Sie bitte ein [Issue](https://github.com/DonatPlayZ/knx-taster-beschriftungstool/issues) - dann erweitere ich das Script, wenn Bedarf besteht und Zeit vorhanden ist.

### Schritt 5: Varianten und Icons konfigurieren

**Wichtig:** Wenn Sie eigene Texte/Beschriftungen haben/wollen, müssen diese zuvor in den Optionen eingegeben werden!

1. Starten Sie `Beschriftungstool.exe`
2. Gehen Sie zum Tab **"Varianten & Kategorien"**
3. Fügen Sie Ihre Varianten hinzu (z.B. "Licht", "Jalousie", etc.)
4. Gehen Sie zum Tab **"Icon-Zuordnung"**
5. Ordnen Sie den Varianten die entsprechenden SVG-Icons zu

**Wichtig:** Die Texte müssen mit den Texten aus der Spalte "Beschriftung" übereinstimmen! Das Tool prüft nach dem Namen, erkennt dann welche Kategorie es ist und fügt daraufhin das Icon ein.

#### Icons von Gira herunterladen

Offizielle Icons können von Gira heruntergeladen werden:
- **Download-Link:** [Gira Beschriftungssoftware Downloads](https://partner.gira.de/service/download/index.html?id=1040&lang=de)
- Die Icons sind im **WMF-Format** (Windows Metafile)
- **Konvertierung:** Diese müssen von `.wmf` in `.svg` konvertiert werden
  - Einfach online möglich (z.B. über Online-Konvertierungstools)
  - Die konvertierten SVG-Dateien dann in den `icons/` Ordner kopieren

**Alternativ:** Das Tool funktioniert auch **ohne Icons** - die PDFs werden dann nur mit Text erstellt.

### Schritt 6: PDFs erstellen

1. Wählen Sie die konvertierte Excel-Datei aus
2. Wählen Sie das Export-Verzeichnis
3. Klicken Sie auf "▶ PDFs erstellen"

Die PDFs werden automatisch erstellt und das Export-Verzeichnis öffnet sich.


## 📋 Wichtige Hinweise

### Tastsensor-Erkennung

Es wird nur nach Schaltern mit **'Tastsensor'** gesucht, unabhängig davon ob es sich um 1-fach, 2-fach, 3-fach, 4-fach oder mehr handelt.

### Icon-Ausrichtung

**Wichtig:** Das Tool wurde ursprünglich für ca. 600 Schalter in einem großen Industriegebäude erstellt. Hier ist es ziemlich oft gleich:
- Es handelt sich ausschließlich um **Wippen**
- Immer **Links EIN, Rechts AUS** oder **Links AUF, Rechts AB**

**Wenn bei Ihnen z.B. Rechts EIN und Links AUS ist**, können Sie einfach die Icons in den Einstellungen drehen (Icon-Zuordnung tauschen).

### Einschränkungen

- Derzeit nur **Wippen** unterstützt (keine Einzeltasten)
- Für Einzeltasten-Unterstützung bitte ein [Issue](https://github.com/DonatPlayZ/knx-taster-beschriftungstool/issues) öffnen

## ⚠️ Hinweis

Bei Problemen o.Ä. entschuldige ich mich erstmal, aber ich habe es vorerst nur mal veröffentlicht, um vielleicht dem ein oder anderen zu helfen! 

Wenn der Bedarf da ist, bin ich gerne bereit, das Programm zu erweitern.

## 📸 Hilfe

Bilder, die beim ETS-Excel-Teil helfen, finden Sie im Ordner `Readme/` der Release-Datei.

## 📄 Lizenz

Dieses Projekt ist unter einer Non-Commercial License lizenziert.
Siehe [LICENSE](LICENSE) für Details.

Copyright (c) 2026 Peindl IT

## 🔗 Links

- [Releases](https://github.com/DonatPlayZ/knx-taster-beschriftungstool/releases)
- [Issues](https://github.com/DonatPlayZ/knx-taster-beschriftungstool/issues) (für Fehlerberichte und Feature-Requests)
