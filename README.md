
# AnalyzPC

A single‑exe Windows tool that scans your full PC hardware and exposes whether your ISP is giving you the speed you pay for.  
Built with no WiFi — only expensive daily mobile data packs in Afghanistan.

## Features (all options)
- 🔍 **System Info**: OS version, CPU model & cores, total/free RAM, disk partitions, network adapters – instant scan.
- ⚡ **Speed Test with Truth Check**: 
  - Measures real download, upload, and ping.
  - Enter your ISP's promised speed (e.g., “2 Mbps”).
  - Displays **Advertised vs Actual** side by side – the numbers don't lie.
- 📋 **Clean Console Report**: copy‑friendly output, no GUI overhead.
- 📦 **Portable EXE**: single file, no installation, fully obfuscated with PyArmor and packed with PyInstaller – tamper‑proof.

## Why This Tool Exists
I live in Afghanistan. I don't have WiFi. I code using a mobile phone hotspot, buying daily packages that claim “2 Mbps” but rarely deliver even half. Every download costs money, and the connection cuts out constantly. I built AnalyzPC to prove this lie — and to give anyone a fast, portable system profiler that works offline (except the speed test, obviously).

## How to Use
1. Download `AnalyzPC.exe` from the [Releases page](https://github.com/yourusername/AnalyzPC/releases).
2. Double‑click to run.
3. Select an option:
   - `1` → View full system information.
   - `2` → Run speed test (enter your ISP's promised speed when asked).
4. Read the report or copy it anywhere.

## Build from Source
If you want to modify or rebuild:
```bash
git clone https://github.com/yourusername/AnalyzPC.git
cd AnalyzPC
pip install pyarmor pyinstaller
# Obfuscate
pyarmor gen --restrict -O obf_dist AnalyzPC.py
# Package to single EXE
pyinstaller --onefile --add-data "obf_dist/pyarmor_runtime_000000;pyarmor_runtime_000000" obf_dist/AnalyzPC.py
```

The final exe will be inside the dist folder.

Tech Stack

· Python 3.x
· PyArmor (code obfuscation, --restrict mode)
· PyInstaller (bundling)
· Speed test powered by speedtest-cli (or custom socket method)

License

MIT – use it, learn from it, share it.

Support & Story

If this tool helped you, a ⭐ on the repo means the world. It was built one megabyte at a time, with a connection that never truly gave 2 Mbps. Let's make internet honesty visible.

```
