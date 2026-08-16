# MD-102 Endpoint Management Lab Environment

## Objective

Build a simulated enterprise endpoint management environment to develop
hands-on skills for Microsoft MD-102 and endpoint administration.

## Technologies

- Microsoft 365
- Microsoft Entra ID
- Microsoft Intune
- Windows 11 Enterprise
- VMware Workstation
- GitHub

## Lab Architecture

Microsoft 365 Tenant
        |
        +-- Microsoft Entra ID
        |
        +-- Microsoft Intune
        |
        +-- Test Users
        |
        +-- Security Groups
        |
        +-- Windows 11 Virtual Machines

## Virtual Machines

| Device | Operating System | Purpose |
|---|---|---|
| MD102-WIN11-01 | Windows 11 Enterprise | Primary test device |
| MD102-WIN11-02 | Windows 11 Enterprise | Future test/pilot device |

## Microsoft Entra Users

The lab uses fictional test identities to simulate an enterprise environment.

Examples:

- John Smith
- Sarah Jones
- Mike Brown
- Lisa Brown
- Tom Wilson
- Amy Davis
- Mark Davis
- Jennifer Lee

## Security Groups

- GRP-IT
- GRP-Sales
- GRP-Accounting
- GRP-HR
- GRP-Intune-Users

## Lab Objectives

- Configure Microsoft Entra ID
- Configure Microsoft Intune
- Enroll Windows devices
- Deploy configuration profiles
- Create compliance policies
- Configure Conditional Access
- Deploy applications
- Manage Windows Updates
- Configure endpoint security
- Practice Windows Autopilot
- Troubleshoot endpoint management issues

## Current Progress

- [x] Microsoft 365 tenant configured
- [x] Windows 11 VM created
- [x] Microsoft Entra users created
- [x] Microsoft Entra security groups created
- [x] Intune access verified
- [x] Intune trial licenses obtained
- [x] Test user licensed for Intune
- [x] Microsoft Entra device join configured
- [x] Intune automatic enrollment configured
- [x] Windows device enrolled
- [x] Enrollment restrictions verified
- [x] Windows 11 VM joined to Microsoft Entra ID
- [x] AzureAdJoined verified
- [x] Intune device enrollment verified
- [ ] Configuration profiles
- [ ] Compliance policies
- [ ] Conditional Access
- [ ] Application deployment
- [ ] Windows Update management
- [ ] Endpoint security
- [ ] Windows Autopilot
