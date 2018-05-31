---
Description: Is the Windows module that performs interactive logon for a logon session. Winlogon behavior can be customized by implementing and registering a Credential Provider.
ms.assetid: 6721367b-e200-4297-897b-4772226203b0
title: Winlogon and Credential Providers
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Winlogon and Credential Providers

[*Winlogon*](security.w_gly#-security-winlogon-gly) is the Windows module that performs interactive logon for a [*logon session*](security.l_gly#-security-logon-session-gly). Winlogon behavior can be customized by implementing and registering a Credential Provider.

For information about implementing a Credential Provider, see the following topics.



| Topic                                                                                                           | Description                                                                                            |
|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| [Credential Provider driven Windows Logon Experience](http://go.microsoft.com/fwlink/?LinkId=717287)<br/> | Overview of Winlogon and Credential Provider architecture and a sample Credential Provider.<br/> |
| [Shell Interfaces](_shell_interfaces)<br/>                                                                | Credential Provider interface reference.<br/>                                                    |
| [Credential Providers in Windows 10](credential-providers-in-windows.md)<br/>                            | Third-party credential providers and system credential providers in Windows 10.<br/>             |



 

For a sample Credential Provider implementation, see the sample located in the Windows SDK installation directory under \\Samples\\Security\\CredentialProvider.

**Windows Server 2003 and Windows XP:** Credential Providers are not supported. For information about customizing Winlogon, see [Winlogon and GINA](winlogon-and-gina.md).

 

 



