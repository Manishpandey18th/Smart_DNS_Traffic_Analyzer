# Smart DNS Traffic Analyzer

**Real-time DNS traffic monitoring tool that detects spoofing, tunneling, and suspicious patterns — with both CLI and beautiful Tkinter GUI.**

[<image-card alt="Python" src="https://img.shields.io/badge/python-3.9%2B-blue" ></image-card>](https://www.python.org/)
[<image-card alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" ></image-card>](https://opensource.org/licenses/MIT)
[<image-card alt="GitHub stars" src="https://img.shields.io/github/stars/your-username/smart-dns-analyzer?style=social" ></image-card>](https://github.com/your-username/smart-dns-analyzer)

<p align="center">
  <img src="https://via.placeholder.com/800x400.png?text=GUI+Screenshot+Here" alt="GUI Screenshot" width="800"/>
  <!-- Replace with real screenshot when you have one -->
</p>

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Customization](#customization)
- [Technologies Used](#technologies-used)
- [Screenshots](#screenshots) *(optional but recommended)*
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## Features

- ⚡ Real-time DNS packet capture and analysis (UDP port 53)
- 🛡️ Threat detection: DNS spoofing, tunneling, suspicious patterns
- Dual mode: **CLI** (terminal) + **GUI** (Tkinter with color-coded alerts)
- 📊 Color-coded threat visualization in GUI (green = normal, yellow = suspicious, red = spoofing)
- 📅 Date-based filtering & CSV/JSON report generation
- ⚙️ Customizable detection thresholds

## Installation

1. Clone the repository
```bash
git clone https://github.com/your-username/smart-dns-analyzer.git
cd smart-dns-analyzer ```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. requirements.txt content:
```bash
scapy==2.5.0
scikit-learn==1.4.1.post1
pandas==2.2.1
numpy==1.26.4
beepy==1.0.7
```

4. Windows users only: Install Npcap
→ Download: https://npcap.com
→ Important: Select WinPcap API-compatible mode during installation

5. Usage
→ Run CLI version
```bash python smart_dns_analyzer.py ```
Run GUI version (Tkinter)
```bash python tkinter_gui.py ```

6. How It Works
→ How It Works

1. Captures live DNS traffic using Scapy
2. Extracts key features from each query:
→ Entropy of domain name
→ Query length
→ Number of subdomains
→ TTL values
→ Query frequency / time-based patterns

3. Classifies traffic using Random Forest model + rule-based heuristics:
→ Normal
→ Suspicious
→ Spoofing / Malicious

4. Displays real-time results (GUI) or terminal output (CLI)
5. Logs flagged queries and generates exportable reports

## Customization
→ Edit detection thresholds in the scripts:
```bash PythonTHRESHOLD_ENTROPY = 3.8
THRESHOLD_LENGTH  = 35
THRESHOLD_TTL     = 10
THRESHOLD_FREQ    = 5 ```

## Technologies Used
→ Python
→ Scapy (packet sniffing)
→ Tkinter (GUI)
→ Pandas & NumPy (data processing)
→ scikit-learn (Random Forest anomaly detection)
→ Npcap (Windows packet capture driver)

## Screenshots


 <img src="screenshots/gui-example.png" alt="GUI Example" width="600">
  
              Real-time GUI with color-coded alerts

## Future Enhancements (Planned)
→ Threat intelligence integration (VirusTotal, etc.)
→ Fast-Flux & DNS Amplification detection
→ Web dashboard (Streamlit/Flask)
→ SIEM export (ELK, Splunk)
