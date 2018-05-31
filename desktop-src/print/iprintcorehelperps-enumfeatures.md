---
Description: The IPrintCoreHelperPSEnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
ms.assetid: c67c15a4-3dbf-4317-b6d5-e52f426e7619
title: IPrintCoreHelperPSEnumFeatures method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IPrintCoreHelperPS::EnumFeatures method

The **IPrintCoreHelperPS::EnumFeatures** method gets a list of all available features, including synthesized and core driver-implement features.

## Syntax


```C++
STDMETHOD EnumFeatures(
  [out] PCSTR *pFeatureList,
  [out] DWORD *pdwNumFeatures
);
```



## Parameters

<dl> <dt>

*pFeatureList* \[out\]
</dt> <dd>

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a **NULL** string.

</dd> <dt>

*pdwNumFeatures* \[out\]
</dt> <dd>

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the *pFeatureList* parameter.

</dd> </dl>

## Return value

**IPrintCoreHelperPS::EnumFeatures** should return S\_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## Remarks

## Requirements



|                            |                                                                                                            |
|----------------------------|------------------------------------------------------------------------------------------------------------|
| Target platform<br/> | <dl> <dt>Desktop</dt> </dl>                         |
| Header<br/>          | <dl> <dt>Prcomoem.h (include Prcomoem.h)</dt> </dl> |



## See also

<dl> <dt>

[**IPrintCoreHelperPS**](iprintcorehelperps-interface.md)
</dt> <dt>

[**IPrintCoreHelperPS::EnumOptions**](iprintcorehelperps-enumoptions.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bprint\print%5D:%20IPrintCoreHelperPS::EnumFeatures%20method%20%20RELEASE:%20%285/12/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/en-us/default.aspx. "Send comments about this topic to Microsoft")




