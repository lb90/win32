---
title: CFSTR\_DSQUERYSCOPE
description: The CFSTR\_DSQUERYSCOPE clipboard format provides a global memory handle (HGLOBAL) that contains a string that specifies the query scope.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 3cf51543-eca4-466c-bf0c-1351fd90798b
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
topic_type:
- apiref
api_name:
- CFSTR_DSQUERYSCOPE
api_location:
- DSQuery.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# CFSTR\_DSQUERYSCOPE

<dl> <dt>

<span id="CFSTR_DSQUERYSCOPE"></span><span id="cfstr_dsqueryscope"></span>**CFSTR\_DSQUERYSCOPE**
</dt> <dd> <dl> <dt>

"DsQueryScope"
</dt> <dt>



The **CFSTR\_DSQUERYSCOPE** clipboard format is supported by the [**IDataObject**](_ole_idataobject) provided by the [**ICommonQuery::OpenQueryWindow**](/windows/win32/Cmnquery/?branch=master) method. The **CFSTR\_DSQUERYSCOPE** clipboard format provides a global memory handle (**HGLOBAL**) that contains a string that specifies the query scope.


</dt> </dl> </dd> </dl>

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                             |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                       |
| Header<br/>                   | <dl> <dt>DSQuery.h</dt> </dl> |



## See also

<dl> <dt>

[**IDataObject**](_ole_idataobject)
</dt> <dt>

[**ICommonQuery::OpenQueryWindow**](/windows/win32/Cmnquery/?branch=master)
</dt> </dl>

 

 




