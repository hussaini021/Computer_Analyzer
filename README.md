# 🔧 MH System Toolbox v2.0 Pro

> **A comprehensive Windows system management and security suite** built with Python. Professional-grade performance monitoring, advanced security scanning, and intelligent cleanup—all in one lightweight, transparent application.

[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/hussaini021/MH-System-Toolbox?style=social)](https://github.com/hussaini021)
[![Platform: Windows](https://img.shields.io/badge/Platform-Windows%207%2B-0078d4)](https://www.microsoft.com/en-us/windows)

---

## 📋 Table of Contents

- [Features](#-features)
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [Usage Guide](#-usage-guide)
- [Architecture](#-architecture)
- [Requirements](#-requirements)
- [Troubleshooting](#-troubleshooting)
- [Development Story](#-development-story)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## ✨ Features

### 📊 **Real-time Dashboard**
- **Live System Metrics**: CPU, RAM, Disk, and Network usage monitored in real-time
- **Visual Analytics**: Interactive matplotlib charts with 60-second history tracking
- **System Health**: Quick snapshot of overall system status with color-coded indicators
- **Network Monitor**: Download/Upload speed with live bandwidth visualization

### 🛡️ **Advanced Security Suite**
- **Threat Scanner**: Scans directories for malware and suspicious files
- **Windows Defender Integration**: Automated full/quick system scans
- **Quarantine System**: Isolate detected threats safely
- **Malware Detection**: Pattern-based and heuristic scanning capabilities
- **Real-time Logging**: Detailed threat analysis and removal logs

### 🧹 **Intelligent Cleanup Tools**
- **Temp File Removal**: Clears Windows temp folders, cache, and temporary data
- **Browser Cleanup**: Remove browsing history, cookies, and cache from major browsers
  - Chrome, Firefox, Edge, Opera support
- **Recycle Bin Management**: Empty or selective recovery from Recycle Bin
- **Smart File Detection**: Auto-identify and remove files older than configurable threshold (default: 7 days)
- **Safe Deletion**: Uses send2trash for safe, recoverable file removal

### 🚀 **Performance Optimization**
- **Process Manager**: View and manage running processes with detailed I/O statistics
- **Startup Controller**: Enable/disable startup programs to improve boot time
- **Disk Usage Analyzer**: Visual breakdown of disk space usage by drive/folder
- **Memory Optimizer**: Clear cached data and optimize memory usage
- **Performance Report**: Export detailed system statistics to CSV

### 🎨 **Professional UI/UX**
- **Dark Mode Design**: GitHub-inspired dark theme with cyber-teal accents
- **Responsive Layout**: Multi-tab interface for organized functionality
- **Real-time Updates**: Non-blocking UI with threaded operations
- **Status Indicators**: Visual feedback for all operations
- **Export Capabilities**: Save logs and reports in CSV/JSON formats

---

## 📦 Installation

### Prerequisites
- **Python 3.8** or higher
- **Windows 7** or later (Windows 10/11 recommended)
- **Administrator privileges** (for some features)

### Step 1: Clone the Repository
```bash
git clone https://github.com/hussaini021/Computer_Analyzer.git
cd Computer_Analyzer
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install psutil send2trash pywin32 winshell speedtest-cli matplotlib pillow
```

### Step 3: Run the Application
```bash
python AnalyizPC.py
```

**Important**: Run as Administrator for full functionality (defragmentation, firewall, event logs)

## How to Use
1. Download `AnalyzPC.exe` from the [Releases page](https://github.com/hussaini021/Computer_Analyzer/releases).
2. Double‑click to run.
3. Select an option:
   - `1` → View full system information.
   - `2` → Run speed test (enter your ISP's promised speed when asked).
4. Read the report or copy it anywhere.

---

## 🚀 Quick Start

### For First-Time Users

1. **Launch the application** with administrator privileges
   ```bash
   python AnalyizPC.py
   ```

2. **Dashboard Tab**: Check your system status at a glance
   - Monitor CPU, RAM, Disk usage in real-time
   - View network activity and speed

3. **Cleaner Tab**: Safely remove unnecessary files
   - Start with "Clean Temp Files" for quick cleanup
   - Use "Full Cleanup" for comprehensive system cleaning
   - Monitor progress in the log window

4. **Antivirus Tab**: Scan for threats
   - Quick Scan: Scans critical system folders
   - Custom Scan: Choose specific directories
   - Windows Defender: Leverage Windows' built-in protection

5. **Network & Tools**: Additional utilities
   - Test internet speed
   - Analyze disk usage
   - Manage processes and startup programs

---

## 📖 Usage Guide

### Dashboard Tab
```
✓ Real-time CPU, RAM, Disk, Network monitoring
✓ Visual charts updating every second
✓ Color-coded health status (Green=Healthy, Red=Critical)
✓ Export system data to CSV
```

### Cleaner Tab
```
✓ Clean Temp Files: Removes %TEMP% and cache directories
✓ Clean Browser Data: Clears history, cookies, cache from all browsers
✓ Empty Recycle Bin: Permanently delete files in Recycle Bin
✓ Full Cleanup: Execute all cleanup operations sequentially

⚠️ Tip: Backup important data before full cleanup
```

### Antivirus Tab
```
✓ Quick Scan: ~30 seconds (system folders)
✓ Custom Scan: Select any directory for scanning
✓ Threat Quarantine: Automatically isolate detected threats
✓ Windows Defender: Full system scan with Microsoft's engine
✓ Real-time Threat Log: Detailed analysis of all detections
```

### Network & Tools Tab
```
✓ Speed Test: Check your internet speed (requires speedtest-cli)
✓ Disk Analyzer: Visual breakdown of disk usage
✓ Process Manager: View and manage running processes
✓ Startup Programs: Control what launches on boot
```

---

## 🏗️ Architecture

### Project Structure
```
MH-System-Toolbox/
├── AnalyizPC.py          # Main application file (1,900+ lines)
├── requirements.txt      # Python dependencies
├── README.md            # This file
└── LICENSE              # MIT License

Features by Module:
├── Core Utilities
│   ├── bytes2human()    - Unit conversion
│   ├── is_admin()       - Admin check
│   └── safe_delete()    - Safe file removal
│
├── System Monitoring
│   ├── LiveData class   - Real-time data collection
│   ├── DashboardPage    - UI for system metrics
│   └── Matplotlib integration - Real-time charts
│
├── Security
│   ├── scan_directory_for_threats()  - File scanning
│   ├── run_windows_defender()        - Defender integration
│   └── AntivirusPage                 - Threat management UI
│
├── Cleanup Operations
│   ├── remove_old_files()   - Smart file removal
│   ├── CleanerPage          - Cleanup UI
│   └── Browser cache handler - Multi-browser support
│
└── UI Framework
    ├── Tkinter-based GUI
    ├── Dark theme with custom styling
    └── Multi-threaded operations
```

### Key Design Patterns
- **Object-Oriented Programming**: Modular, maintainable code structure
- **Threading**: Prevents UI freezing during long operations
- **Event-Driven Architecture**: Real-time updates without polling
- **Error Handling**: Comprehensive try-catch blocks throughout
- **Logging System**: Detailed operation logs for debugging

### Performance Considerations
- **Minimal Memory Footprint**: ~50-100 MB at runtime
- **Non-Blocking UI**: All heavy operations run on separate threads
- **Efficient Data Structures**: Deques for circular buffers in real-time data
- **Lazy Loading**: Features load only when accessed

---

## 📋 Requirements

### System Requirements
| Component | Minimum | Recommended |
|-----------|---------|-------------|
| OS | Windows 7 | Windows 10/11 |
| RAM | 2 GB | 4+ GB |
| Python | 3.8 | 3.9+ |
| Disk Space | 100 MB | 500 MB |

### Python Dependencies
```
psutil>=5.9.0           # System monitoring
tkinter                 # GUI framework (included with Python)
matplotlib>=3.5.0       # Data visualization
pillow>=9.0.0          # Image processing
send2trash>=1.8.0      # Safe file deletion
pywin32>=300           # Windows API access
winshell>=0.6          # Windows shell utilities
speedtest-cli>=2.1.3   # Internet speed testing
```

---

## 🔧 Troubleshooting

### Issue: "No module named 'X'"
**Solution**: Install missing dependency
```bash
pip install [module-name]
```

### Issue: "Permission Denied" errors
**Solution**: Run as Administrator
```bash
Right-click → Run as Administrator
```

### Issue: Antivirus features not working
**Solution**: 
1. Ensure Windows Defender is installed
2. Run with admin privileges
3. Check if Windows Defender service is running

### Issue: UI freezes during operation
**Solution**: This shouldn't happen (threading prevents it)
- If it does, restart the application
- Report the issue on GitHub

### Issue: Matplotlib charts not displaying
**Solution**:
```bash
pip install --upgrade matplotlib
# Ensure TkAgg backend is available
```

### Issue: Performance slow on large directories
**Solution**:
- Use "Quick Scan" instead of "Custom Scan" for system folders
- Scan directories with fewer files first
- Close other applications to free up system resources

---

## 💻 Development Story

This project represents **months of dedicated development**, with countless hours of:

- **Research**: Deep diving into Windows APIs, system monitoring techniques, and security protocols
- **Coding**: Building 1,900+ lines of production-grade Python code
- **Testing**: Testing across multiple Windows versions and system configurations
- **Optimization**: Profiling and optimizing for performance and usability
- **Documentation**: Creating comprehensive guides and code comments

**The Commitment**:
This wasn't built as a side project or quick prototype. Every morning, the internet was turned on specifically to continue this work. The dedication shows in:
- Clean, maintainable code architecture
- Thoughtful UI/UX design
- Comprehensive error handling
- Real-world feature prioritization
- Performance optimization at every level

---

## 🤝 Contributing

Contributions are welcome and encouraged! Whether it's bug reports, feature requests, or code improvements, your input helps make this project better.

### How to Contribute

1. **Fork the repository**
   ```bash
   git clone https://github.com/hussaini021/Computer_Analyzer.git
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes** and test thoroughly
   ```bash
   python AnalyizPC.py
   ```

4. **Commit your changes**
   ```bash
   git commit -m "Add feature: description of your changes"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create a Pull Request** with a detailed description

### Code Style Guidelines
- Follow PEP 8 conventions
- Add comments for complex logic
- Test on Windows 7+ before submitting
- Update documentation as needed

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### You are free to:
- ✅ Use commercially and privately
- ✅ Modify the source code
- ✅ Distribute the software
- ✅ Sublicense the software

### Under the condition:
- ⚠️ Include a copy of the original license and copyright notice

---

## 📧 Contact & Support

### Author
**Murtaza Hussaini**
- 🎓 Kabul University · ISE Department · Year 3
- 🔗 GitHub: [@hussaini021](https://github.com/hussaini021)
- 📧 Email: [murtazaom.167@gmail.com]

### Support
- **Report Issues**: [GitHub Issues](https://github.com/hussaini021/Computer_Analyzer/issues)
- **Feature Requests**: [GitHub Discussions](https://github.com/hussaini021/Computer_Analyzer/discussions)
- **Security Issues**: Please email directly (responsible disclosure)

---

## 🌟 Acknowledgments

Special thanks to:
- The Python community for excellent libraries
- Windows API documentation and community forums
- Everyone who has tested and provided feedback
- The open-source movement for inspiration and tools

---

## 📊 Project Stats

| Metric | Value |
|--------|-------|
| Lines of Code | 1,900+ |
| Python Version | 3.8+ |
| Development Time | Months of daily work |
| Number of Features | 15+ |
| Supported Windows Versions | 7 to 11+ |
| Code Quality | Production-grade |

---

## 🚀 Roadmap

### Planned Features (v2.1)
- [ ] Network packet analyzer
- [ ] GPU monitoring (for gaming PCs)
- [ ] Advanced firewall manager
- [ ] Custom alert system
- [ ] Scheduled cleanup automation

### Under Consideration
- Multi-language support
- Mobile app integration
- Cloud sync capabilities
- Advanced reporting dashboard

---

## ⚡ Getting Help

1. **Check existing issues** - Your question might already be answered
2. **Read the troubleshooting section** - Common problems and solutions
3. **Create a detailed issue** - Include Windows version, Python version, and error message
4. **Search documentation** - Full guides are available

---

## 📸 Screenshots

*Coming soon* - Visual tour of the application interface

---

## 💡 Pro Tips

- **Run as Administrator** for full feature access
- **Regular backups** before major cleanup operations
- **Export reports** regularly for system monitoring trends
- **Update Python** to latest stable version for best performance
- **Check documentation** before reporting issues

---

## 📚 Additional Resources

- [Python Official Documentation](https://docs.python.org/3/)
- [Windows API Documentation](https://docs.microsoft.com/en-us/windows/win32/api/)
- [Tkinter GUI Documentation](https://docs.python.org/3/library/tkinter.html)
- [psutil Documentation](https://psutil.readthedocs.io/)

---

<div align="center">

**Made with ❤️ by Murtaza Hussaini**

[![Star if helpful](https://img.shields.io/badge/⭐%20If%20helpful%20-please%20star-yellow.svg)](https://github.com/hussaini021/Computer_Analyzer)

*Last updated: 2025*

</div>

lyzPC to prove this lie — and to give anyone a fast, portable system profiler that works offline (except the speed test, obviously).

