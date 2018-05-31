---
Description: A single Matrix object can store a single transformation or a sequence of transformations.
ms.assetid: 1dc68ff8-6b17-4934-82da-ab2fc612aafa
title: Why Transformation Order Is Significant
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Why Transformation Order Is Significant

A single [**Matrix**](/windows/win32/gdiplusmatrix/nl-gdiplusmatrix-matrix?branch=master) object can store a single transformation or a sequence of transformations. The latter is called a *composite*  *transformation*. The matrix of a composite transformation is obtained by multiplying the matrices of the individual transformations.

In a composite transformation, the order of the individual transformations is important. For example, if you first rotate, then scale, then translate, you get a different result than if you first translate, then rotate, then scale. In Windows GDI+, composite transformations are built from left to right. If S, R, and T are scale, rotation, and translation matrices respectively, then the product SRT (in that order) is the matrix of the composite transformation that first scales, then rotates, then translates. The matrix produced by the product SRT is different from the matrix produced by the product TRS.

One reason order is significant is that transformations like rotation and scaling are done with respect to the origin of the coordinate system. Scaling an object that is centered at the origin produces a different result than scaling an object that has been moved away from the origin. Similarly, rotating an object that is centered at the origin produces a different result than rotating an object that has been moved away from the origin.

The following example combines scaling, rotation and translation (in that order) to form a composite transformation. The argument [****MatrixOrderAppend****](/windows/win32/Gdiplusenums/ne-gdiplusenums-matrixorder?branch=master) passed to the [**Graphics::RotateTransform**](/windows/win32/Gdiplusgraphics/nf-gdiplusgraphics-graphics-rotatetransform?branch=master) method specifies that the rotation will follow the scaling. Likewise, the argument [****MatrixOrderAppend****](/windows/win32/Gdiplusenums/ne-gdiplusenums-matrixorder?branch=master) passed to the [**Graphics::TranslateTransform**](/windows/win32/Gdiplusgraphics/nf-gdiplusgraphics-graphics-translatetransform?branch=master) method specifies that the translation will follow the rotation.


```
Rect rect(0, 0, 50, 50);
Pen pen(Color(255, 255, 0, 0), 0);
graphics.ScaleTransform(1.75f, 0.5f);
graphics.RotateTransform(28.0f, MatrixOrderAppend);
graphics.TranslateTransform(150.0f, 150.0f, MatrixOrderAppend);
graphics.DrawRectangle(&amp;pen, rect);
```



The following example makes the same method calls as the previous example, but the order of the calls is reversed. The resulting order of operations is first translate, then rotate, then scale, which produces a very different result than first scale, then rotate, then translate:


```
Rect rect(0, 0, 50, 50);
Pen pen(Color(255, 255, 0, 0), 0);
graphics.TranslateTransform(150.0f, 150.0f);
graphics.RotateTransform(28.0f, MatrixOrderAppend);
graphics.ScaleTransform(1.75f, 0.5f, MatrixOrderAppend);
graphics.DrawRectangle(&amp;pen, rect);
```



One way to reverse the order of the individual transformations in a composite transformation is to reverse the order of a sequence of method calls. A second way to control the order of operations is to change the matrix order argument. The following example is the same as the previous example, except that [****MatrixOrderAppend****](/windows/win32/Gdiplusenums/ne-gdiplusenums-matrixorder?branch=master) has been changed to [****MatrixOrderPrepend****](/windows/win32/Gdiplusenums/ne-gdiplusenums-matrixorder?branch=master). The matrix multiplication is done in the order SRT, where S, R, and T are the matrices for scale, rotate, and translate, respectively. The order of the composite transformation is first scale, then rotate, then translate.


```
Rect rect(0, 0, 50, 50);
Pen pen(Color(255, 255, 0, 0), 0);
graphics.TranslateTransform(150.0f, 150.0f,MatrixOrderPrepend);
graphics.RotateTransform(28.0f, MatrixOrderPrepend);
graphics.ScaleTransform(1.75f, 0.5f, MatrixOrderPrepend);
graphics.DrawRectangle(&amp;pen, rect);
```



The result of the preceding example is the same result that we achieved in the first example of this section. This is because we reversed both the order of the method calls and the order of the matrix multiplication.

 

 


