---
Description: The EndOfStream method notifies the pin that no additional data is expected. This method implements the IPinEndOfStream method.
ms.assetid: db9896eb-3db2-4d58-a787-4d80ce8f0d0e
title: CTransformInputPin.EndOfStream method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CTransformInputPin.EndOfStream method

The `EndOfStream` method notifies the pin that no additional data is expected. This method implements the [**IPin::EndOfStream**](/windows/win32/Strmif/nf-strmif-ipin-endofstream?branch=master) method.

## Syntax


```C++
HRESULT EndOfStream();
```



## Parameters

This method has no parameters.

## Return value

Returns an **HRESULT** value. Possible values include those shown in the following table.



| Return code                                                                                           | Description                                 |
|-------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                  | Success.<br/>                         |
| <dl> <dt>**S\_FALSE**</dt> </dl>               | Pin is currently flushing.<br/>       |
| <dl> <dt>**VFW\_E\_NOT\_CONNECTED**</dt> </dl> | The output pin is not connected.<br/> |
| <dl> <dt>**VFW\_E\_RUNTIME\_ERROR**</dt> </dl> | A run-time error occurred.<br/>       |
| <dl> <dt>**VFW\_E\_WRONG\_STATE**</dt> </dl>   | The pin is stopped.<br/>              |



 

## Remarks

This method calls the filter's [**CTransformFilter::EndOfStream**](ctransformfilter-endofstream.md) method to deliver the end-of-stream notification downstream.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Transfrm.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



 

 



