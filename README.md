# PC Optimizer for R6

**Ultimative Windows-Optimierung für Rainbow Six Siege** – Maximale FPS, minimale Latenz, null Bloatware.

Löscht Hintergrunddienste, deaktiviert Telemetrie & Datenfresser, optimiert CPU/GPU/Netzwerk für pure R6-Leistung. Automatische Hardware-Erkennung mit 5 PC-Tiers – von der Ultra-Low-Kiste bis zum High-End-Rig.

## Features

- **5 PC-Tiers** – Ultra-Low, Low-End, Mid, High, High-End – mit automatischer Profilempfehlung via Hardware-Scan
- **Auto-Detect** – erkennt CPU/GPU/RAM/SSD und schlägt den optimalen Tier vor
- **22+ Optimierungen** – Game Mode, HPET, Core Parking, Memory Compression, Timer Resolution, C-States, Spectre/Meltdown, Netzwerk-Tweaks, R6 GameSettings.ini uvm.
- **Win 10 & Win 11 Support** – versionsspezifische Tweaks (VBS, Widgets, Animationen deaktivieren)
- **Sicherung & Wiederherstellung** – vollständiges System-Snapshot vor jeder Optimierung, 1-Klick-Restore (Snapshot bleibt dauerhaft erhalten)
- **Per-Action Undo** – einzelne Optimierungen können direkt rückgängig gemacht werden (z. B. CPU 100%-Taktung)
- **Animated UI** – dunkles GitHub-Design mit Rocket-Startanimation, Hover-Effekten, Live-Log

## PC Tiers

| Tier | Ziel | Beschreibung |
|------|------|-------------|
| **Ultra-Low** | Extrem | Minimale Latenz um jeden Preis – aktiviert alle Ultra-Low-Tweaks |
| **Low-End** | Max FPS | Maximale Bildrate auf schwacher Hardware |
| **Mid** | Balanced | Gute Performance bei stabilen 144+ FPS |
| **High** | Performance | Optimiert für hohe FPS, schont Systemstabilität |
| **High-End** | Latency | Minimiert Input-Lag auf leistungsstarken Systemen |

## Download

| Variante | Größe | Beschreibung |
|----------|-------|-------------|
| **PC_Optimizer_R6_Setup.exe** | ~9 MB | Inno Setup-Installer – installiert mit Admin-Rechten, Startmenü-Verknüpfung, Systemsteuerung-Deinstallation |
| **PC_Optimizer_R6.exe** | ~28 MB | Portable Einzeldatei (Nuitka Onefile), kein Setup nötig |

> **Hinweis zur portablen EXE**: Manche Antiviren-Programme melden False Positives. Die EXE wird mit Nuitka nativ kompiliert (C-Kompilierung, kein gepacktes Python). Bei Bedarf unter Windows Defender auf "Trotzdem ausführen" klicken.

### Installer (empfohlen)

Der Inno Setup-Installer:
- Installiert nach `%ProgramFiles%\PC Optimizer for R6`
- Erzwingt **Admin-Ausführung** via AppCompatFlags
- Erstellt Startmenü-Eintrag + optional Desktop-Verknüpfung
- Deinstallierbar über Systemsteuerung

## Anforderungen

- Windows 10 oder Windows 11 (64-Bit)
- Rainbow Six Siege installiert (für GameSettings.ini-Optimierung)
- **Administrator-Rechte zwingend erforderlich** (für Registry, Dienste, BCD, powercfg)

## Nutzung

1. `PC_Optimizer_R6_Setup.exe` ausführen und installieren (oder portable EXE direkt starten)
2. **Disclaimer** bestätigen (nach 3s)
3. Win 10 / Win 11 auswählen
4. **Hardware-Scan** durchführen lassen oder Tier manuell wählen
5. Optimierungen auswählen (Profilvorschlag je nach Tier)
6. "OPTIMIERUNG STARTEN" klicken – Snapshot wird automatisch erstellt
7. **Rückgängig**: "ALLE ÄNDERUNGEN RÜCKGÄNGIG" (Snapshot-Restore) oder "↺" neben CPU-Option (schnelles Undo)

## Selber bauen

### Portable EXE (Nuitka)

```bash
pip install nuitka

python -m nuitka --onefile --windows-console-mode=disable ^
  --enable-plugin=tk-inter --windows-icon-from-ico=icon.ico ^
  --windows-company-name=BosuFPS --windows-product-name="PC Optimizer for R6" ^
  --file-version=2.0.0 ^
  --file-description="PC Optimizer for Rainbow Six Siege - Leistungsoptimierung" ^
  --product-version=2.0.0 ^
  --output-dir=dist_nuitka ^
  optimizer/main.py
```

### Installer (Inno Setup)

```bash
# Inno Setup 6 installieren (winget)
winget install "Inno Setup"

# Kompilieren
& "C:\Program Files (x86)\Inno Setup 6\ISCC.exe" installer.iss
```

## Lizenz

© 2025 BosuFPS. Alle Rechte vorbehalten.
