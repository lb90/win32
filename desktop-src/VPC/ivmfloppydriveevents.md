---
title: IVMFloppyDriveEvents interface
description: Defines the outgoing event interface for the IVMFloppyDrive interface. The client implements these methods to receive events sent from IVMFloppyDrive.
ms.assetid: fbb66554-f042-4891-94be-1a12b8c179c2
keywords:
- IVMFloppyDriveEvents interface Virtual PC
- IVMFloppyDriveEvents interface Virtual PC , described
topic_type:
- apiref
api_name:
- IVMFloppyDriveEvents
api_location:
- VPCCOMInterfaces.h
api_type:
- COM
ms.date: 05/31/2018
ms.topic: interface
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IVMFloppyDriveEvents interface

\[Windows Virtual PC is no longer available for use as of Windows 8. Instead, use the [Hyper-V WMI provider (V2)](https://msdn.microsoft.com/library/windows/desktop/hh850319).\]

Defines the outgoing event interface for the [**IVMFloppyDrive**](ivmfloppydrive.md) interface. The client implements these methods to receive events sent from **IVMFloppyDrive**.

## Members

The **IVMFloppyDriveEvents** interface inherits from the [**IDispatch**](ebbff4bc-36b2-4861-9efa-ffa45e013eb5) interface. **IVMFloppyDriveEvents** also has these types of members:

-   [Methods](#methods)

### Methods

The **IVMFloppyDriveEvents** interface has these methods.



| Method                                                      | Description                                                                   |
|:------------------------------------------------------------|:------------------------------------------------------------------------------|
| [**OnMediaEject**](ivmfloppydriveevents-onmediaeject.md)   | Receives notification that media has been ejected from the drive.<br/>  |
| [**OnMediaInsert**](ivmfloppydriveevents-onmediainsert.md) | Receives notification that media has been inserted into the drive.<br/> |



 

## Requirements



|                                     |                                                                                               |
|-------------------------------------|-----------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps only\]<br/>                                                    |
| Minimum supported server<br/> | None supported<br/>                                                                     |
| End of client support<br/>    | Windows 7<br/>                                                                          |
| Product<br/>                  | Windows Virtual PC<br/>                                                                 |
| Header<br/>                   | <dl> <dt>VPCCOMInterfaces.h</dt> </dl> |
| IID<br/>                      | DIID\_IVMFloppyDriveEvents is defined as a9ed3401-4e09-4177-86ec-a13bf9fa7d4e<br/>      |



 

 




