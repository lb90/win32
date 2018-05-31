---
Description: Proxy function for the GetResolution method.
ms.assetid: 5e261c2b-534a-4875-a84f-7251d54f15c6
title: IWICBitmapSource\_GetResolution\_Proxy function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IWICBitmapSource\_GetResolution\_Proxy function

Proxy function for the [**GetResolution**](/windows/win32/Wincodec/nf-wincodec-iwicbitmapsource-getresolution?branch=master) method.

## Syntax


```C++
HRESULT IWICBitmapSource_GetResolution_Proxy(
  _In_  IWICBitmapSource *THIS_PTR,
  _Out_ double           *pDpiX,
  _Out_ double           *pDpiY
);
```



## Parameters

<dl> <dt>

*THIS\_PTR* \[in\]
</dt> <dd>

Type: **[**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master)\***

Pointer to this [**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master) object.

</dd> <dt>

*pDpiX* \[out\]
</dt> <dd>

Type: **double\***

A pointer that receives the x-axis dpi resolution.

</dd> <dt>

*pDpiY* \[out\]
</dt> <dd>

Type: **double\***

A pointer that receives the y-axis dpi resolution.

</dd> </dl>

## Return value

Type: **HRESULT**

If this function succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

## Requirements



|                                     |                                                                                                                                                                  |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2, Windows Vista \[desktop apps only\]<br/>                                                                                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                                                                             |
| DLL<br/>                      | <dl> <dt>Windowscodecs.dll; </dt> <dt>Wincodec.lib</dt> </dl> |



 

 



