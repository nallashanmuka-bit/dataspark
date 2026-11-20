# DataSpark v2.0.0 — Production Release Build
*Dictionary Lookup Tool & Smart Analytics Engine | Hackathon Project #114*

---

## 🌟 Overview
**DataSpark** is a production-ready Python application engineered to streamline vocabulary data management, query word meanings via live dictionary APIs with defensive offline fallback, execute input sanitization, and generate comprehensive executive analytics and visual trend reports.

---

## 🚀 Key Features

### 1. Core API Engine & Defensive Fallback
- Connects directly to the **Free Dictionary API** for real-time word lookup.
- If offline, rate-limited, or encountering network timeouts, seamlessly degrades to an embedded **Offline Mock Cache** or generates structured fallback records without interrupting user workflow.

### 2. Defensive Input Validation
- Centralized sanitization module utilizing regular expressions to filter out numerical values, injection payloads, empty prompts, and boundary violations (> 50 chars).

### 3. Local File Storage & Auto-Recovery
- Automatic serialization and deserialization of application state in **JSON** and **CSV** formats.
- **File Corruption Recovery**: Automatically detects missing or malformed JSON files, creates timestamped backup files (`.bak`), and re-initializes clean database templates.

### 4. Executive Analytics & Visual Plotting
- Calculates system-wide KPIs: Total vocabulary words, total query operations, average queries per word, and top-searched keywords.
- Incorporates **Matplotlib** to generate dual-dashboard visual charts (`dataspark_chart.png`) plotting record categories and lookup distribution.

### 5. Multi-Format Audit Briefs & Bulk CSV Import
- Exports Markdown reports (`dataspark_report.md`) containing summary tables and **Threshold Warning Indicators** for flagged or high-frequency queries.
- Ingests bulk external CSV files with row-by-row validation logging.

### 6. Flexible Interfaces (CLI + Tkinter GUI + TUI)
- Interactive menu-driven console with ANSI color branding.
- Desktop graphical UI powered by **Tkinter** for visual navigation.

---

## 🛠️ Quickstart Guide

### Running the Terminal Interface (Default)
```bash
python3 main.py
```

### Launching Desktop Graphical Interface (GUI)
```bash
python3 main.py --gui
```

### Running Automated Test Suite
```bash
python3 -m unittest discover tests
```

---

## 📁 Package Architecture
```text
dataspark_package_v2/
├── dataspark/
│   ├── __init__.py
│   ├── models.py          # Dataclasses & schema definitions
│   ├── validator.py       # Defensive regex validation wrapper
│   ├── api_client.py      # Live API & offline fallback engine
│   ├── storage.py         # Persistence manager & corruption recovery
│   ├── analytics.py       # KPI aggregator & Matplotlib plot generator
│   ├── reporter.py        # Markdown audit briefs & CSV bulk importer
│   ├── cli.py             # Interactive menu console
│   ├── gui.py             # Tkinter visual desktop GUI
│   └── tui.py             # Terminal user interface wrapper
├── data/                  # Pre-populated seed database (JSON/CSV)
├── tests/                 # Automated unit tests
├── main.py                # Main executable entry point
├── README.md              # Documentation
└── setup.py               # Installation script
```

---
*DataSpark v2.0.0 — Engineered for Reliability, Fault Tolerance, and Data Clarity.*
