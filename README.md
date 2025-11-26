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
- joined the Windows 10 client to the domain ([1.1](./screenshots/1-what-i-did/1.1.png))
- created users ([1.2](./screenshots/1-what-i-did/1.2.png))
- configured Group Policy settings ([1.3](./screenshots/1-what-i-did/1.3.png))
- configured password policies ([1.4](./screenshots/1-what-i-did/1.4.png))
- created a shared drive and mapped it to a user ([1.5](./screenshots/1-what-i-did/1.5.png))
- confirmed Group Policy settings through gpresult /h report ([1.6](./screenshots/1-what-i-did/1.6.png))

## Issues Encountered
(Screenshots in the 2.x range)

### Simulated Issues
- failed logon attempts and account lockouts ([2.1](./screenshots/2-issues/2.1.png))
- password resets ([2.2](./screenshots/2-issues/2.2.png))
- account expiration testing ([2.3](./screenshots/2-issues/2.3.png))
- account disabled ([2.4](./screenshots/2-issues/2.4.png))
- logon hours restrictions ([2.5](./screenshots/2-issues/2.5.png))
- testing drive mapping ([2.6](./screenshots/2-issues/2.6.png))

### Real Issues
- forgetting to point the client VM's DNS settings at the Domain Controller, causing domain join attempts to fail ([2.7](./screenshots/2-issues/2.7.png))
- choosing VM sizes that fit within Azure's free subscription limits ([2.8](./screenshots/2-issues/2.8.png))
- public IP addresses not being assigned automatically, so I had to configure them manually during VM creation ([2.9](./screenshots/2-issues/2.9.png))

## Tools Used
- Azure Portal
- Remote Desktop Connection (RDP)
- Server Manager
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
- File and Storage Services
- PowerShell

## Conclusion
This lab helped me build a stronger understanding of AD DS, GPOs, and how to troubleshoot common account-related issues in a controlled Azure environment.
