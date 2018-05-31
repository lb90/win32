---
Description: The CheckInputType method checks whether a specified media type is acceptable for input.
ms.assetid: 11f156f7-add2-45be-a0d3-05d21f596b89
title: CTransformFilter.CheckInputType method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CTransformFilter.CheckInputType method

The `CheckInputType` method checks whether a specified media type is acceptable for input.

## Syntax


```C++
virtual HRESULT CheckInputType(
   const CMediaType *mtIn
) = 0;
```



## Parameters

<dl> <dt>

*mtIn* 
</dt> <dd>

Pointer to a [**CMediaType**](cmediatype.md) object that specifies the media type.

</dd> </dl>

## Return value

Returns an **HRESULT** value. Possible values include those shown in the following table.



| Return code                                                                                                | Description                              |
|------------------------------------------------------------------------------------------------------------|------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                       | Media type is acceptable.<br/>     |
| <dl> <dt>**VFW\_E\_TYPE\_NOT\_ACCEPTED**</dt> </dl> | Media type is not acceptable.<br/> |



 

## Remarks

The derived class must implement this method. Return S\_OK if the proposed input format is acceptable, or an error code otherwise.

This method does not need to verify that the input format is compatible with the output format (if any). The input pin verifies that by calling the [**CheckTransform**](ctransformfilter-checktransform.md) method.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Transfrm.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CTransformFilter Class**](ctransformfilter.md)
</dt> </dl>

 

 



