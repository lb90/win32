---
Description: The Duration method retrieves the duration of the stream.
ms.assetid: 82fbd7f5-36dc-4e81-9ce5-9ee28adf73ef
title: CPullPin.Duration method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CPullPin.Duration method

The `Duration` method retrieves the duration of the stream.

## Syntax


```C++
HRESULT Duration(
   REFERENCE_TIME *ptDuration
);
```



## Parameters

<dl> <dt>

*ptDuration* 
</dt> <dd>

Pointer to a variable that receives the duration, in bytes multiplied by 10,000,000.

</dd> </dl>

## Return value

Returns S\_OK.

## Remarks

The duration is indeterminate until the [**CPullPin::Connect**](cpullpin-connect.md) method is called.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Pullpin.h</dt> </dl>                                                                                                       |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CPullPin Class**](cpullpin.md)
</dt> </dl>

 

 



