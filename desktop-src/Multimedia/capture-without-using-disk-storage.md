---
title: Capture Without Using Disk Storage
description: Capture Without Using Disk Storage
ms.assetid: 2e2f1b67-69be-424c-8a6f-d9db5eeb6088
keywords:
- WM_CAP_SEQUENCE_NOFILE message
- capCaptureSequenceNoFile macro
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Capture Without Using Disk Storage

You can use capture services without writing the data to a disk file by using the [**WM\_CAP\_SEQUENCE\_NOFILE**](wm-cap-sequence-nofile.md) message (or the [**capCaptureSequenceNoFile**](/windows/win32/Vfw/nf-vfw-capcapturesequencenofile?branch=master) macro). This message is useful only in conjunction with callback functions that allow your application to use the video and audio data directly. For example, videoconferencing applications might use this message to obtain streaming video frames. The callback functions would transfer the captured images to the remote computer.

 

 



