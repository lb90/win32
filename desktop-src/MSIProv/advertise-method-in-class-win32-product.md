---
title: Advertise method of the Win32\_Product class
description: Advertises an associated Win32\_Product instance using the installation package provided through the PackageLocation parameter and any supplied command line options.
ms.assetid: f9afe011-cbac-4a49-a6c9-169ff86aaa36
keywords:
- Advertise method
- Advertise method, Win32_Product class
- Win32_Product class, Advertise method
topic_type:
- apiref
api_name:
- Win32_Product.Advertise
api_location:
- Msiprov.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Advertise method of the Win32\_Product class

The **Advertise** [WMI class](https://msdn.microsoft.com/library/aa393244) method advertises an associated [**Win32\_Product**](win32-product.md) instance using the installation package provided through the *PackageLocation* parameter and any supplied command line options.

> [!Note]  
> For more information about support or requirements for installation on a specific operating system, see [Operating System Availability of WMI Components](https://msdn.microsoft.com/library/aa392726#windows-installer-provider).

 

This topic uses Managed Object Format (MOF) syntax. For more information about using this method, see [Calling a Method](https://msdn.microsoft.com/library/aa384832).

## Syntax


```mof
uint32 Advertise(
  [in] string PackageLocation,
  [in] string Options
);
```



## Parameters

<dl> <dt>

*PackageLocation* \[in\]
</dt> <dd>

The path to the package to be advertised.

</dd> <dt>

*Options* \[in\]
</dt> <dd>

Command line options for the advertisement. Format as *property***=***setting*.

</dd> <dt>

*AllUsers* 
</dt> <dd>

Indicates whether the operation should be applied to all users on the computer. If **FALSE**, the operation is applied to only the current user. This parameter is no longer used.

</dd> </dl>

## Return value



| Return code                                                                               | Description                       |
|-------------------------------------------------------------------------------------------|-----------------------------------|
| <dl> <dt>**0**</dt> </dl>          | Successful completion<br/>  |
| <dl> <dt>**2147549445**</dt> </dl> | RPC Server Fault Error<br/> |



 

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP<br/>                                                                  |
| Minimum supported server<br/> | Windows Server 2003<br/>                                                         |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                 |
| MOF<br/>                      | <dl> <dt>Msi.mof</dt> </dl>     |
| DLL<br/>                      | <dl> <dt>Msiprov.dll</dt> </dl> |



## See also

<dl> <dt>

[Installed Applications Classes](https://msdn.microsoft.com/library/aa390887)
</dt> <dt>

[**Win32\_Product**](win32-product.md)
</dt> <dt>

[WMI Tasks: Computer Software](https://msdn.microsoft.com/library/aa394588)
</dt> </dl>

 

 




