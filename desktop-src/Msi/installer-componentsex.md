---
Description: Returns a RecordList object that lists installed components.
ms.assetid: a91656de-2ebc-45b5-86f8-b13f35c6a762
title: Installer.ComponentsEx property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Installer.ComponentsEx property

This property returns a [**RecordList**](recordlist-object.md) object that lists installed components. This property calls [**MsiEnumComponentsEx**](/windows/win32/Msi/nf-msi-msienumcomponentsexa?branch=master).

**[Windows Installer 4.5 or earlier](not-supported-in-windows-installer-4-5.md):** Not supported. This property is available beginning with Windows Installer 5.0.

This property is read-only.

## Syntax


```JScript
propVal = Installer.ComponentsEx
```



## Property value

## Requirements



|                    |                                                                                                         |
|--------------------|---------------------------------------------------------------------------------------------------------|
| Version<br/> | Windows Installer 5.0 on Windows Server 2012, Windows 8, Windows Server 2008 R2 or Windows 7<br/> |
| DLL<br/>     | <dl> <dt>Msi.dll</dt> </dl>                      |
| IID<br/>     | IID\_IInstaller is defined as 000C1090-0000-0000-C000-000000000046<br/>                           |



## See also

<dl> <dt>

[**MsiEnumComponentsEx**](/windows/win32/Msi/nf-msi-msienumcomponentsexa?branch=master)
</dt> </dl>

 

 



