# Azure-Hosted Active Directory Environment
## Overview
In this lab, I set up Active Directory Domain Services (AD DS) using Azure Cloud Services to provide a reliable environment for testing. I engaged with core AD administration tasks and focussed on troubleshooting common account-related issues.

## Environment Details

### Virtual Machines (VMs)
- Azure VM running Windows Server 2019 (Domain Controller)
- Azure VM running Windows 10 (Client)

### Network
- Subnet `172.16.0.0/24`
- Domain Controller private IP: `172.16.0.4` (static)
- DNS: Domain Controller configured as the primary DNS server
- Domain: `duman.local`

## Network Topology

```
Azure Cloud
 ├── Windows Server 2019 (Domain Controller)
 │     ├── IP: 172.16.0.4
 │     └── DNS for domain: duman.local
 └── Windows 10 Client
       └── Uses Domain Controller as DNS
```

## What I Did
(Screenshots in the 1.x range)

I carried out the following Active Directory administration tasks:
- joined the Windows 10 client to the domain (1.1)
- created users (1.2)
- configured Group Policy settings (1.3)
- configured password policies (1.4)
- created a shared drive and mapped it to a user (1.5)
- confirmed Group Policy settings through gpresult /h report (1.6)

## Issues Encountered
(Screenshots in the 2.x range)

### Simulated Issues
- failed logon attempts and account lockouts (2.1)
- password resets (2.2)
- account expiration testing (2.3)
- account disabled (2.4)
- logon hours restrictions (2.5)
- testing drive mapping (2.6)

### Real Issues
- forgetting to point the client VM's DNS settings at the Domain Controller, causing domain join attempts to fail (2.7)
- choosing VM sizes that fit within Azure's free subscription limits (2.8)
- public IP addresses not being assigned automatically, so I had to configure them manually during VM creation (2.9)

## Tools Used
- Azure Portal
- Remote Desktop Connection (RDP)
- Server Manager
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
- File and Storage Services
- PowerShell

## Screenshots and Notes

## Conclusion
This lab helped me build a stronger understanding of AD DS, GPOs, and how to troubleshoot common account-related issues in a controlled Azure environment.
