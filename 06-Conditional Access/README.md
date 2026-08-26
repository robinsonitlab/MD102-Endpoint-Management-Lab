# Microsoft Entra Conditional Access

## Objective

Create and test a Conditional Access policy that requires users to
access cloud resources from a device marked compliant by Microsoft Intune.

## Conditional Access Policy

**Name:** CA-Require-Compliant-Device

**User:** John Smith

**Target resources:** All resources

**Grant control:** Require device to be marked as compliant

**Mode:** Report-only

## Test Environment

**Device:** MD102-WIN11-01

**User:** John Smith

**Compliance Policy:** COMP-Windows11-Baseline

## Test 1 — Compliant Device

The Windows 11 device was compliant because BitLocker was enabled.

The Conditional Access policy was evaluated in Report-only mode.

**Result: Success**

This demonstrated that a compliant device satisfies the Conditional
Access requirement.

## Test 2 — Noncompliant Device

BitLocker was temporarily disabled on the Windows 11 test device.

Intune subsequently reported:

**Device: Noncompliant**

A new John Smith sign-in was performed.

The Conditional Access policy reported:

**Failure**

Because the policy was in Report-only mode, access was not actually
blocked. The result demonstrated that the sign-in would have been
blocked if the policy were enabled.

## Test 3 — Device Remediation

BitLocker was re-enabled and the Windows 11 device was synchronized
with Intune.

Final status:

**MD102-WIN11-01 — Compliant**

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
COMP-Windows11-Baseline
    |
    v
BitLocker
    |
    v
MD102-WIN11-01

## What I Learned

- Conditional Access can use Intune compliance as an access-control signal.
- Report-only mode allows Conditional Access policies to be tested safely.
- A compliant device can satisfy a Conditional Access requirement.
- A noncompliant device causes the Conditional Access requirement to fail.
- Compliance status and Conditional Access work together to enforce
  endpoint security.
- Security Defaults and custom Conditional Access policies are separate
  security approaches.
- Troubleshooting requires testing both the endpoint and cloud service.

## Status

- [x] Create Conditional Access policy
- [x] Target John Smith
- [x] Target all resources
- [x] Require compliant device
- [x] Configure Report-only mode
- [x] Test compliant device
- [x] Test noncompliant device
- [x] Verify Conditional Access failure
- [x] Restore device compliance
- [x] Verify final compliant state
## Troubleshooting: Compliance Status Did Not Immediately Update

### Problem

BitLocker was fully encrypted and Windows reported:

- VolumeStatus: FullyEncrypted
- ProtectionStatus: On
- EncryptionPercentage: 100%

However, Intune continued to report the device as noncompliant.

### Investigation

Windows MDM logs showed DeviceStatus/CertAttestation activity.

The device had been encrypted after the previous boot.

### Resolution

The Windows 11 VM was restarted to allow the device health
attestation state to be refreshed.

After rebooting and synchronizing with Intune, the device changed to:

**Compliant**

### Lesson Learned

Some Intune compliance checks rely on device health attestation
information that is measured during the Windows boot process.

A reboot may therefore be required after changing security
configuration such as BitLocker encryption.
