# PC Optimizer for R6

**Ultimative Windows-Optimierung für Rainbow Six Siege** – Maximale FPS, minimale Latenz, null Bloatware.

Löscht Hintergrunddienste, deaktiviert Telemetrie & Datenfresser, optimiert CPU/GPU/Netzwerk für pure R6-Leistung. Automatische Hardware-Erkennung mit 5 PC-Tiers – von der Ultra-Low-Kiste bis zum High-End-Rig.

## Features

- **5 PC-Tiers** – Ultra-Low, Low-End, Mid, High, High-End – mit automatischer Profilempfehlung via Hardware-Scan
- **Auto-Detect** – erkennt CPU/GPU/RAM/SSD und schlägt den optimalen Tier vor
- **22+ Optimierungen** – Game Mode, HPET, Core Parking, Memory Compression, Timer Resolution, C-States, Spectre/Meltdown, Netzwerk-Tweaks, R6 GameSettings.ini uvm.
- **Win 10 & Win 11 Support** – versionsspezifische Tweaks (VBS, Widgets, Animationen deaktivieren)
- **Sicherung & Wiederherstellung** – vollständiges System-Snapshot vor jeder Optimierung, 1-Klick-Restore
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

**[PC_Optimizer_R6.exe](dist_nuitka/PC_Optimizer_R6.exe)** – ~28 MB, portable Einzeldatei, keine Installation nötig.

> **Hinweis**: Manche Antiviren-Programme melden False Positives. Die EXE wird mit Nuitka nativ kompiliert (C-Kompilierung, kein gepacktes Python). Bei Bedarf unter Windows Defender auf "Trotzdem ausführen" klicken.

## Anforderungen

- Windows 10 oder Windows 11 (64-Bit)
- Rainbow Six Siege installiert (für GameSettings.ini-Optimierung)
- **Administrator-Rechte empfohlen** (für Registry, Dienste, BCD, powercfg)

## Nutzung

1. `PC_Optimizer_R6.exe` ausführen
2. **Disclaimer** bestätigen (nach 3s)
3. Win 10 / Win 11 auswählen
4. **Hardware-Scan** durchführen lassen oder Tier manuell wählen
5. Optimierungen auswählen (Profilvorschlag je nach Tier)
6. "OPTIMIERUNG STARTEN" klicken – Snapshot wird automatisch erstellt
7. **Rückgängig**: "ALLE ÄNDERUNGEN RÜCKGÄNGIG" (Snapshot-Restore) oder "↺" neben CPU-Option (schnelles Undo)

## Selber bauen

```bash
# Nuitka installieren
pip install nuitka

# Build
python -m nuitka --onefile --windows-disable-console ^
  --enable-plugin=tk-inter --windows-icon-from-ico=icon.ico ^
  --windows-company-name=BosuFPS --windows-product-name="PC Optimizer for R6" ^
  --windows-file-version=1.1.0.0 ^
  --windows-file-description="PC Optimizer for Rainbow Six Siege - Leistungsoptimierung" ^
  --windows-product-version=1.1.0.0 ^
  --output-dir=dist_nuitka --output-filename=PC_Optimizer_R6.exe ^
  optimizer/main.py
```

## Lizenz

© 2025 BosuFPS. Alle Rechte vorbehalten.
