# orange-nmr-addon

NMR-Preprocessing-Widgets für **Orange3** — für die Verarbeitung von 1D-NMR-
Spektren (z.B. ¹H) im Rahmen multivariater Analysen (Chemometrie).

## 🧩 Enthaltene Widgets

| Widget | Funktion |
|---|---|
| **NMR Binning** | Spektrale Auflösung reduzieren (avg/sum/max-Buckets) |
| **NMR Normalization** | Gesamtfläche / Maximum / L2 / Referenz-Region |
| **NMR Baseline Correction** | Polynom-Fit oder Asymmetric Least Squares (ALS) |
| **NMR Filter** | Savitzky-Golay: Glättung + Ableitungen |
| **NMR Region Exclusion** | Lösungsmittel-/Artefakt-ppm-Bereiche entfernen |
| **NMR Reference & Alignment** | Peak-basierte Verschiebung (Alignment) |

Die Spektraldaten folgen der Orange/Spectroscopy-Konvention: Die
**Attributnamen kodieren die x-Achse (ppm-Werte)**.

---

## 📋 Voraussetzungen

| Voraussetzung | Hinweis |
|---|---|
| Orange3 ≥ 3.40 installiert | Version unter Hilfe → Über prüfen |
| Internet-Zugriff auf GitHub | zum Herunterladen des Repos |

> ⚠️ **Wichtig:** Es muss immer **Oranges eigenes Python** verwendet werden,
> nicht `/usr/bin/python3`! Sonst wird das Add-on in der falschen Umgebung
> installiert und Orange findet es nicht.

---

## 🚀 Installation (Schritt für Schritt)

### macOS (Orange.app)

**Schritt 1 — Oranges eingebettetes Python prüfen:**

```bash
/Applications/Orange.app/Contents/Frameworks/Python.framework/Versions/Current/bin/python3 --version
```

Merke dir diesen Pfad (abgekürzt als `ORANGEPY`).

**Schritt 2 — Add-on von GitHub installieren:**

```bash
ORANGEPY=/Applications/Orange.app/Contents/Frameworks/Python.framework/Versions/Current/bin/python3
$ORANGEPY -m pip install git+https://github.com/philippweller/orange-nmr-addon.git
```

**Schritt 3 — Installation prüfen:**

```bash
$ORANGEPY -c "import oranjenmr; print('OK')"
```

Erscheint `OK`, ist das Paket korrekt installiert.

**Schritt 4 — In Orange öffnen:**

Orange starten. Die Widgets erscheinen unter der Kategorie **NMR Preprocessing**.
Du musst Orange nicht neu starten — das Canvas-Fenster erneut öffnen genügt.

---

### Windows (Orange Command Prompt)

**Schritt 1 — Orange Command Prompt öffnen:**

Startmenü → *Orange* → *Orange Command Prompt*.

**Schritt 2 — Installieren:**

```cmd
python -m pip install git+https://github.com/philippweller/orange-nmr-addon.git
```

**Schritt 3 — Prüfen:**

```cmd
python -c "import oranjenmr; print('OK')"
```

**Schritt 4 — Orange öffnen** und unter **NMR Preprocessing** nachschauen.

---

### Linux / Conda / Venv

**Schritt 1 — Umgebung aktivieren:**

```bash
conda activate orange    # oder: source .venv/bin/activate
```

**Schritt 2 — Installieren:**

```bash
pip install git+https://github.com/philippweller/orange-nmr-addon.git
```

**Schritt 3 — Prüfen:**

```bash
python -c "import oranjenmr; print('OK')"
```

**Schritt 4 — Orange starten** und das Widget suchen.

---

### Mit Spectroscopy-Integration (optional, empfohlen)

Falls die Software von `orangecontrib.spectroscopy` installiert ist, nutzt das
Add-on dessen `getx()`-Funktion für eine robustere ppm-Achsen-Erkennung:

```bash
# macOS
$ORANGEPY -m pip install ".[full]"
```
```bash
# Windows / Linux / Conda
python -m pip install ".[full]"
```

---

## 🔄 Updates einspielen

Auf **jedem** Rechner mit installiertem Add-on:

**Schritt 1 — aktuelle Version erneut installieren:**

```bash
# macOS
$ORANGEPY -m pip install --upgrade --force-reinstall git+https://github.com/philippweller/orange-nmr-addon.git
```
```bash
# Windows / Linux / Conda
python -m pip install --upgrade --force-reinstall git+https://github.com/philippweller/orange-nmr-addon.git
```

**Schritt 2 — Orange neu starten**, damit die neuen Widgets geladen werden.

> `--force-reinstall` wird empfohlen, weil Orange Widgets beim Canvas-Öffnen
> zwischenspeichert.

---

## 🗑️ Deinstallation

```bash
# macOS
$ORANGEPY -m pip uninstall oranjenmr -y
```
```bash
# Windows / Linux / Conda
python -m pip uninstall oranjenmr -y
```

Danach Orange neu starten.

---

## 🛠️ Fehlerbehebung

| Problem | Lösung |
|---|---|
| `import oranjenmr` schlägt fehl | Du hast das falsche Python benutzt (siehe Schritt 1). |
| Widget erscheint nicht in Orange | `pip show oranjenmr` prüfen; Orange vollständig neu starten. |
| `Host key verification failed` | Nur beim SSH-Workflow relevant — nutze die `git+https://`-URL. |
| alte Version bleibt | `pip install --force-reinstall` verwenden (siehe Updates). |

---

## 📦 Entwicklung / Repo lokal ausprobieren

```bash
git clone git@github.com:philippweller/orange-nmr-addon.git
cd orange-nmr-addon
# Editable-Install:
$ORANGEPY -m pip install -e .
```

---

## 📄 Lizenz

MIT © Philipp Weller