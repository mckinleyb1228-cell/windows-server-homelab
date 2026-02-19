# Active Directory Domain Controller Lab

## Project Overview
Built a Windows Server 2022 Domain Controller in a VirtualBox lab environment to simulate enterprise Active Directory infrastructure.

## Environment
- Host OS: Windows 11 Home
- Hypervisor: Oracle VirtualBox
- Server OS: Windows Server 2022 Evaluation
- Domain Name: lab.local
- DC Name: LAB-DC01
- Network Type: Host-Only Adapter
- Static IP: 192.168.56.10

## Objectives
- Deploy Windows Server VM
- Configure static IP and DNS
- Install AD DS role
- Promote server to Domain Controller
- Validate AD functionality using PowerShell
- Enable remote access via RustDesk + Tailscale

## Build Steps

### 1. VM Creation
- Created new VM in VirtualBox
- Allocated 60GB dynamically expanding disk
- Attached Windows Server 2022 ISO

### 2. Network Configuration
- Configured Host-Only adapter
- Assigned static IP address
- Set DNS to self (192.168.56.10)

### 3. AD DS Installation
- Installed Active Directory Domain Services role
- Promoted server to new forest: lab.local

### 4. Validation
- Imported ActiveDirectory module
- Ran:
  - Import-Module ActiveDirectory
  - Get-ADDomain
- Confirmed domain operational

## Remote Access Setup
- Installed Tailscale on host machine
- Installed RustDesk for remote desktop access
- Configured power settings to prevent sleep

## Lessons Learned
- DNS must point to domain controller for AD to function
- PowerShell modules must be imported before AD cmdlets are available
- Static IP is critical before promoting to DC
- Remote access requires sleep to be disabled

## Next Steps
- Create Organizational Units
- Create test users and groups
- Join Windows 11 client VM to domain
- Implement Group Policy Objects
- Automate user creation with PowerShell
