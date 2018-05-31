---
Description: The IPrintCoreHelperPSGetOptionAttribute method retrieves the option attribute list or the value of a specific option attribute.
ms.assetid: 66e794e6-ded0-41b1-b52b-d886bb58a4ff
title: IPrintCoreHelperPSGetOptionAttribute method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IPrintCoreHelperPS::GetOptionAttribute method

The **IPrintCoreHelperPS::GetOptionAttribute** method retrieves the option attribute list or the value of a specific option attribute.

## Syntax


```C++
HRESULT GetOptionAttribute(
  [in]  PCSTR  pszFeatureKeyword,
  [in]  PCSTR  pszOptionKeyword,
  [in]  PCSTR  pszAttribute,
  [out] PDWORD pdwDataType,
  [out] PBYTE  *pbData,
  [out] PDWORD pcbSize
);
```



## Parameters

<dl> <dt>

*pszFeatureKeyword* \[in\]
</dt> <dd>

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the feature keyword to query for.

</dd> <dt>

*pszOptionKeyword* \[in\]
</dt> <dd>

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the option keyword to query for. This value can be obtained from a prior call to [**IPrintCoreHelperPS::EnumOptions**](iprintcorehelperps-enumoptions.md).

</dd> <dt>

*pszAttribute* \[in\]
</dt> <dd>

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the attribute requested. If this parameter is **NULL**, the caller is requesting a list of all supported attribute names for the option instead of specifying a specific attribute name for the option.

</dd> <dt>

*pdwDataType* \[out\]
</dt> <dd>

A pointer to a variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the [**EATTRIBUTE\_DATATYPE**](eattribute-datatype.md) enumeration type, which is defined in printoem.h.

</dd> <dt>

*pbData* \[out\]
</dt> <dd>

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.

</dd> <dt>

*pcbSize* \[out\]
</dt> <dd>

A pointer to a variable that receives the size, in bytes, of the buffer that is pointed to by the *pbData* parameter.

</dd> </dl>

## Return value

**IPrintCoreHelperPS::GetOptionAttribute** should return one of the following values.



| Return code                                                                                   | Description                                                                                                                                                                           |
|-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>          | The method succeeded.<br/>                                                                                                                                                      |
| <dl> <dt>**E\_FAIL**</dt> </dl>        | The method failed.<br/>                                                                                                                                                         |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>  | The method attempted to query for a nonexistent attribute.<br/> This value might also mean that the feature keyword name or option keyword name were not recognized.<br/> |
| <dl> <dt>**E\_OUTOFMEMORY**</dt> </dl> | The value in *pcbSize* was smaller than the number of bytes to be written to the output buffer that is pointed to by *pbData*.<br/>                                             |



 

## Remarks

If **IPrintCoreHelperPS::GetOptionAttribute** is called with its *pszAttribute* and *pbData* parameters set to **NULL**, the method returns with \**pcbSize* set to the number of bytes that are needed for the list of all of the supported attribute names for the option. If this method is called a second time, with *pszAttribute* set to **NULL** and *pbData* pointing to a buffer of the size that was specified in \**pcbSize* in the previous call, the method returns with \**pdwDataType* set to kADT\_ASCII (an enumerator of the [**EATTRIBUTE\_DATATYPE**](eattribute-datatype.md) enumeration type) and *pbData* pointing to a NULL-delimited list of all of the supported attribute names for the option. This list is terminated with two null characters.

For more information about **IPrintCoreHelperPS::GetOptionAttribute**, see [Using GetOptionAttribute](print.using_getoptionattribute).

## Requirements



|                            |                                                                                                            |
|----------------------------|------------------------------------------------------------------------------------------------------------|
| Target platform<br/> | <dl> <dt>Desktop</dt> </dl>                         |
| Header<br/>          | <dl> <dt>Prcomoem.h (include Prcomoem.h)</dt> </dl> |



## See also

<dl> <dt>

[**IPrintCoreHelperPS**](iprintcorehelperps-interface.md)
</dt> <dt>

[**IPrintCoreHelperPS::GetFeatureAttribute**](iprintcorehelperps-getfeatureattribute.md)
</dt> <dt>

[**IPrintCoreHelperPS::GetGlobalAttribute**](iprintcorehelperps-getglobalattribute.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bprint\print%5D:%20IPrintCoreHelperPS::GetOptionAttribute%20method%20%20RELEASE:%20%285/12/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/en-us/default.aspx. "Send comments about this topic to Microsoft")




