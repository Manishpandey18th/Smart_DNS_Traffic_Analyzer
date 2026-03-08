# Smart DNS Traffic Analyzer

**Real-time DNS traffic monitoring tool that detects spoofing, tunneling, and suspicious patterns — with both CLI and beautiful Tkinter GUI.**

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Customization](#customization)
- [Technologies Used](#technologies-used)
- [Future Enhancements](#future-enhancements)

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
cd smart-dns-analyzer
```

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

## Usage
→ Run CLI version
```bash
python smart_dns_analyzer.py 
```
Run GUI version (Tkinter)
```bash
python tkinter_gui.py 
```

## How It Works
1. Captures live DNS traffic using Scapy
2. Extracts key features from each query:
- Entropy of domain name
- Query length
- Number of subdomains
- TTL values
- Query frequency / time-based patterns

3. Classifies traffic using Random Forest model + rule-based heuristics:
- Normal
- Suspicious
- Spoofing / Malicious

4. Displays real-time results (GUI) or terminal output (CLI)
5. Logs flagged queries and generates exportable reports

## Customization
→ Edit detection thresholds in the scripts:
```bash Python
THRESHOLD_ENTROPY = 3.8
THRESHOLD_LENGTH  = 35
THRESHOLD_TTL     = 10
THRESHOLD_FREQ    = 5
```

## Technologies Used
- Python
- Scapy (packet sniffing)
- Tkinter (GUI)
- Pandas & NumPy (data processing)
- scikit-learn (Random Forest anomaly detection)
- Npcap (Windows packet capture driver)



## Future Enhancements (Planned)
→ Threat intelligence integration (VirusTotal, etc.)
→ Fast-Flux & DNS Amplification detection
→ Web dashboard (Streamlit/Flask)
→ SIEM export (ELK, Splunk)
