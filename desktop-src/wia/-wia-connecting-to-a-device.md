---
ms.assetid: 16ff280d-818b-4a4e-b5a6-16e81f5b35c6
title: Connecting to a Device
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Connecting to a Device

> [!Note]  
> This scripting system has been replaced with Windows Image Acquisition (WIA) Automation Layer. See [Windows Image Acquisition Automation Layer](http://msdn.microsoft.com/en-us/library/windows/desktop/ms630827.aspx).

 

The first step in any application or script that uses the Windows Image Acquisition (WIA) scripting model is creating the [**Wia**](-wia-wia.md) object. This object provides methods for to obtain a collection of [**DeviceInfo**](-wia-deviceinfo.md) objects and connect these objects to devices. It also provides the ability to listen for WIA hardware events.

The following line of Microsoft Visual Basic Scripting Edition (VBScript) code creates the [**Wia**](-wia-wia.md) object:


```
objWia = CreateObject("Wia.Script")
```



After creating the [**Wia**](-wia-wia.md) object, use its [**Create**](-wia-iwia-create.md) method to connect to a WIA hardware device.

You can also use the [**Wia**](-wia-wia.md) object's [**Devices**](-wia-iwia-devices.md) property to obtain a collection of [**DeviceInfo**](-wia-deviceinfo.md) objects. Enumerate this collection and use the [**Create**](-wia-iwiadeviceinfo-create.md) method to connect to a device.

 

 


