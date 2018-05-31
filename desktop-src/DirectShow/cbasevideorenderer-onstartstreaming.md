---
Description: The OnStartStreaming method resets all times that control streaming.
ms.assetid: a2bb07f2-6880-4030-96c5-d146982dfe66
title: CBaseVideoRenderer.OnStartStreaming method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseVideoRenderer.OnStartStreaming method

The `OnStartStreaming` method resets all times that control streaming.

## Syntax


```C++
HRESULT OnStartStreaming();
```



## Parameters

This method has no parameters.

## Return value

Returns an **HRESULT** value.

## Remarks

This member function overrides [**CBaseRenderer::OnStartStreaming**](cbaserenderer-onstartstreaming.md).

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Renbase.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseVideoRenderer Class**](cbasevideorenderer.md)
</dt> </dl>

 

 



