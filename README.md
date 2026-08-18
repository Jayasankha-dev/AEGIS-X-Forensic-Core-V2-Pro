<img width="1472" height="913" alt="Capture" src="https://github.com/user-attachments/assets/bdc629e4-29b6-4d9b-8f40-c4776f6a20a3" />




# AEGIS-X Pro
<img width="256" height="256" alt="logo" src="https://github.com/user-attachments/assets/c0221a6a-6329-4ec1-959c-6561d62964bd" />

### Defensive Cybersecurity & Digital Forensics Toolkit for Windows

AEGIS-X Pro is a Windows-focused defensive cybersecurity and digital forensics toolkit designed for security analysis, incident triage, system inspection, persistence discovery, network intelligence, evidence collection, and forensic investigation.

The project started as a terminal-based forensic utility and has been expanded into a more structured security analysis platform while preserving its original forensic capabilities.

---

## ⚠️ Disclaimer

AEGIS-X Pro is designed for **defensive security, authorized investigations, digital forensics, incident response, and system administration**.

Only use this software on systems you own or have explicit permission to investigate.

The author is not responsible for damage, data loss, unauthorized access, or misuse of this software.

---

## ✨ Features

### 🔍 Core Forensics

- Quick system triage
- Running process analysis
- Process relationship analysis
- Process executable path inspection
- File-system forensic analysis
- Recently modified file analysis
- Prefetch inspection
- Alternate Data Stream detection
- USB device history
- Windows event log analysis
- PowerShell event analysis
- System error analysis

### 🌐 Network Intelligence

- Established network connection analysis
- Listening port discovery
- Process-to-network relationship analysis
- DNS resolver cache inspection
- ARP neighbor table collection
- IPv4 routing table analysis
- Remote IP classification
- Private/public IP detection
- GeoIP country and city enrichment
- ASN / organization lookup
- Network evidence collection

### 🛡️ Persistence Analysis

AEGIS-X Pro can inspect common Windows persistence locations, including:

- Registry Run keys
- Startup folders
- WMI event subscriptions
- Services
- Scheduled tasks
- Drivers
- Browser extensions
- Other forensic persistence artifacts

The goal is to identify unusual or unexpected persistence mechanisms that may require further investigation.

---

## 🧪 Security Analysis

AEGIS-X Pro provides defensive analysis capabilities for identifying suspicious indicators such as:

- Unknown executables
- Unexpected startup entries
- Suspicious process paths
- Unusual network connections
- Unexpected listening services
- Suspicious PowerShell activity
- Encoded or unusual command-line activity
- Unexpected browser extensions
- Unusual persistence entries
- Files requiring hash verification

### Important

A suspicious indicator does **not automatically mean malware**.

AEGIS-X Pro is intended to help an analyst collect and correlate evidence before making a final determination.

---

## 🧠 Forensic Analysis Workflow

AEGIS-X Pro follows an evidence-first approach:

```text
                 ┌──────────────────────┐
                 │   System Collection  │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │  Evidence Normalize  │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │  Indicator Analysis  │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │    Risk Assessment   │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ Analyst Investigation│
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ Evidence / Reporting│
                 └──────────────────────┘
````

---

# 🖥️ Terminal Interface

AEGIS-X Pro uses a professional terminal interface designed for Windows forensic investigations.

Example:

```text
╔══════════════════════════════════════════════════════════════╗
║                     AEGIS-X PRO                              ║
║              FORENSIC SECURITY PLATFORM                     ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  CORE FORENSICS                                              ║
║  [01] Quick Triage             [02] Network Intelligence     ║
║  [03] Persistence Hunt         [04] File-System Forensics    ║
║  [05] Windows Log Analysis     [06] Process Relationship     ║
║  [07] Security Posture         [08] Findings Center          ║
║                                                              ║
║  ADVANCED ANALYSIS                                           ║
║  [09] File Hash / IOC Analyzer [10] Forensic Timeline        ║
║  [11] Browser Integrity        [12] Live Response            ║
║                                                              ║
║  RESPONSE / EVIDENCE                                         ║
║  [13] Evidence Export          [14] JSON Report              ║
║  [15] Full Security Audit      [16] Refresh / Cache          ║
║                                                              ║
║  SYSTEM                                                       ║
║  [17] Users & Administrators   [18] Security Status          ║
║                                                              ║
║  [0] Exit                                                     ║
╚══════════════════════════════════════════════════════════════╝
```

---

# 📜 Internal Output Viewer

Large forensic scans can generate thousands of lines of output.

AEGIS-X Pro includes an internal output viewer so analysts do not have to rely entirely on the Windows console scrollback buffer.

### Viewer controls

```text
↑ / ↓       Scroll one line
PgUp / PgDn Scroll one page
Home        Go to beginning
End         Go to end
Q / Esc     Exit viewer
```

This makes long forensic reports easier to inspect without losing previously collected output.

---

# 🌐 Network Intelligence

The network engine provides structured information about active network activity.

Example:

```text
[>] Collecting established network connections...

[*] chrome.exe             142.250.xxx.xxx     443    Public
[*] svchost.exe            20.198.xxx.xxx      443    Public
[*] System                  192.168.1.1        53     Private
```

Network records can include:

* Process ID
* Process name
* Executable path
* Remote IP
* Remote port
* Protocol
* IP scope
* Country
* City
* ASN organization
* Connection state

---

# 🌍 GeoIP Support

AEGIS-X Pro can optionally use MaxMind GeoLite databases for IP enrichment.

Supported databases include:

```text
database/
├── GeoLite2-City.mmdb
├── GeoLite2-Country.mmdb
└── GeoLite2-ASN.mmdb
```

Private and local addresses are identified locally and are not unnecessarily sent to the GeoIP database.

---

# 🔐 File Hash / IOC Analysis

AEGIS-X Pro supports file hashing for defensive investigation.

Supported hashes include:

* SHA-256
* MD5

Example:

```text
File:
C:\Suspicious\sample.exe

SHA-256:
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

MD5:
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

Result:
REVIEW REQUIRED
```

Hashing is intended to support:

* Evidence identification
* File comparison
* IOC investigations
* Malware-analysis workflows
* Incident-response documentation

---

# 🧩 Persistence Investigation

AEGIS-X Pro investigates common Windows persistence locations.

Examples include:

```text
Registry Run Keys
Startup Folders
Services
Scheduled Tasks
WMI Event Subscriptions
Drivers
Browser Extensions
```

The tool does not treat every persistence entry as malicious.

Instead, analysts should review:

```text
Location
     ↓
Executable
     ↓
Digital Signature
     ↓
File Hash
     ↓
Parent / Trigger
     ↓
Network Activity
     ↓
Risk Assessment
```

---

# 📊 Security Findings

AEGIS-X Pro can organize findings into severity levels:

```text
HIGH
MEDIUM
LOW
INFO
OK
```

Severity is intended as an investigative priority indicator rather than a definitive malware verdict.

---

# 🧾 Evidence & Reporting

AEGIS-X Pro supports structured forensic evidence collection and report generation.

Reports can contain information such as:

* System information
* Processes
* Network connections
* Listening ports
* Persistence entries
* Services
* Scheduled tasks
* Browser artifacts
* File hashes
* Security findings
* Forensic observations

JSON output can be used for:

* Further analysis
* SIEM ingestion
* Automated processing
* Incident documentation
* Evidence preservation

---

# 🛠️ Requirements

Recommended environment:

```text
Operating System : Windows 10 / Windows 11
Python           : 3.10+
Architecture     : x64
```

Some forensic features may require **Administrator privileges**.

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/Jayasankha-dev/AEGIS-X-Pro.git
```

Enter the project directory:

```bash
cd AEGIS-X-Pro
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run:

```bash
python main.py
```

For the best results, run the terminal as Administrator when investigating protected Windows resources.

---

# 🏗️ Building the Windows EXE

AEGIS-X Pro can be packaged into a Windows executable using PyInstaller.

Example:

```bash
pyinstaller --clean --noconfirm --onefile --console --name "AEGIS-X Pro" main.py
```

The generated executable will normally appear inside:

```text
dist/
```

If the project uses bundled databases or other assets, make sure they are included in the PyInstaller configuration.

---

# 📁 Project Structure

```text
AEGIS-X-Pro/
│
├── main.py
├── scanner.py
├── network.py
├── forensics.py
├── utils.py
│
├── database/
│   ├── GeoLite2-City.mmdb
│   ├── GeoLite2-Country.mmdb
│   └── GeoLite2-ASN.mmdb
│
├── reports/
│
├── evidence/
│
├── requirements.txt
├── build_windows.bat
└── README.md
```

---

# 🔬 Defensive Investigation Example

A typical investigation workflow can look like this:

```text
1. Run Quick Triage
        ↓
2. Review suspicious processes
        ↓
3. Inspect process relationships
        ↓
4. Review network connections
        ↓
5. Check listening ports
        ↓
6. Hunt persistence locations
        ↓
7. Inspect suspicious files
        ↓
8. Calculate file hashes
        ↓
9. Review Windows event logs
        ↓
10. Export evidence
        ↓
11. Generate final report
```

---

# 🚧 Project Status

AEGIS-X Pro is an actively developed project.

Current development focuses on:

* Improved Windows compatibility
* Faster forensic collection
* Better evidence correlation
* Improved risk scoring
* More reliable network analysis
* Better reporting
* Improved terminal usability
* Additional defensive forensic modules

---

# 🔮 Planned Features

Future development may include:

* Advanced forensic timeline visualization
* Improved IOC correlation
* YARA integration
* Sigma rule support
* Windows Event correlation
* PE metadata analysis
* Digital-signature verification improvements
* Evidence integrity verification
* Automated HTML reports
* PDF forensic reports
* Offline threat-intelligence databases
* More advanced process/network correlation
* Plugin architecture
* Optional web-based dashboard

---

# 👨‍💻 Author

**Jayasankha**

GitHub:

[https://github.com/Jayasankha-dev](https://github.com/Jayasankha-dev)

AEGIS-X is developed as a personal defensive cybersecurity and digital-forensics project.

---

# 📄 License

This project is intended for defensive security and authorized forensic investigation.

See the repository license file for the complete licensing terms.

---

# ⭐ Contributing

Contributions, bug reports, feature suggestions, and security improvements are welcome.

Before submitting a pull request:

1. Test the change on a Windows environment.
2. Avoid introducing destructive behavior.
3. Keep forensic collection read-only where possible.
4. Document new modules.
5. Preserve existing evidence formats.
6. Clearly explain security-related changes.

---

# 🔒 Security Philosophy

AEGIS-X follows an **evidence-first** philosophy.

```text
Collect
   ↓
Validate
   ↓
Correlate
   ↓
Analyze
   ↓
Review
   ↓
Report
```

A security tool should help an analyst understand what happened rather than blindly label every unusual event as malicious.

---

## AEGIS-X Pro

**Defensive Security • Digital Forensics • Incident Triage • Evidence Analysis**

Made for investigation.
Built for visibility.
Designed for defense.
