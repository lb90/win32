---
Description: The StopStreaming method halts streaming when the filter switches out of the running state.
ms.assetid: 465dde15-adec-46da-b8c8-56743e0cbd29
title: CBaseRenderer.StopStreaming method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseRenderer.StopStreaming method

The `StopStreaming` method halts streaming when the filter switches out of the running state.

## Syntax


```C++
virtual HRESULT StopStreaming();
```



## Parameters

This method has no parameters.

## Return value

Returns S\_OK.

## Remarks

This method calls the [**CBaseRenderer::OnStopStreaming**](cbaserenderer-onstopstreaming.md) method. That method does nothing in the base class, but the derived class can override it.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Renbase.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseRenderer Class**](cbaserenderer.md)
</dt> </dl>

 

 



