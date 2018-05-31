---
title: Reading the defaultSecurityDescriptor for an Object Class
description: Using ADSI, you can obtain the defaultSecurityDescriptor attribute for an object class with the IADs interface.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 12d1e77a-bd70-4c64-9b4f-ac5caaf5fe40
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
keywords:
- Active Directory examples Active Directory , reading the defaultSecurityDescriptor for an Object Class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Reading the defaultSecurityDescriptor for an Object Class

Using ADSI, you can obtain the **defaultSecurityDescriptor** attribute for an object class with the [**IADs**](https://msdn.microsoft.com/library/aa705950) interface. To obtain the **defaultSecurityDescriptor** attribute for an object class, perform the following steps.

1.  Get an [**IADs**](https://msdn.microsoft.com/library/aa705950) interface pointer to the **classSchema** object for the object class.
2.  Use the [**IADs.Get**](https://msdn.microsoft.com/library/aa746347) method to get the default security descriptor of the object. The name of the property that contains the security descriptor is "defaultSecurityDescriptor". The property will be returned as a [**VARIANT**](e305240e-9e11-4006-98cc-26f4932d2118) containing a BSTR with the default security descriptor in SDDL string format.
3.  Use the [**ConvertStringSecurityDescriptorToSecurityDescriptor**](https://msdn.microsoft.com/library/windows/desktop/aa376401) function to convert the SDDL string form to a security descriptor.
4.  Use the [**GetSecurityDescriptorDacl**](https://msdn.microsoft.com/library/windows/desktop/aa446648), [**GetSecurityDescriptorSacl**](https://msdn.microsoft.com/library/windows/desktop/aa446653), [**GetSecurityDescriptorOwner**](https://msdn.microsoft.com/library/windows/desktop/aa446651), and [**GetSecurityDescriptorControl**](https://msdn.microsoft.com/library/windows/desktop/aa446647) Security APIs to read the parts of the security descriptor.

For a code example that demonstrates how to do this, see [Example Code for Reading defaultSecurityDescriptor](example-code-for-reading-defaultsecuritydescriptor.md).

 

 



