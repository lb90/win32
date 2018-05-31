---
title: close command
description: The close command closes the device or file and any associated resources. MCI unloads a device when all instances of the device or all files are closed. All MCI devices recognize this command.
ms.assetid: f756c11d-54a7-4238-8a99-4263a6c36109
keywords:
- close command Windows Multimedia
topic_type:
- apiref
api_name:
- close
api_location:
- corecrt_io.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# close command

The close command closes the device or file and any associated resources. MCI unloads a device when all instances of the device or all files are closed. All MCI devices recognize this command.

To send this command, call the [**mciSendString**](/windows/win32/Mmsystem/?branch=master) function with the *lpszCommand* parameter set as follows.

``` syntax
_stprintf_s(
  lpszCommand, 
  TEXT("close %s %s"), 
  lpszDeviceID, 
  lpszFlags
); 
```

## Parameters

<dl> <dt>

<span id="lpszDeviceID"></span><span id="lpszdeviceid"></span><span id="LPSZDEVICEID"></span>*lpszDeviceID*
</dt> <dd>

Identifier of an MCI device. This identifier or alias is assigned when the device is opened.

</dd> <dt>

<span id="lpszFlags"></span><span id="lpszflags"></span><span id="LPSZFLAGS"></span>*lpszFlags*
</dt> <dd>

Can be "wait", "notify", or both. For more information about these flags, see [The Wait, Notify, and Test Flags](the-wait-notify-and-test-flags.md).

</dd> </dl>

## Return Value

Returns zero if successful or an error otherwise.

## Remarks

To close all devices opened by your application, specify the "all" device identifier for the *lpszDeviceID* parameter.

Closing the **cdaudio** device stops audio playback.

**Windows 2000/XP:** If the **cdaudio** device is playing, closing the **cdaudio** device does not cause the audio to stop playing. Send the [stop](stop.md) command first.

## Examples

The following command closes the "mysound" device.

``` syntax
close mysound
```

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                               |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                     |
| Header<br/>                   | <dl> <dt>Corecrt\_io.h</dt> </dl> |



## See also

<dl> <dt>

[MCI](mci.md)
</dt> <dt>

[MCI Command Strings](mci-command-strings.md)
</dt> </dl>

 

 




