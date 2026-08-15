# Microsoft Entra ID Configuration

## Objective

Configure Microsoft Entra ID to support Windows 11 device enrollment
and Intune-based endpoint management.

## Users

Created fictional test users representing multiple departments:

- IT
- Sales
- Accounting
- HR

## Security Groups

Created the following groups:

- GRP-IT
- GRP-Sales
- GRP-Accounting
- GRP-HR
- GRP-Intune-Users

## Device Join Configuration

Configured Microsoft Entra ID to allow selected users to join Windows
devices to the organization.

### Configuration

Setting:

Users may join devices to Microsoft Entra ID

Configured as:

Selected

Assigned group:

GRP-Intune-Users

### Purpose

Restrict Microsoft Entra device joining to authorized users rather than
allowing all users in the tenant to join devices.

## Testing

The configuration will be tested using:

User: John Smith

Device:

MD102-WIN11-01

## Status

Configuration completed.

Device enrollment testing is pending.
