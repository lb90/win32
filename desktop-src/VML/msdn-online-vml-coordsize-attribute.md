---
title: VML CoordSize Attribute
description: VML CoordSize Attribute
ms.assetid: 4e7a7eca-7db2-4522-be8e-e817601625ed
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# VML CoordSize Attribute

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Specifies the horizontal and vertical units of the rectangle that bounds a shape. Read/write. [IVgVector2D](msdn-online-vml-ivgvector2d-data-type.md).

**Applies To**

[Shape](shape-element--vml.md)

**Tag Syntax**

&lt;v: *element* coordsize=" *expression* "&gt;

**Script Syntax**

*element* .coordsize="*expression*"

*expression*=*element*.coordsize

**Remarks**

If not specified, the coordinate size is the same as the bounding box of the shape.

Note that this attribute is a vector and that the units are relative to the length and width of the bounding rectangle.

Also note that mapping between **coordsize** and the bounding box can be made anisotropic. Make sure that the **coordsize width** and **coordsize height** is the same as the **style width** and **height** if you don't want to distort the shape.

In scripting, because this is a 2-D vector, you can access the x and y values separately, and can also determine the type of units expected.

*VML Standard Attribute*

**Example**

The shape is 100 points high and 100 points wide, but each horizontal and vertical unit in the coordinate space is 1/10 of a point.


```HTML
   <v:shape id="rect01"
   fillcolor="red" strokecolor="red"
   coordorigin="0 0" coordsize="1000 1000"
   style="position:relative;top:0;left:0;width:100pt;height:100pt"
   path="m 1,1 l 1,200, 200,200, 200,1 x e">
   </v:shape>
```



[CoordSize Attribute Example](http://samples.msdn.microsoft.com/workshop/samples/vml/shape/examples/x_corsiz.md). (Requires Microsoft Internet Explorer 5 or greater.)

 

 



