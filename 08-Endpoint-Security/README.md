## Windows Defender Firewall

### Policy

**Name:** SEC-WindowsFirewall-Baseline

**Assignment:** GRP-Intune-Users

### Firewall Rule

**Rule:** Allow-Inbound-ICMPv4

**Action:** Allow

**Direction:** Inbound

**Protocol:** ICMPv4

**ICMP Type:** Echo Request

**Network Type:** Private

### Verification

The policy was successfully assigned to the Windows 11 test device.

The firewall rule was verified locally using PowerShell:

```powershell
Get-NetFirewallRule -PolicyStore ActiveStore |
Where-Object {$_.DisplayName -eq "Allow-Inbound-ICMPv4"} |
Format-List DisplayName,Enabled,Direction,Action,PolicyStoreSource,PolicyStoreSourceType
```

Result:

```text
DisplayName           : Allow-Inbound-ICMPv4
Enabled               : True
Direction             : Inbound
Action                : Allow
PolicyStoreSource     : MDM
PolicyStoreSourceType : MDM
```

The `PolicyStoreSourceType` value of `MDM` confirms that the
firewall rule was deployed through Microsoft Intune rather than
created locally.

### Network Testing

The physical Windows computer successfully pinged the Windows 11
test VM.

This confirmed that the Intune-managed firewall rule allowed
inbound ICMPv4 traffic.

## Result

**Successful**

- [x] Firewall policy created
- [x] Firewall rule created
- [x] Policy assigned
- [x] Intune deployment succeeded
- [x] MDM firewall rule verified
- [x] Inbound ICMPv4 tested
- [x] Ping successful
