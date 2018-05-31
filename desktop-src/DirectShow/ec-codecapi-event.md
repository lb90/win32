---
Description: The EC\_CODECAPI\_EVENT event is sent by an encoder to signal an encoding event. The client registers for encoder event by calling the ICodecAPIRegisterForEvent method.
ms.assetid: 88924ba9-707b-41a7-9bca-c630b4a9c4c8
title: EC\_CODECAPI\_EVENT
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# EC\_CODECAPI\_EVENT

The EC\_CODECAPI\_EVENT event is sent by an encoder to signal an encoding event. The client registers for encoder event by calling the [**ICodecAPI::RegisterForEvent**](/windows/win32/Strmif/nf-strmif-icodecapi-registerforevent?branch=master) method.

## Parameters

<dl> <dt>

<span id="lParam1"></span><span id="lparam1"></span><span id="LPARAM1"></span>*lParam1*
</dt> <dd>

User data. The value of this parameter is the pointer that the caller specified in the *userData* parameter of the [**RegisterForEvent**](/windows/win32/Strmif/nf-strmif-icodecapi-registerforevent?branch=master) method.

</dd> <dt>

<span id="lParam2"></span><span id="lparam2"></span><span id="LPARAM2"></span>*lParam2*
</dt> <dd>

Pointer to the event data. This data is allocated by the encoder and must be freed by the application, using the **CoTaskMemFree** function. The data block starts with a [**CodecAPIEventData**](/windows/win32/strmif/ns-strmif-codecapieventdata?branch=master) structure; cast the *lParam2* parameter to a pointer to this structure.

</dd> </dl>

## Default Action

No default action.

## Requirements



|                   |                                                                                    |
|-------------------|------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Dshow.h</dt> </dl> |



## See also

<dl> <dt>

[Event Notification Codes](event-notification-codes.md)
</dt> <dt>

[Event Notification in DirectShow](event-notification-in-directshow.md)
</dt> </dl>

 

 



