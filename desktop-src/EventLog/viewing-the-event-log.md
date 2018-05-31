---
Description: When the user starts Event Viewer to view the event log entries, it calls the ReadEventLog function to obtain the EVENTLOGRECORD structures.
ms.assetid: 1d5b62cb-cf5b-4f4c-8521-1c783ae3afc7
title: Viewing the Event Log
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Viewing the Event Log

When the user starts Event Viewer to view the event log entries, it calls the [**ReadEventLog**](/windows/win32/Winbase/nf-winbase-readeventloga?branch=master) function to obtain the [**EVENTLOGRECORD**](/windows/win32/Winnt/ns-winnt-_eventlogrecord?branch=master) structures. The Event Viewer uses the event source and event identifier to get message text for each event from the registered message file (indicated by the **EventMessageFile** registry value for the source). The Event Viewer uses the [**LoadLibraryEx**](https://msdn.microsoft.com/library/windows/desktop/ms684179) function to load the message file. The Event Viewer then uses the [**FormatMessage**](https://msdn.microsoft.com/library/windows/desktop/ms679351) function to retrieve the base description string from the loaded module. Finally, the Event Viewer replaces the insertion parameters in the base description string to yield the final message string.

 

 


