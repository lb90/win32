---
title: Asynchronous Call State
description: This page describes the Asynchronous Call State for RPC calls.
ms.assetid: 4a594dad-a8a1-44e9-8648-ddc2539c234c
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Asynchronous Call State

This page describes the Asynchronous Call State for RPC calls.

## Client Behavior



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>State</th>
<th>State name</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>C</td>
<td>Make the call</td>
<td>Make the RPC
<ul>
<li>On success go to state WComp</li>
<li>On exception go to End</li>
</ul>
To fail: go to Can<br/></td>
</tr>
<tr class="even">
<td>Can</td>
<td>Cancel the call</td>
<td>Call [<strong>RpcAsyncCancelCall</strong>](/windows/win32/Rpcasync/nf-rpcasync-rpcasynccancelcall?branch=master)Go to WComp<br/></td>
</tr>
<tr class="odd">
<td>WComp</td>
<td>Wait for completion</td>
<td>Wait for notificationCall-complete notification should be received<br/> Go to Comp<br/></td>
</tr>
<tr class="even">
<td>Comp</td>
<td>Completion</td>
<td>Issue [<strong>RpcAsyncCompleteCall</strong>](/windows/win32/Rpcasync/nf-rpcasync-rpcasynccompletecall?branch=master)Go to End<br/></td>
</tr>
<tr class="odd">
<td>End</td>


</tr>
</tbody>
</table>



 

## Server Behavior



| State | State name     | Action                                                                                                                                                                                                              |
|-------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| D     | Dispatch       | The call is dispatched by the RPC runtimeProcess<br/> Go to Comp<br/> To fail fatally (while executing on the RPC thread): Raise exception; go to End<br/> To fail gracefully: go to A<br/> |
| A     | Abort the call | Call [**RpcAsyncAbortCall**](/windows/win32/Rpcasync/nf-rpcasync-rpcasyncabortcall?branch=master)Go to End<br/>                                                                                                                                             |
| Comp  | Completion     | Issue [**RpcAsyncCompleteCall**](/windows/win32/Rpcasync/nf-rpcasync-rpcasynccompletecall?branch=master)Go to End<br/>                                                                                                                                      |
| End   |                |                                                                                                                                                                                                                     |



 

 

 




