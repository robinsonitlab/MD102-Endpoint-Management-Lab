## Microsoft Defender Antivirus

### Policy

**Name:** SEC-DefenderAV-Baseline

**Assignment:** GRP-Intune-Users

### Configured Settings

- Real-time monitoring: Allowed
- Cloud protection: Allowed
- Behavior monitoring: Allowed
- Scanning of downloaded files and attachments: Allowed

### Verification

The Windows 11 test device was synchronized with Microsoft Intune.

PowerShell was used to verify Microsoft Defender status:

```powershell
Get-MpComputerStatus | Select-Object `
    AntivirusEnabled,
    RealTimeProtectionEnabled,
    BehaviorMonitorEnabled,
    IoavProtectionEnabled,
    AMServiceEnabled
