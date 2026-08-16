## Troubleshooting: Intune Policy Not Applying

### Problem

The Windows 11 device was enrolled in Intune, but the configuration
profile was not initially appearing in the device assignment report.

### Investigation

- Verified the device was enrolled in Microsoft Intune.
- Verified John Smith was the primary user.
- Verified John Smith was a member of GRP-Intune-Users.
- Verified the configuration profile was assigned to GRP-Intune-Users.
- Checked the device's last Intune check-in.
- Discovered the Windows 11 VM had an incorrect system date/time.

### Root Cause

The Windows 11 VM's system date and time were approximately two days
behind the current date.

### Resolution

Restarted the Windows 11 VM and corrected the system date/time.

### Result

The Intune configuration profile began appearing under the device
configuration status as Pending, indicating that Intune was processing
the assigned policy.

### Lesson Learned

Accurate system time is important for cloud authentication and endpoint
management communications. Incorrect system time can interfere with
authentication, synchronization, and policy processing.
