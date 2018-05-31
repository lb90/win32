---
title: RestoreProperties method of the CIM\_ProtocolController class
description: Requests that the Device re-establish its configuration, setup and/or state information from a backing store.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 67fa1ca6-d6dc-4cbb-a87d-3ff8c64af489
ms.prod: windows-server-dev
ms.technology:
- iscsi-target
- windows-management-instrumentation
ms.tgt_platform: multiple
keywords:
- RestoreProperties method iSCSI Software Target API
- RestoreProperties method iSCSI Software Target API , CIM_ProtocolController class
- CIM_ProtocolController class iSCSI Software Target API , RestoreProperties method
topic_type:
- apiref
api_name:
- CIM_ProtocolController.RestoreProperties
api_location:
- SMiSCSITargetProv.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# RestoreProperties method of the CIM\_ProtocolController class

Requests that the Device re-establish its configuration, setup and/or state information from a backing store. The intent is to capture this information at an earlier time (via the SaveProperties method), and use it to return a Device to this earlier "condition". This method may not be supported by all Devices. The method should return 0 if successful, 1 if the request is not supported, and some other value if any other error occurred. In a subclass, the set of possible return codes could be specified, using a ValueMap qualifier on the method. The strings to which the ValueMap contents are 'translated' may also be specified in the subclass as a Values array qualifier.

## Syntax


```mof
uint32 RestoreProperties();
```



## Parameters

This method has no parameters.

## Requirements



|                                     |                                                                                                  |
|-------------------------------------|--------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                        |
| Minimum supported server<br/> | Windows Server 2012 R2<br/>                                                                |
| Namespace<br/>                | Root\\CIMv2\\Storage\\iScsiTarget<br/>                                                     |
| MOF<br/>                      | <dl> <dt>SmIscsiTarget.mof</dt> </dl>     |
| DLL<br/>                      | <dl> <dt>SMiSCSITargetProv.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_ProtocolController**](cim-protocolcontroller.md)
</dt> </dl>

 

 




