# Microsoft Entra Conditional Access

## Objective

Create and test a Conditional Access policy requiring users to access
cloud resources from devices marked compliant by Microsoft Intune.

## Conditional Access Policy

**Name:** CA-Require-Compliant-Device

**User:** John Smith

**Target resources:** All resources

**Grant control:** Require device to be marked as compliant

**Policy mode:** Report-only

## Prerequisites

The Windows 11 test device was enrolled in Microsoft Intune and assigned
the following compliance policy:

COMP-Windows11-Baseline

The device was required to have BitLocker enabled.

## Compliance Status

Before remediation:

**MD102-WIN11-01 — Noncompliant**

Reason:

**BitLocker — Not compliant**

After enabling BitLocker:

**MD102-WIN11-01 — Compliant**

## Conditional Access Testing

A new sign-in was performed using John Smith.

The Conditional Access policy was evaluated in Report-only mode.

### Result

**CA-Require-Compliant-Device — Success**

The policy successfully evaluated the sign-in while requiring the device
to be marked as compliant.

## Architecture

John Smith
    |
    v
Microsoft Entra ID
    |
    v
Conditional Access
    |
    v
Require compliant device
    |
    v
Microsoft Intune
    |
    v
MD102-WIN11-01
    |
    v
Compliance Policy
    |
    v
BitLocker = Enabled
    |
    v
COMPLIANT

## What I Learned

- Conditional Access controls access to cloud resources based on conditions.
- Intune compliance policies determine whether a device meets security requirements.
- Conditional Access can use Intune compliance as an access-control signal.
- Report-only mode allows policies to be tested before enforcement.
- Security Defaults and custom Conditional Access policies are separate
  security approaches.
- Disabling Security Defaults in the lab allowed custom Conditional Access
  policies to be tested.

## Status

- [x] Create Conditional Access policy
- [x] Target test user
- [x] Target cloud resources
- [x] Require compliant device
- [x] Configure Report-only mode
- [x] Generate test sign-in
- [x] Verify Conditional Access evaluation
- [x] Policy result = Success
