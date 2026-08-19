# Intune Compliance Policy

## Objective

Create and test a Microsoft Intune compliance policy that requires
BitLocker encryption on Windows 11 devices.

## Compliance Policy

**Name:** COMP-Windows11-Baseline

**Platform:** Windows 10 and later

**Assignment:** GRP-Intune-Users

## Compliance Requirement

### BitLocker

**Requirement:** Require BitLocker

The policy requires Windows devices to have BitLocker encryption enabled
in order to be considered compliant.

## Initial Compliance Test

The test device was initially reported as:

**Noncompliant**

The reason was:

**BitLocker — Not compliant**

### Initial BitLocker State

The Windows 11 VM was checked using:

```powershell
Get-BitLockerVolume
