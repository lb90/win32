---
Description: Modem configuration functions enable you to configure a modem before making a connection.
ms.assetid: 67d8f3c4-0295-4028-8b12-1a5e26979df5
title: Modem Configuration
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Modem Configuration

Modem configuration functions enable you to configure a modem before making a connection. An application can set modem options and determine the features of a modem without using commands specific to any modem device. Following are the general features an application may set before making a call:

-   Primary mode of operation (synchronous, asynchronous, and whether error control is enabled).
-   V.42 error control (defined by CCITT recommendation V.42), including specific parameters. CCITT stands for the International Telegraph and Telephone Consultative Committee.
-   V.42bis (defined by CCITT recommendation V.42bis) and MNP5 data compression.
-   Time-out options, including call setup, inactivity, and buffered data delivery.

Before setting a modem's configuration, an application should determine the capabilities of the modem device by using the [**GetCommProperties**](/windows/win32/Winbase/nf-winbase-getcommproperties?branch=master) function. This function fills in a [**COMMPROP**](/windows/win32/WinBase/ns-winbase-_commprop?branch=master) structure. This structure contains both a general portion, which applies to all communications devices, and a portion that is specific to each provider subtype. For modem devices, the provider-specific portion of the **COMMPROP** structure is a [**MODEMDEVCAPS**](/windows/win32/Mcx/ns-mcx-_modemdevcaps?branch=master) structure.

An application can get and set the current configuration of a modem by using the [**GetCommConfig**](/windows/win32/Winbase/nf-winbase-getcommconfig?branch=master) and [**SetCommConfig**](/windows/win32/Winbase/nf-winbase-setcommconfig?branch=master) functions, both of which use a [**COMMCONFIG**](/windows/win32/Winbase/ns-winbase-_commconfig?branch=master) structure. This structure contains both a general portion, which applies to all communications devices, and a portion that is specific to each provider subtype. For modem devices, the provider-specific portion of the **COMMCONFIG** structure is a [**MODEMSETTINGS**](/windows/win32/Mcx/ns-mcx-_modemsettings?branch=master) structure.

After configuring a modem, an application can use the Telephony Application Programming Interface (TAPI) to actually establish a connection.

The modem configuration functions do not provide for long-term management and maintenance of a modem. Modem service providers should supply modem configuration dialog boxes for this purpose.

 

 


