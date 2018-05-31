---
Description: Sets the autohide and always-on-top states of the Windows taskbar.
title: ABM\_SETSTATE message
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ABM\_SETSTATE message

Sets the autohide and always-on-top states of the Windows taskbar.


```C++
SHAppBarMessage(ABM_SETSTATE, pabd); 
```



## Parameters

<dl> <dt>

*pabd* 
</dt> <dd>

A pointer to an [**APPBARDATA**](/windows/win32/Shellapi/ns-shellapi-_appbardata?branch=master) structure. You must specify the **cbSize** and **hWnd** members when sending this message. Data for the desired state is sent in the **lParam** member using one of the following values.

<dt>

<span id="0"></span>

<span id="0"></span>**0**


</dt> <dd>

Autohide and always-on-top both off

</dd> <dt>

<span id="ABS_ALWAYSONTOP"></span><span id="abs_alwaysontop"></span>

<span id="ABS_ALWAYSONTOP"></span><span id="abs_alwaysontop"></span>**ABS\_ALWAYSONTOP**


</dt> <dd>

Always-on-top on, autohide off

</dd> <dt>

<span id="ABS_AUTOHIDE"></span><span id="abs_autohide"></span>

<span id="ABS_AUTOHIDE"></span><span id="abs_autohide"></span>**ABS\_AUTOHIDE**


</dt> <dd>

Autohide on, always-on-top off

</dd> <dt>

<span id="ABS_AUTOHIDE___ABS_ALWAYSONTOP"></span><span id="abs_autohide___abs_alwaysontop"></span>

<span id="ABS_AUTOHIDE___ABS_ALWAYSONTOP"></span><span id="abs_autohide___abs_alwaysontop"></span>**ABS\_AUTOHIDE \| ABS\_ALWAYSONTOP**


</dt> <dd>

Autohide and always-on-top both on

</dd> </dl> </dd> </dl>

## Return value

Always returns **TRUE**.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Shellapi.h</dt> </dl> |



 

 



