---
Description: Creates a sprite object which is associated with a particular device. Sprite objects are used to draw 2D images to the screen.
ms.assetid: 1611073f-0590-415a-8ea5-dc1d224f20b9
title: D3DXCreateSprite function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DXCreateSprite function

Creates a sprite object which is associated with a particular device. Sprite objects are used to draw 2D images to the screen.

## Syntax


```C++
HRESULT D3DXCreateSprite(
  _In_  LPDIRECT3DDEVICE9 pDevice,
  _Out_ LPD3DXSPRITE      *ppSprite
);
```



## Parameters

<dl> <dt>

*pDevice* \[in\]
</dt> <dd>

Type: **[**LPDIRECT3DDEVICE9**](/windows/win32/d3d9helper/nn-d3d9-idirect3ddevice9?branch=master)**

Pointer to an [**IDirect3DDevice9**](/windows/win32/d3d9helper/nn-d3d9-idirect3ddevice9?branch=master) interface, the device to be associated with the sprite.

</dd> <dt>

*ppSprite* \[out\]
</dt> <dd>

Type: **[**LPD3DXSPRITE**](id3dxsprite.md)\***

Address of a pointer to an [**ID3DXSprite**](id3dxsprite.md) interface. This interface allows the user to access sprite functions.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the function succeeds, the return value is S\_OK. If the function fails, the return value can be one of the following: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Remarks

This interface can be used to draw two dimensional images in screen space of the associated device.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx9core.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[General Purpose Functions](dx9-graphics-reference-d3dx-functions-general-purpose.md)
</dt> </dl>

 

 



