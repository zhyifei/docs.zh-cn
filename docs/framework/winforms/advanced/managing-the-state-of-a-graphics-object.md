---
title: 管理 Graphics 对象的状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: b81c3c8b25f13ac5791b5d2116b8536575f9ebcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525114"
---
# <a name="managing-the-state-of-a-graphics-object"></a>管理 Graphics 对象的状态
<xref:System.Drawing.Graphics>类的核心是[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。 若要绘制任何内容，你可以获取<xref:System.Drawing.Graphics>对象、 设置其属性，并调用其方法<xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawImage%2A>， <xref:System.Drawing.Graphics.DrawString%2A>，以及类似的内容)。  
  
 下面的示例调用<xref:System.Drawing.Graphics.DrawRectangle%2A>方法<xref:System.Drawing.Graphics>对象。 第一个自变量传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>方法是<xref:System.Drawing.Pen>对象。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>图形状态  
 A<xref:System.Drawing.Graphics>对象不仅仅提供绘制方法，如<xref:System.Drawing.Graphics.DrawLine%2A>和<xref:System.Drawing.Graphics.DrawRectangle%2A>。 A<xref:System.Drawing.Graphics>对象还维护图形状态，可以划分为以下类别：  
  
-   质量设置  
  
-   转换  
  
-   剪辑区域  
  
### <a name="quality-settings"></a>质量设置  
 A<xref:System.Drawing.Graphics>对象具有多个属性影响绘制的项的质量。 例如，你可以设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性指定应用于文本消除锯齿 （如果有） 的类型。 影响质量其他属性都是<xref:System.Drawing.Graphics.SmoothingMode%2A>， <xref:System.Drawing.Graphics.CompositingMode%2A>， <xref:System.Drawing.Graphics.CompositingQuality%2A>，和<xref:System.Drawing.Graphics.InterpolationMode%2A>。  
  
 下面的示例绘制两个椭圆，另一个使用平滑模式设置为<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>另一个使用平滑模式设置为<xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>转换  
 A<xref:System.Drawing.Graphics>对象维护应用于由该绘制的所有项的两种转换 （world 和页）<xref:System.Drawing.Graphics>对象。 任何仿射转换可以存储在世界变换。 仿射转换包括缩放、 旋转、 反射、 倾斜和转换。 可以使用页转换，缩放和更改单位 （例如，为英寸的像素）。 有关详细信息，请参阅[坐标系和坐标转换](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)。  
  
 下面的示例设置世界变换和页变换的<xref:System.Drawing.Graphics>对象。 世界转换设置为 30 度旋转。 页转换设置以便坐标传递到第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>将被视为毫米等，而不是像素。 这段代码将两个相同调用<xref:System.Drawing.Graphics.DrawEllipse%2A>方法。 世界转换应用于第一个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用，而且这两种转换 （world 和页） 应用到第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 下图显示两个椭圆。 请注意，30 度旋转有关的源的坐标系统 （客户端区域的左上角），而不省略号的中心。 另请注意钢笔的宽度为 1 的第二个椭圆意味着在第一个椭圆和 1 毫米 1 个像素。  
  
 ![椭圆](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### <a name="clipping-region"></a>剪辑区域  
 A<xref:System.Drawing.Graphics>对象维护适用于由该绘制的所有项的剪辑区域<xref:System.Drawing.Graphics>对象。 你可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。  
  
 下面的示例通过两个矩形的并集创建形 plus 区域。 该区域指定的剪辑区域为<xref:System.Drawing.Graphics>对象。 然后的代码绘制仅限于的剪辑区域的内部的两行。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 下图显示裁剪后的行。  
  
 ![有限的剪辑区域](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [使用嵌套的图形容器](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
