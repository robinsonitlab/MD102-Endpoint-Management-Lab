# Intune Win32 Application Deployment

## Objective

Package and deploy a Windows application using Microsoft Intune
Win32 application management.

## Application

**Application:** 7-Zip

**Version:** 25.01

**Architecture:** 64-bit

**Install behavior:** System

## Packaging

The 7-Zip installer was packaged using the Microsoft Win32 Content
Prep Tool.

Output:

7z2501-x64.intunewin

## Installation Command

7z2501-x64.exe /S

## Uninstall Command

"C:\Program Files\7-Zip\Uninstall.exe" /S

## Detection Rule

**Detection Type:** File

**Path**
C:\Program Files\7-Zip

**File**
7zFM.exe

**Detection Method:** File or folder exists

## Assignment

The application was assigned as:

**Required**

Target group:

**GRP-Intune-Users**

## Test Device

Device: MD102-WIN11-01

User: John Smith

7-Zip was successfully deployed to the Windows 11 test device.

The application was verified on the endpoint using:

</> PowerShell

Test-Path "C:\Program Files\7-Zip\7zFM.exe"

Result:

True

Intune subsequently reported:

**Device install status: Installed**

## What I Learned
* Win32 applications must be packaged into an .intunewin file.
* The Microsoft Win32 Content Prep Tool can package Windows installers.
* Intune uses detection rules to determine whether an application is installed.
* Applications can be assigned as Required to Entra security groups.
* System installation allows applications to install without requiring the user to perform the installation.
* Intune reporting can be used to verify application deployment.
* Endpoint verification is important in addition to Intune reporting.

## Deployment Workflow
1. Download application installer.
2. Create packaging directory.
3. Package installer with Win32 Content Prep Tool.
4. Upload .intunewin package to Intune.
5. Configure installation commands.
6. Configure requirements.
7. Configure detection rule.
8. Assign application to test group.
9. Sync endpoint.
10. Verify application installation.
11. Verify Intune installation status.

## Status
* Download application
* Package application
* Upload to Intune
* Configure install command
* Configure uninstall command
* Configure requirements
* Configure detection rule
* Assign application
* Deploy application
* Verify application on endpoint
* Verify Intune status
