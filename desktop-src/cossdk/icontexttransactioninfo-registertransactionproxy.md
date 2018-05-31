---
Description: Associates an ITransactionProxy implementation with the current context.
ms.assetid: 64009632-b536-41fb-95ac-b23e2cbf18da
title: IContextTransactionInfoRegisterTransactionProxy method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IContextTransactionInfo::RegisterTransactionProxy method

Associates an [**ITransactionProxy**](/windows/win32/ComSvcs/nn-comsvcs-itransactionproxy?branch=master) implementation with the current context.

## Syntax


```C++
HRESULT RegisterTransactionProxy(
  [in]  ITransactionProxy *pProxy,
  [out] GUID              *pGuid
);
```



## Parameters

<dl> <dt>

*pProxy* \[in\]
</dt> <dd>

An [**ITransactionProxy**](/windows/win32/ComSvcs/nn-comsvcs-itransactionproxy?branch=master) implementation to associate with the current context.

</dd> <dt>

*pGuid* \[out\]
</dt> <dd>

A GUID that identifies the transaction proxy. COM+ uses this GUID when calling [**ITransactionProxy::Commit**](/windows/win32/ComSvcs/nf-comsvcs-itransactionproxy-commit?branch=master) on the transaction proxy.

</dd> </dl>

## Return value

This method can return the standard return values E\_INVALIDARG, E\_OUTOFMEMORY, and E\_UNEXPECTED, as well as the following values.



| Return code                                                                                                     | Description                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                            | The method completed successfully.<br/>                                                                           |
| <dl> <dt>**CONTEXT\_E\_ALREADYINTRANSACTION**</dt> </dl> | The current context already has an associated [**ITransactionProxy**](/windows/win32/ComSvcs/nn-comsvcs-itransactionproxy?branch=master) implementation.<br/> |
| <dl> <dt>**E\_NOTIMPL**</dt> </dl>                       | The current context is hosting a Bring Your Own Transaction (BYOT) transaction or a non-root transaction.<br/>    |



 

## Remarks

The **RegisterTransactionProxy** method can only be called if the current context is a root transaction context. It cannot be called if the context is hosting a BYOT transaction or a non-root transaction.

## Requirements



|                                     |                                                               |
|-------------------------------------|---------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2 \[desktop apps only\]<br/>          |
| Minimum supported server<br/> | Windows Server 2003 with SP1 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[**IContextTransactionInfo**](icontexttransactioninfo.md)
</dt> </dl>

 

 



