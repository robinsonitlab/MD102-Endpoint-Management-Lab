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
```

## Windows Firewall Profile Verification

The Windows 11 test device was synchronized with Microsoft Intune.

The firewall profiles were verified locally using PowerShell:

```powershell
Get-NetFirewallProfile |
    Select-Object Name, Enabled, DefaultInboundAction, DefaultOutboundAction
```

Result:

```text
Domain   True   NotConfigured   NotConfigured
Private  True   NotConfigured   NotConfigured
Public   True   NotConfigured   NotConfigured
```

All three Windows Firewall profiles were successfully enabled
through the Intune policy.

The default inbound and outbound actions were intentionally left
NotConfigured because this lab exercise focused on centrally
enabling the firewall profiles.
