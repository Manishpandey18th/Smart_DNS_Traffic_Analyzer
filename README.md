# Smart DNS Traffic Analyzer

A real-time DNS traffic monitoring tool that detects spoofing, suspicious, and normal traffic using both **CLI** and **GUI (Tkinter)** modes.

## Features
- Real-time DNS packet capture & analysis
- Threat detection: DNS spoofing, tunneling, suspicious patterns
- Dual interface: Command-Line (CLI) + Graphical (Tkinter)
- Color-coded threat visualization in GUI
- Date-based filtering & report generation
- Customizable detection thresholds

## Installation

1. Clone the repository
```bash
git clone https://github.com/your-username/smart-dns-analyzer.git
cd smart-dns-analyzer

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
→ Captures live DNS traffic (UDP port 53) using Scapy
→ <b>Extracts features</b>: Entropy, Length, Subdomains, TTL, Frequency
→ Classifies traffic as Normal, Suspicious or Spoofing
→ Displays real-time results (GUI) or terminal output (CLI)
→ Logs flagged queries & generates exportable reports

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

## Future Enhancements (Planned)

→ Threat intelligence integration (VirusTotal, etc.)
→ Fast-Flux & DNS Amplification detection
→ Web dashboard (Streamlit/Flask)
→ SIEM export (ELK, Splunk)
