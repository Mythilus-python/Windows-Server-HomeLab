# SMB File Sharing Configuration

## Overview
Configured SMB file sharing on Windows Server to provide centralized file access for domain users in an Active Directory environment.

## Environment
- Windows Server
- Active Directory domain: Bookstore.com
- Domain-joined Windows client
- Server hostname: OWNER
- SMB network shares:
  - `\\OWNER\Shares`
  - `\\OWNER\Accounting`

## Configuration
- Created shared folders on Windows Server.
- Configured SMB share permissions and NTFS permissions.
- Configured network access for domain users.
- Deployed the shared drive using Group Policy Preferences.
- Mapped `\\OWNER\Shares` as network drive `S:`.

## Permission Levels
- **Read:** View and open files.
- **Modify:** Read, create, edit and delete files.
- **Full Control:** Modify files, change NTFS permissions and take ownership.

### Accounting Permissions
- SMB Share Permissions: Everyone - Read Only
- NTFS Permissions: Domain Users - Modify
- Administrators and SYSTEM - Full Control

**Note:** SMB share permissions and NTFS permissions work together. The most restrictive effective permission limits access. The observed file modification behavior requires further investigation because the displayed SMB share permission is Read Only.

## Verification
- Successfully accessed the SMB network shares from a domain-joined Windows client.
- Verified that the mapped `S:` drive appeared in File Explorer.
- Confirmed Group Policy application using `gpresult /r`.
- Accessed `\\OWNER\Accounting` using the domain account `ad
