Argus – PC Integrity & Cheat Check Tool






Argus is a user-consented, audit-safe PC integrity checker for detecting potential cheat artifacts in major games like FiveM/GTA, Call of Duty, Rainbow Six Siege, Valorant, and more. It uses Windows-exposed data only, ensuring safe, non-intrusive auditing.

📥 Download

Download Argus_PCCheck.ps1
 – raw script for PowerShell

🚀 Features
Core Scans

Registry (startup entries, software keys, drivers/services)

Startup folders & scheduled tasks

Services & drivers enumeration

File hashes (SHA256) & digital signatures

Timeline of suspicious artifacts

USB history (device ID, serial, first/last connected)

Event logs filtered for cheat-related keywords

GUI Features

Dark mode

Operator & Player fields

Game-specific buttons + ALL GAMES option

Progress bar & live scan timer

ZIP evidence bundle (Desktop)

Safety & Compliance

Fully consent-based

Audit-safe; no memory scanning

Non-intrusive; read-only Windows data

Complete ZIP evidence bundle for audits

⚙️ Setup Instructions
1. Clone or Download Script
git clone https://github.com/SeraphV2/Argus-PCCheck.git


Or download directly:
Argus_PCCheck.ps1

2. Set PowerShell Execution Policy
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser


Or, if running directly from GitHub:

Set-ExecutionPolicy Bypass -Scope CurrentUser

3. Run Locally
cd C:\Tools
.\Argus_PCCheck.ps1


Fill in Operator and Player fields

Click the game button or ALL GAMES

View progress bar and live timer

ZIP evidence bundle appears on the Desktop

4. Run Directly from GitHub
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/SeraphV2/Argus-PCCheck/main/Argus_PCCheck.ps1" -OutFile "$env:TEMP\Argus_PCCheck.ps1"
powershell -ExecutionPolicy Bypass -File "$env:TEMP\Argus_PCCheck.ps1"


Downloads the script to TEMP

Launches GUI automatically

5. Optional: Desktop Shortcut

Target:

powershell.exe -ExecutionPolicy Bypass -Command "Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/SeraphV2/Argus-PCCheck/main/Argus_PCCheck.ps1' -OutFile '$env:TEMP\Argus_PCCheck.ps1'; powershell -ExecutionPolicy Bypass -File '$env:TEMP\Argus_PCCheck.ps1'"


One-click GUI launch

📦 Output

All outputs are saved in a ZIP evidence bundle on Desktop:

Report.txt – complete scan report

Timeline.csv – artifact timestamps

FileHashes.csv – SHA256 & digital signatures

USBHistory.csv – connected USB devices

EventLogs.csv – filtered system/application/security events

🛡️ Safety & Usage Notes

Operator consent is required

Some scans may require administrator privileges

Script is read-only; does not modify system

🎮 Supported Games

FiveM / GTA

Call of Duty

Rainbow Six Siege

Valorant

ALL GAMES (high/medium/low-risk keywords)

📌 Changelog

v1.0 – Initial release

Full GUI

Registry, Startup, Services/Drivers, USB, Event Logs scans

Timeline & file hashes

Progress bar + live timer

ZIP evidence bundle
