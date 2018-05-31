---
title: WM\_DDE\_ACK message
description: The WM\_DDE\_ACK message notifies a Dynamic Data Exchange (DDE) application of the receipt and processing of the following messages WM\_DDE\_POKE, WM\_DDE\_EXECUTE, WM\_DDE\_DATA, WM\_DDE\_ADVISE, WM\_DDE\_UNADVISE, WM\_DDE\_INITIATE, or WM\_DDE\_REQUEST (in some cases). To post this message, call the PostMessage function with the following parameters.
ms.assetid: aca47dbf-e1f2-4725-8364-0aa7fcd98bd9
keywords:
- WM_DDE_ACK message Data Exchange
topic_type:
- apiref
api_name:
- WM_DDE_ACK
api_location:
- Dde.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# WM\_DDE\_ACK message

The **WM\_DDE\_ACK** message notifies a Dynamic Data Exchange (DDE) application of the receipt and processing of the following messages: [**WM\_DDE\_POKE**](wm-dde-poke.md), [**WM\_DDE\_EXECUTE**](wm-dde-execute.md), [**WM\_DDE\_DATA**](wm-dde-data.md), [**WM\_DDE\_ADVISE**](wm-dde-advise.md), [**WM\_DDE\_UNADVISE**](wm-dde-unadvise.md), [**WM\_DDE\_INITIATE**](wm-dde-initiate.md), or [**WM\_DDE\_REQUEST**](wm-dde-request.md) (in some cases).

To post this message, call the [**PostMessage**](https://msdn.microsoft.com/library/windows/desktop/ms644944) function with the following parameters.


```C++
#define WM_DDE_ACK     0x03E4
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

When responding to [**WM\_DDE\_INITIATE**](wm-dde-initiate.md), this parameter is a handle to the server window sending the message.

When responding to [**WM\_DDE\_EXECUTE**](wm-dde-execute.md), this parameter is a handle to the server window posting the message.

When replying to all other messages, this parameter is a handle to the client or server window posting the message.

</dd> <dt>

*lParam* 
</dt> <dd>

When responding to [**WM\_DDE\_INITIATE**](wm-dde-initiate.md), the low-order word contains an atom that identifies the replying application. The high-order word contains an atom that identifies the topic for which a conversation is being established.

When responding to [**WM\_DDE\_EXECUTE**](wm-dde-execute.md), the low-order word specifies a [**DDEACK**](/windows/win32/Dde/ns-dde-ddeack?branch=master) structure containing a series of flags that indicate the status of the response. The high-order word is a handle to a global memory object that contains the command string that was received in the **WM\_DDE\_EXECUTE** message.

When replying to all other messages, the low-order word specifies a [**DDEACK**](/windows/win32/Dde/ns-dde-ddeack?branch=master) structure containing a series of flags that indicate the status of the response. The high-order word contains a global atom that identifies the name of the data item for which the response is sent.

</dd> </dl>

## Remarks

### Posting

Except in response to the [**WM\_DDE\_INITIATE**](wm-dde-initiate.md) message, the application posts the **WM\_DDE\_ACK** message by calling the [**PostMessage**](https://msdn.microsoft.com/library/windows/desktop/ms644944) function, not by calling the [**SendMessage**](https://msdn.microsoft.com/library/windows/desktop/ms644950) function. When responding to **WM\_DDE\_INITIATE**, the application sends the **WM\_DDE\_ACK** message by calling **SendMessage**. In this case, neither the application-name atom nor the topic-name atom should be **NULL** (even if the **WM\_DDE\_INITIATE** message specified **NULL** atoms).

When acknowledging any message with an accompanying atom, the application posting **WM\_DDE\_ACK** can either reuse the atom that accompanied the original message, or it can delete it and create a new one.

When acknowledging [**WM\_DDE\_EXECUTE**](wm-dde-execute.md), the application that posts **WM\_DDE\_ACK** should reuse the global memory object identified in the original **WM\_DDE\_EXECUTE** message.

All posted **WM\_DDE\_ACK** messages must create or reuse the *lParam* parameter by calling the [**PackDDElParam**](/windows/win32/Dde/nf-dde-packddelparam?branch=master) function or the [**ReuseDDElParam**](/windows/win32/Dde/nf-dde-reuseddelparam?branch=master) function.

If an application has initiated the termination of a conversation by posting [**WM\_DDE\_TERMINATE**](wm-dde-terminate.md) and is awaiting confirmation, the waiting application should not acknowledge (positively or negatively) any subsequent messages sent by the other application. The waiting application should delete any atoms or shared memory objects received in these intervening messages. Memory objects should not be freed if the **fRelease** flag is set to **FALSE** in [**WM\_DDE\_POKE**](wm-dde-poke.md) and [**WM\_DDE\_DATA**](wm-dde-data.md) messages.

### Receiving

The application that receives a **WM\_DDE\_ACK** message should delete all atoms accompanying the message. If the application receives a **WM\_DDE\_ACK** in response to a message with an accompanying global memory object, and the object was sent with the **fRelease** flags set to **FALSE**, the application is responsible for deleting the object.

If the application receives a negative **WM\_DDE\_ACK** message posted in reply to a [**WM\_DDE\_ADVISE**](wm-dde-advise.md) message, the application should delete the global memory object posted with the original **WM\_DDE\_ADVISE** message. If the application receives a negative **WM\_DDE\_ACK** message posted in reply to a [**WM\_DDE\_DATA**](wm-dde-data.md), [**WM\_DDE\_POKE**](wm-dde-poke.md), or [**WM\_DDE\_EXECUTE**](wm-dde-execute.md) message, the application should delete the global memory object posted with the original **WM\_DDE\_DATA**, **WM\_DDE\_POKE**, or **WM\_DDE\_EXECUTE** message.

The application that receives a posted **WM\_DDE\_ACK** message must free the *lParam* parameter by using the [**FreeDDElParam**](/windows/win32/Dde/nf-dde-freeddelparam?branch=master) function.

## Requirements



|                                     |                                                                                                      |
|-------------------------------------|------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                 |
| Header<br/>                   | <dl> <dt>Dde.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**DDEACK**](/windows/win32/Dde/ns-dde-ddeack?branch=master)
</dt> <dt>

[**FreeDDElParam**](/windows/win32/Dde/nf-dde-freeddelparam?branch=master)
</dt> <dt>

[**PackDDElParam**](/windows/win32/Dde/nf-dde-packddelparam?branch=master)
</dt> <dt>

[**PostMessage**](https://msdn.microsoft.com/library/windows/desktop/ms644944)
</dt> <dt>

[**ReuseDDElParam**](/windows/win32/Dde/nf-dde-reuseddelparam?branch=master)
</dt> <dt>

[**SendMessage**](https://msdn.microsoft.com/library/windows/desktop/ms644950)
</dt> <dt>

[**UnpackDDElParam**](/windows/win32/Dde/nf-dde-unpackddelparam?branch=master)
</dt> <dt>

[**WM\_DDE\_ADVISE**](wm-dde-advise.md)
</dt> <dt>

[**WM\_DDE\_DATA**](wm-dde-data.md)
</dt> <dt>

[**WM\_DDE\_EXECUTE**](wm-dde-execute.md)
</dt> <dt>

[**WM\_DDE\_INITIATE**](wm-dde-initiate.md)
</dt> <dt>

[**WM\_DDE\_POKE**](wm-dde-poke.md)
</dt> <dt>

[**WM\_DDE\_REQUEST**](wm-dde-request.md)
</dt> <dt>

[**WM\_DDE\_TERMINATE**](wm-dde-terminate.md)
</dt> <dt>

[**WM\_DDE\_UNADVISE**](wm-dde-unadvise.md)
</dt> <dt>

**Conceptual**
</dt> <dt>

[About Dynamic Data Exchange](about-dynamic-data-exchange.md)
</dt> </dl>

 

 




