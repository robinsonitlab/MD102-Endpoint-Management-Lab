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

