---
Description: Contains methods that let you access and modify the security settings for a namespace.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: a54fdd85-feb8-4727-9f26-fe4f213cab6b
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
title: '\_\_SystemSecurity class'
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# \_\_SystemSecurity class

The **\_\_SystemSecurity** system class contains methods that let you access and modify the security settings for a namespace. The **\_\_SystemSecurity** class is a singleton class in each namespace.

> [!Note]  
> For more information, see [Setting Namepace Security Descriptors](setting-namespace-security-descriptors.md).

 

The following syntax is simplified from Managed Object Format (MOF) code and includes all inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
class __SystemSecurity
{
};
```

## Members

The **\_\_SystemSecurity** class has these types of members:

-   [Methods](#methods)

### Methods

The **\_\_SystemSecurity** class has these methods.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Method</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">[<strong>Get9XUserList</strong>](--systemsecurity-get9xuserlist.md)</td>
<td style="text-align: left;">Gets a list of users who are allowed remote access.<br/>
<blockquote>
[!Note]<br />
This method does not work on supported versions of Windows. Use [<strong>GetSD</strong>](--systemsecurity-getsd.md) instead.
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;">[<strong>GetCallerAccessRights</strong>](--systemsecurity-getcalleraccessrights.md)</td>
<td style="text-align: left;">Returns a mask with each bit that corresponds to an access right.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;">[<strong>GetSD</strong>](--systemsecurity-getsd.md)</td>
<td style="text-align: left;">Gets the [<strong>SECURITY_DESCRIPTOR</strong>](https://msdn.microsoft.com/library/windows/desktop/aa379561) for the namespace to which the user is connected.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;">[<strong>GetSecurityDescriptor</strong>](getsecuritydescriptor-method-in-class---systemsecurity-.md)</td>
<td style="text-align: left;">Gets the security descriptor that controls access to the WMI namespace associated with the instance of <strong>__SystemSecurity</strong>. The security descriptor is returned as an instance of[<strong>__SecurityDescriptor</strong>](--securitydescriptor.md).<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;">[<strong>Set9XUserList</strong>](--systemsecurity-set9xuserlist.md)</td>
<td style="text-align: left;">Sets a list of users who are allowed remote access.<br/>
<blockquote>
[!Note]<br />
This method does not work on supported versions of Windows. Use [<strong>SetSD</strong>](--systemsecurity-setsd.md) instead.
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;">[<strong>SetSD</strong>](--systemsecurity-setsd.md)</td>
<td style="text-align: left;">Sets the security descriptor for the namespace to which the user is connected.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;">[<strong>SetSecurityDescriptor</strong>](setsecuritydescriptor-method-in-class---systemsecurity.md)</td>
<td style="text-align: left;">Writes an updated version of the security descriptor that controls access to the printer. The security descriptor is represented by an instance of [<strong>__SecurityDescriptor</strong>](--securitydescriptor.md).<br/></td>
</tr>
</tbody>
</table>



 

## Remarks

You can require that client scripts and applications use an encrypted connection for authentication by adding the **RequiresEncryption** qualifier to the .mof file that creates the namespace. You can also modify an existing namespace by adding this attribute and compile the .mof file again. For more information about how to use **RequiresEncryption**, see [Requiring an Encrypted Connection to a Namespace](requiring-an-encrypted-connection-to-a-namespace.md).

## Requirements



|                                     |                                |
|-------------------------------------|--------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>       |
| Minimum supported server<br/> | Windows Server 2008<br/> |
| Namespace<br/>                | All WMI namespaces<br/>  |



## See also

<dl> <dt>

[WMI System Classes](wmi-system-classes.md)
</dt> <dt>

[WMI Security Constants](wmi-security-constants.md)
</dt> <dt>

[WMI Security Descriptor Objects](wmi-security-descriptor-objects.md)
</dt> <dt>

[Securing WMI Namespaces](securing-wmi-namespaces.md)
</dt> <dt>

[Establishing Inheritance of Namespace Security](establishing-inheritance-of-namespace-security.md)
</dt> <dt>

[Access Control Lists (ACLs)](https://msdn.microsoft.com/library/windows/desktop/aa374872)
</dt> <dt>

[**Security\_Descriptor**](https://msdn.microsoft.com/library/windows/desktop/aa379561)
</dt> </dl>

 

 



