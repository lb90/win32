---
Description: The GetProperties method retrieves the properties of the sample. This method implements the IMediaSample2GetProperties method.
ms.assetid: c2a6d611-9c17-41fb-bb6d-f5b17f1c9966
title: CMediaSample.GetProperties method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CMediaSample.GetProperties method

The `GetProperties` method retrieves the properties of the sample. This method implements the [**IMediaSample2::GetProperties**](/windows/win32/Strmif/nf-strmif-imediasample2-getproperties?branch=master) method.

## Syntax


```C++
HRESULT GetProperties(
   DWORD cbProperties,
   BYTE  *pbProperties
);
```



## Parameters

<dl> <dt>

*cbProperties* 
</dt> <dd>

Length of property data to retrieve, in bytes.

</dd> <dt>

*pbProperties* 
</dt> <dd>

Pointer to a buffer of size *cbProperties*.

</dd> </dl>

## Return value

Returns one of the **HRESULT** values shown in the following table.



| Return code                                                                               | Description                           |
|-------------------------------------------------------------------------------------------|---------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>      | Success.<br/>                   |
| <dl> <dt>**E\_POINTER**</dt> </dl> | **NULL** pointer argument.<br/> |



 

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CMediaSample Class**](cmediasample.md)
</dt> </dl>

 

 



