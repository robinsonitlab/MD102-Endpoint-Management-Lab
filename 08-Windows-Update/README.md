# Windows Update Management

## Objective

Create and deploy a Windows Update ring using Microsoft Intune to
manage Windows Update behavior on a Windows 11 pilot device.

## Update Ring

Name: UPD-Windows11-Pilot

Assignment: GRP-Intune-Users

Test Device: MD102-WIN11-01

Test User: John Smith

## Configuration

- Microsoft product updates: Allow
- Windows drivers: Allow
- Quality update deferral: 0 days
- Feature update deferral: 0 days
- Feature update uninstall period: 10 days
- Automatic update behavior: Auto install at maintenance time
- Active hours: 8 AM – 5 PM
- Pause updates: Disabled
- Check for updates: Enabled
- Feature update deadline: 7 days
- Quality update deadline: 7 days
- Grace period: 2 days
- Auto reboot before deadline: Yes

## Verification

The update ring was successfully assigned to the test device.

After synchronizing the Windows 11 VM with Intune, the Windows Update
settings were checked locally.

The **Pause updates** option was unavailable, confirming that the
Intune configuration was applied to the endpoint.

## What I Learned

- Intune Update Rings can centrally manage Windows Update behavior.
- Update Rings can be assigned to Entra security groups.
- Update deferrals control when updates become available.
- Deadlines establish when updates must be installed.
- Grace periods provide additional time before required restarts.
- Intune can restrict end-user Windows Update options.
- Endpoint verification is important when validating Intune policies.

## Status

- [x] Create Update Ring
- [x] Configure update settings
- [x] Configure deadlines
- [x] Assign to security group
- [x] Verify assignment
- [x] Sync endpoint
- [x] Verify Windows Update settings
- [x] Verify Pause updates is unavailable
