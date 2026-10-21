# SMB File Sharing Configuration

## Overview
Configured SMB file sharing on Windows Server to provide centralized access to files for domain users.

## Environment
- Windows Server
- Active Directory domain: Bookstore.com
- Windows client joined to the domain
- SMB network share: `\\OWNER\shares`

## Configuration
- Created a shared folder on Windows Server
- Configured share and NTFS permissions
- Configured network access for domain users
- Deployed the shared drive using Group Policy Preferences

## Permission Levels
- Read: View and open files
- Modify: Read, create, edit and delete files
- Full Control: Modify files and change NTFS permissions

## Verification
- Successfully accessed the network share from a domain-joined Windows client
- Verified that the mapped S: drive appeared in File Explorer

## Purpose
Practice Windows Server file sharing, SMB permissions and centralized file access management.
