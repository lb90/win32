---
Description: External Device Interfaces for DV Camcorders
ms.assetid: 001321c5-70c7-4baa-ba5a-1e424ca0d647
title: External Device Interfaces for DV Camcorders
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# External Device Interfaces for DV Camcorders

The [WDM Video Capture](wdm-video-capture-filter.md) filter exposes three interfaces for controlling a camcorder.



|                                                |                                                 |
|------------------------------------------------|-------------------------------------------------|
| [**IAMExtDevice**](/windows/win32/Strmif/nn-strmif-iamextdevice?branch=master)           | The base interface for external device control. |
| [**IAMExtTransport**](/windows/win32/Strmif/nn-strmif-iamexttransport?branch=master)     | Controls the VCR functions.                     |
| [**IAMTimecodeReader**](/windows/win32/Strmif/nn-strmif-iamtimecodereader?branch=master) | Reads timecode from the device.                 |



 

> [!Note]  
> To use these interfaces with the MSDV camcorder driver, include the header file XPrtDefs.h in your project.

 

After you select a capture device and create an instance of the capture filter, query the filter for these interfaces. The following example declares a custom structure that holds the interface pointers, along with Boolean values that specify the availability of each interface:


```C++
struct _MyDevCap
{
    IAMExtDevice       *pDevice;
    IAMExtTransport    *pTransport;
    IAMTimecodeReader  *pTimecode;
    BOOL                bHasDevice;
    BOOL                bHasTransport;
    BOOL                bHasTimecode;
} MyDevCap;

HRESULT hr;
IBaseFilter *pDVCam;  // Pointer to the capture filter.

// Create an instance of the capture filter (not shown).

hr = pDVCam->QueryInterface(IID_IAMExtDevice, (void **)&amp;MyDevCap.pDevice);
MyDevCap.bHasDevice = (SUCCEEDED(hr));

hr = pDVCam->QueryInterface(IID_IAMExtTransport, (void **)&amp;MyDevCap.pTransport);
MyDevCap.bHasTransport = (SUCCEEDED(hr));

hr = pDVCam->QueryInterface(IID_IAMTimecodeReader, (void **)&amp;MyDevCap.pTimecode);
MyDevCap.bHasTimecode = (SUCCEEDED(hr));
```



## Related topics

<dl> <dt>

[Controlling a DV Camcorder](controlling-a-dv-camcorder.md)
</dt> </dl>

 

 


