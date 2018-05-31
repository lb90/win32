---
title: Shader Specified Stencil Reference Value
description: Enabling pixel shaders to output the Stencil Reference Value, rather than using the API-specified one, enables a very fine granular control over stencil operations.
ms.assetid: 6E336623-9746-4872-ADC1-C5489F53D7AE
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Shader Specified Stencil Reference Value

Enabling pixel shaders to output the Stencil Reference Value, rather than using the API-specified one, enables a very fine granular control over stencil operations.

The shader specified value replaces the API-specified *Stencil Reference Value* for that invocation, which means the change affects both the stencil test, and when stencil op D3D11\_STENCIL\_OP\_REPLACE (one member of [**D3D11\_STENCIL\_OP**](/windows/win32/D3D11/ne-d3d11-d3d11_stencil_op?branch=master)) is used to write the reference value to the stencil buffer.

In earlier versions of D3D11, the Stencil Reference Value can only be specified by the [**ID3D11DeviceContext::OMSetDepthStencilState**](/windows/win32/D3D11/nf-d3d11-id3d11devicecontext-omsetdepthstencilstate?branch=master) method. This means that this value can only be defined on a per-draw granularity. This D3D11.3 feature enables developers to read and use the Stencil Reference Value (`SV_StencilRef`) that is output from a pixel shader, meaning that it can be specified on a per-pixel or per-sample granularity.

This feature is optional in D3D11.3. To test for its support, check the `PSSpecifiedStencilRefSupported` boolean field of [**D3D11\_FEATURE\_DATA\_D3D11\_OPTIONS2**](/windows/win32/D3D11/ns-d3d11-d3d11_feature_data_d3d11_options2?branch=master) using [**ID3D11Device::CheckFeatureSupport**](/windows/win32/D3D11/nf-d3d11-id3d11device-checkfeaturesupport?branch=master)

Here is an example of the use of `SV_StencilRef` in a pixel shader:

``` syntax
float main2(float4 c : COORD) : SV_StencilRef
{
    return c;
}
```

## Related topics

<dl> <dt>

[Direct3D 11.3 Features](direct3d-11-3-features.md)
</dt> <dt>

[Shader Model 5.1](https://msdn.microsoft.com/library/windows/desktop/dn933277)
</dt> </dl>

 

 



