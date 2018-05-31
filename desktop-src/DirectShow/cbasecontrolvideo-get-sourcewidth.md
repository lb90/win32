---
Description: The get\_SourceWidth method retrieves the width of the current source rectangle.
ms.assetid: e8e27f8f-57e5-489c-aae7-86493677b380
title: CBaseControlVideo.get\_SourceWidth method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseControlVideo.get\_SourceWidth method

The `get_SourceWidth` method retrieves the width of the current source rectangle.

## Syntax


```C++
HRESULT get_SourceWidth(
   long *pSourceWidth
);
```



## Parameters

<dl> <dt>

*pSourceWidth* 
</dt> <dd>

Pointer to the width of the current source rectangle.

</dd> </dl>

## Return value

Returns an **HRESULT** value that depends on the implementation; can be one of the following values, or other values not listed.



| Return code                                                                                           | Description                                                                      |
|-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| <dl> <dt>**E\_FAIL**</dt> </dl>                | Failure.<br/>                                                              |
| <dl> <dt>**E\_POINTER**</dt> </dl>             | **NULL** pointer argument.<br/>                                            |
| <dl> <dt>**VFW\_E\_NOT\_CONNECTED**</dt> </dl> | The operation cannot be performed because the pins are not connected.<br/> |
| <dl> <dt>**NOERROR**</dt> </dl>                | Success.<br/>                                                              |



 

## Remarks

This member function implements the [**IBasicVideo::get\_SourceWidth**](/windows/win32/Control/nf-control-ibasicvideo-get_sourcewidth?branch=master) method.

An application can change the source and destination rectangles for the video through the [**IBasicVideo**](/windows/win32/Control/nn-control-ibasicvideo?branch=master) interface. The source rectangle affects which section of the native video source will appear on the display; the destination rectangle affects where the video will appear when played. The destination rectangle is relative to the client area of the window in which it is playing. The upper-left corner of the window is coordinate (0,0).

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Ctlutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseControlVideo Class**](cbasecontrolvideo.md)
</dt> </dl>

 

 



