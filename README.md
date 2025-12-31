# Argus PC Check
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/SeraphV2/Argus-PC-Check)

Argus is a PowerShell script designed for PC integrity checks within competitive gaming communities. It scans a user's computer for evidence of cheating software, unauthorized modifications, and other suspicious artifacts. The script features a user-friendly GUI and generates a comprehensive report packaged in a single ZIP file for easy review by an administrator or operator.

## Features

- **Graphical User Interface (GUI):** A simple interface for initiating scans, requiring only operator and player names.
- **Pre-configured Scan Profiles:** Includes tailored scans for popular games like FiveM/GTA, Call of Duty, Rainbow Six Siege, and Valorant, plus a comprehensive "ALL GAMES" option.
- **Multi-faceted Scanning:**
    - **Registry:** Scans keys and values for suspicious keywords.
    - **Startup Programs:** Checks common startup folders for malicious files.
    - **Scheduled Tasks:** Lists scheduled tasks that may be used for persistence.
    - **Services & Drivers:** Examines system services and drivers for known cheat-related components.
- **Artifact Collection:**
    - **USB History:** Gathers a history of all USB devices connected to the machine.
    - **Event Logs:** Searches Windows Event Logs (System, Application, Security) for keywords associated with cheating.
- **Intelligent Filtering:** Utilizes a severity-based keyword system (High, Medium, Low) and a whitelist to minimize false positives from legitimate software (e.g., NVIDIA, Steam, Discord).
- **Comprehensive Reporting:** Generates a primary text report, a CSV timeline of all findings, USB history, and relevant event logs.
- **Packaged Evidence:** All generated reports are automatically compressed into a single `.zip` archive on the user's Desktop for easy submission.

## How to Use

1.  Download the `Argus_PCCheck.ps1` script file.
2.  Right-click the file and select **Run with PowerShell**.
3.  If you encounter an error related to execution policies, you may need to run the following command in a PowerShell terminal and then try again:
    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```
4.  The Argus PC Integrity window will appear.
5.  Enter the name of the **Operator** (the person conducting the check) and the **Player** (the person being checked).
6.  Click the button corresponding to the game or profile you wish to scan.
7.  Wait for the scan to complete. A progress bar will show the status.
8.  Once finished, a `PC_EVIDENCE_{PCName}_{Timestamp}.zip` file will be created on your Desktop. This file contains all the scan results.

## Output Files

The scan generates a single ZIP archive on the user's desktop, containing the following files:

-   `PC_Check_{PC_Name}_{Game}_{Timestamp}.txt`: A human-readable summary of the scan, listing artifacts found, categorized by severity.
-   `Timeline.csv`: A detailed, chronological log of all flagged artifacts with their type, path, and severity.
-   `USBHistory.csv`: A report listing all USB devices ever connected to the PC, including device description, serial number, and connection times.
-   `EventLogs.csv`: A collection of entries from Windows Event Logs that match suspicious keywords.

## Detection Keywords

Argus uses keyword matching to identify potentially malicious files, registry entries, and processes.

#### High Severity
```
dma, pcileech, leechcore, fpga, kdmapper, mapper, spoof, ring0
```

#### Medium Severity
```
cheat, aimbot, esp, wallhack, inject, loader, overlay, trigger
```

#### Low Severity
```
menu, cfg, lua, script
```

## Whitelist

To reduce false positives, the script ignores paths and names containing keywords related to common, legitimate software.

```
nvidia, amd, microsoft, windows, steam, obs, logitech, razer, corsair, epic, battlenet, riot
```

## Disclaimer

This tool is intended for authorized integrity scans where user consent has been explicitly given. It should be used responsibly by community administrators and event operators to ensure fair play.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.