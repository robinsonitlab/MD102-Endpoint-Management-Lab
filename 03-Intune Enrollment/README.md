# Microsoft Intune Windows Enrollment

## Objective

Configure automatic enrollment of Windows 11 devices into Microsoft
Intune through Microsoft Entra ID.

## Licensing

The lab administrator is licensed through:

- Microsoft 365 Business Premium with Copilot

The test user is licensed through:

- Microsoft Intune trial

The Intune trial provides additional licenses for lab users.

## Automatic Enrollment Configuration

Configured automatic enrollment under:

Intune Admin Center
→ Devices
→ Enrollment
→ Windows
→ Automatic Enrollment

### MDM User Scope

Configured:

Some

Assigned group:

GRP-Intune-Users

### WIP User Scope

Configured:

None

## Enrollment Workflow

The intended enrollment process is:

John Smith
    |
    v
Microsoft Entra ID
    |
    v
Windows 11 Device Join
    |
    v
Automatic MDM Enrollment
    |
    v
Microsoft Intune
    |
    v
Device Management

## Test Device

Device:

MD102-WIN11-01

Test User:

John Smith

## Current Status

Automatic Intune enrollment has been configured.

Windows device enrollment has not yet been completed.

## Next Steps

1. Verify Windows enrollment restrictions.
2. Join MD102-WIN11-01 to Microsoft Entra ID.
3. Verify automatic Intune enrollment.
4. Confirm device appears in Intune.
5. Verify device synchronization and management status.

# Microsoft Intune Windows Enrollment

## Objective

Configure and test automatic enrollment of a Windows 11 device into
Microsoft Intune through Microsoft Entra ID.

The goal of this lab is to simulate an enterprise Windows endpoint
deployment and demonstrate the ability to configure, enroll, manage,
and troubleshoot Windows devices using Microsoft Entra ID and Microsoft Intune.

---

## Lab Environment

### Cloud Services

- Microsoft 365
- Microsoft Entra ID
- Microsoft Intune

### Virtualization

- VMware Workstation

### Test Device

- Device Name: MD102-WIN11-01
- Operating System: Windows 11 Enterprise
- Device Type: Virtual Machine

### Test User

- User: John Smith
- Department: IT
- Group: GRP-Intune-Users

---

## Licensing

The lab administrator is licensed through:

- Microsoft 365 Business Premium with Copilot

The test user is licensed through:

- Microsoft Intune Trial

The Intune trial provides additional licenses for testing Windows
endpoint enrollment and management.

---

## Microsoft Entra ID Configuration

### Device Join Permissions

Configured Microsoft Entra ID to allow selected users to join devices
to Microsoft Entra ID.

**Setting:**

Users may join devices to Microsoft Entra ID

**Configuration:**

Selected

**Assigned Group:**

GRP-Intune-Users

This restricts device joining to authorized lab users.

---

## Intune Automatic Enrollment

Configured automatic MDM enrollment in the Microsoft Intune admin center.

**Location:**

Devices → Enrollment → Windows → Automatic Enrollment

### MDM User Scope

**Configuration:**

Some

**Assigned Group:**

GRP-Intune-Users

### WIP User Scope

**Configuration:**

None

This configuration allows members of GRP-Intune-Users to automatically
enroll their Windows devices into Microsoft Intune when they join
the device to Microsoft Entra ID.

---

## Enrollment Restrictions

Reviewed the default enrollment restriction policy:

**Policy:** All Users

### Windows Configuration

- Windows (MDM): Allow
- Personally owned devices: Allow

Personally owned Windows devices were allowed for the initial lab
enrollment to simplify testing.

This setting will be revisited later when testing corporate-owned
devices and Windows Autopilot.

---

## Device Enrollment

### Device

MD102-WIN11-01

### Enrollment User

John Smith

The Windows 11 virtual machine was successfully joined to
Microsoft Entra ID using the John Smith test account.

### Verification

The following command was used to verify the Microsoft Entra join:

```powershell
dsregcmd /status

# Intune Configuration Profiles

## Objective

Create and deploy a Windows 11 configuration profile using Microsoft
Intune Settings Catalog.

## Configuration Profile

**Name:** CFG-Windows11-Baseline

**Platform:** Windows 10 and later

**Profile type:** Settings catalog

**Assignment:** GRP-Intune-Users

## Configured Settings

### Enable screen saver

**Setting:** Enable screen saver (User)

**Configuration:** Enabled

### Screen saver timeout

**Setting:** Screen saver timeout (User)

**Configuration:** 300 seconds

### Password protection

**Setting:** Password protect the screen saver (User)

**Configuration:** Enabled

## Deployment

The configuration profile was assigned to:

GRP-Intune-Users

The test user, John Smith, is a member of this group.

The target device is:

MD102-WIN11-01

## Verification

The Windows 11 device successfully synchronized with Microsoft Intune.

The configuration profile reported:

**Succeeded**

## Troubleshooting

### Issue

The configuration profile initially remained in Pending status.

### Investigation

The Windows VM was found to have an incorrect system date/time and
later experienced a VMware NAT networking issue.

### Resolution

The VMware virtual network was restored and the Windows VM regained
Internet connectivity.

After connectivity was restored:

- Microsoft Entra authentication succeeded.
- AzureAdPrt changed to YES.
- Intune synchronization succeeded.
- Configuration profile status changed to Succeeded.

## What I Learned

- Intune configuration profiles can be targeted using Entra security groups.
- User-scoped settings can be assigned to user groups.
- Intune policy deployment depends on successful device communication.
- Windows system time and network connectivity can affect cloud
  authentication and endpoint management.
- Intune reporting can be used to verify policy deployment.
- Successful policy processing should be verified on both the Intune
  side and the Windows endpoint.

## Status

- [x] Create configuration profile
- [x] Configure Settings Catalog
- [x] Assign policy to security group
- [x] Sync Windows device
- [x] Verify Intune deployment
- [x] Troubleshoot deployment
