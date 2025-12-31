Argus

PC Integrity & Cheat Check Tool

A user‑consented, audit‑safe integrity checker that detects potential cheat artifacts in popular games — using only Windows‑exposed data.
⚡ Quick Start
Direct Run (One‑Click)
powershell

irm https://raw.githubusercontent.com/SeraphV2/Argus-PCCheck/main/Argus_PCCheck.ps1 | iex

Downloads and runs the GUI immediately.
Traditional Download

    Download Argus_PCCheck.ps1

    Run in PowerShell:
    powershell

.\Argus_PCCheck.ps1

✨ What Argus Does
Feature	Description
Registry Scan	Startup entries, installed software, drivers
File Analysis	SHA‑256 hashes + digital signature verification
USB History	Device IDs, serials, connection timestamps
Event Logs	Filtered for cheat‑related keywords
Services & Tasks	Running services + scheduled tasks
Timeline	Chronological artifact tracking
GUI Interface	Dark mode, progress bar, live timer
Evidence Bundle	Auto‑ZIPs all findings to Desktop
🛠️ Setup & Usage
1. Execution Policy (One‑Time)
powershell

# Allow local scripts
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

2. Run with GUI
powershell

# After download
.\Argus_PCCheck.ps1

    Enter Operator and Player names

    Select a game or ALL GAMES

    Watch real‑time progress

    Find Argus_Evidence_YYYYMMDD.zip on your Desktop

3. Remote Execution
powershell

# Download + run in temporary location
$url = "https://raw.githubusercontent.com/SeraphV2/Argus-PCCheck/main/Argus_PCCheck.ps1"
$temp = "$env:TEMP\Argus.ps1"
Invoke-WebRequest -Uri $url -OutFile $temp
powershell -ExecutionPolicy Bypass -File $temp

📊 Output Files

All evidence is packaged into a single ZIP file containing:
text

📁 Argus_Evidence_20241201.zip
├── 📄 Report.txt          # Full scan report
├── 📄 Timeline.csv        # Artifact timeline
├── 📄 FileHashes.csv      # SHA‑256 + signatures
├── 📄 USBHistory.csv      # USB connection history
└── 📄 EventLogs.csv       # Filtered Windows events

🎯 Supported Games

    FiveM / Grand Theft Auto V

    Call of Duty series

    Rainbow Six Siege

    Valorant

    All Games (generic cheat detection)

Detection uses game‑specific signatures + heuristic analysis.
🔒 Safety & Compliance

✅ Consent‑Based – Requires operator approval
✅ Read‑Only – Never modifies system files
✅ No Memory Scanning – Audit‑safe Windows APIs only
✅ Transparent – All findings exportable for review
⚠️ Admin Recommended – Some scans need elevated rights
📁 Project Structure
text

Argus-PCCheck/
├── Argus_PCCheck.ps1      # Main script
├── README.md              # This file
└── LICENSE                # MIT License

❓ FAQ

Q: Does Argus modify my system?
A: No. It only reads Windows‑exposed data.

Q: Can I run it without admin rights?
A: Yes, but some scans will be limited.

Q: Where is data saved?
A: All output goes to a ZIP on your Desktop.

Q: Is this against game ToS?
A: Argus is for consensual audits only. Check your game's policies.
📜 Changelog
v1.0

    Initial public release

    Full GUI with dark mode

    Game‑specific detection profiles

    USB history + event log parsing

    ZIP evidence bundling

📄 License

MIT License – see LICENSE for details.
⚠️ Disclaimer

Use Argus only on systems you own or have explicit permission to audit. The authors are not responsible for misuse or violations of game Terms of Service.

GitHub: https://github.com/SeraphV2/Argus-PCCheck
Issues: Report a bug or request a feature

Built for competitive integrity. 🛡️
