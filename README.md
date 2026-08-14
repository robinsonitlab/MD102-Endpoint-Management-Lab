# MD102-Endpoint-Management-Lab
MD102-Endpoint-Management-Lab
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
