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

```

![Microsoft Defender Onboarding](screenshots/05-mde-onboarding.png)

---

## 6. Controlled PowerShell Attack Simulation

Connected to the Windows Server through Remote Desktop and executed a controlled PowerShell attack simulation.

The script was intentionally run in the lab environment to generate suspicious endpoint behavior that Microsoft Defender for Endpoint could detect.

```powershell
& "C:\Users\azureuser\Downloads\AttackScript.ps1"
```

![PowerShell Attack Simulation](screenshots/06-attack-script-execution.png)

---

## 7. Microsoft Defender Alert Investigation

Microsoft Defender for Endpoint generated a Medium-severity alert after detecting abnormal process behavior on the Windows Server.

I reviewed the alert details and process tree to understand the chain of execution and determine why the behavior was considered suspicious.

The investigation included reviewing:

- Alert severity
- Affected endpoint
- Logged-on user
- Process relationships
- Suspicious PowerShell activity
- Parent and child processes

![Microsoft Defender Alert Investigation](screenshots/07-defender-alert-investigation.png)

---

## 8. Microsoft Defender Live Response

Used Microsoft Defender Live Response to establish a remote investigation session with the Windows Server.

Live Response provides security analysts with a remote shell that can be used to investigate endpoints, collect information, and perform response actions.

![Microsoft Defender Live Response](screenshots/08-live-response.png)

---

## Skills Demonstrated

- Microsoft Defender for Endpoint
- Endpoint Detection and Response (EDR)
- Security Alert Investigation
- SOC Alert Triage
- Process Tree Analysis
- PowerShell Analysis
- Microsoft Entra ID
- Azure RBAC
- Identity and Access Management
- Principle of Least Privilege
- Azure Virtual Machines
- Windows Server Administration
- Remote Desktop Protocol (RDP)
- Microsoft Defender Live Response
- Endpoint Onboarding

---

## What I Learned

This lab gave me hands-on experience with identity security and endpoint detection and response.

I learned how to create users, assign permissions based on least privilege, deploy and monitor a Windows endpoint, verify Microsoft Defender for Endpoint onboarding, generate controlled suspicious activity, investigate a Defender alert, analyze process activity, and use Live Response during an endpoint investigation.

The SOC investigation workflow demonstrated in this lab was:

**Identify the alert → review the affected device → analyze process activity → determine what triggered the detection → investigate the endpoint using EDR tools.**

---

## Disclaimer

This project was completed in a controlled educational lab environment. All attack simulation and security testing was performed on systems that I created and was authorized to use.
