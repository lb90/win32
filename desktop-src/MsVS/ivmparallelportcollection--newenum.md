---
title: IVMParallelPortCollection \_NewEnum property
description: The \_NewEnum property contains an IEnumVariant enumerator for the collection.
ms.assetid: 3330fdd1-ca6f-4e16-a7a7-976130e440e4
keywords:
- _NewEnum property Virtual Server
- _NewEnum property Virtual Server , IVMParallelPortCollection interface
- IVMParallelPortCollection interface Virtual Server , _NewEnum property
topic_type:
- apiref
api_name:
- IVMParallelPortCollection._NewEnum
- IVMParallelPortCollection.get__NewEnum
api_location:
- VsComInterfaces.h
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IVMParallelPortCollection::\_NewEnum property

The **\_NewEnum** property contains an **IEnumVariant** enumerator for the collection.

This property is read-only.

## Syntax


```C++
HRESULT get__NewEnum(
  [out] IUnknown **enumerator
);
```



## Property value

The **IEnumVariant** enumerator for this collection.

## Error codes



| Name                                                                                          | Meaning                                  |
|-----------------------------------------------------------------------------------------------|------------------------------------------|
| <dl> <dt>S\_OK</dt> </dl>              | The operation was successful.<br/> |
| <dl> <dt>E\_POINTER</dt> </dl>         | The parameter is **NULL**.<br/>    |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl> | An unexpected error occurred.<br/> |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server 2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMParallelPortCollection**](ivmparallelportcollection.md)
</dt> </dl>

 

 




