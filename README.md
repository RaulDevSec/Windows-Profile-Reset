# Windows-Profile-Reset

PowerShell automation tool designed to securely reset Windows user profiles. The script validates administrative privileges, detects and terminates active user sessions, removes associated registry profile entries, renames user directories, and provides structured execution feedback.

## Purpose

This tool was created to automate the manual process of resetting corrupted or problematic Windows user profiles in enterprise and IT support environments.
Instead of manually editing the registry and renaming profile folders, this script ensures a controlled, repeatable, and secure remediation workflow.

## How It Works

1. Verifies whether the script is running with administrative privileges.
   If not, it automatically relaunches a new elevated PowerShell instance and prompts for administrator credentials. 
2. Prompts for the target username.
3. Verifies if the user session is active and logs it off if necessary.
4. Searches and removes the user profile entry from:
   HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList
5. Renames the user profile folder from:
   C:\Users\username → C:\Users\username.old
6. Displays confirmation of successful execution.

## Requirements

- Windows OS
- PowerShell 5.1+
- Administrative privileges

## Security Considerations

- Must be executed with administrative privileges.
- Logging off an active session may cause unsaved data loss.
- Registry modification is permanent and should be used cautiously.
- Intended for controlled IT environments.
