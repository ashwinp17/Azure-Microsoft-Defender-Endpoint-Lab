# Azure Microsoft Defender for Endpoint Lab

## Project Overview

This lab focused on identity and access management, least privilege, endpoint security, and SOC-style alert investigation in a Microsoft Azure environment.

I created test employee accounts in Microsoft Entra ID, assigned role-based permissions, deployed and monitored a Windows Server virtual machine, onboarded the endpoint to Microsoft Defender for Endpoint, simulated suspicious PowerShell activity, and investigated the resulting security alert.

---

## Technologies Used

- Microsoft Azure
- Microsoft Entra ID
- Azure Role-Based Access Control (RBAC)
- Windows Server 2022
- Microsoft Defender for Endpoint
- Microsoft Defender for Cloud
- PowerShell
- Remote Desktop Protocol (RDP)
- Microsoft Defender Live Response

---

## 1. Identity and Access Management

Created test employee accounts in Microsoft Entra ID to simulate users with different responsibilities within an organization.

The accounts included:

- David Developer
- Hannah HR
- Sarah Security

![Microsoft Entra ID Users](screenshots/01-entra-users.png)

---

## 2. Least-Privilege RBAC

Assigned Azure roles based on each user's job responsibilities:

- David Developer — Contributor
- Hannah HR — Reader
- Sarah Security — Security Reader

This demonstrated the principle of least privilege by ensuring users only received the permissions necessary to perform their responsibilities.

![Azure RBAC Role Assignments](screenshots/02-rbac-role-assignments.png)

---

## 3. Security Role Assignment

Assigned the Security Operator role to the Sarah Security account.

This role allows a security-focused user to work with security events without providing unnecessary administrative permissions.

![Security Operator Role](screenshots/03-security-operator-role.png)

---

## 4. Azure Windows Server Deployment

Deployed a Windows Server virtual machine in Microsoft Azure to act as the endpoint for the security monitoring portion of the lab.

The server was used for Microsoft Defender for Endpoint onboarding, attack simulation, and security investigation.

![Azure Windows VM](screenshots/04-azure-windows-vm.png)

---

## 5. Microsoft Defender for Endpoint Onboarding

Verified that Microsoft Defender for Endpoint was running on the Windows Server.

PowerShell was used to confirm that the Microsoft Defender Advanced Threat Protection service was running and that the device had successfully completed the onboarding process.

The onboarding status returned:

```text
Sense: Running
OnboardingState: 1
