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
