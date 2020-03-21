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
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182457"
---
# <a name="managing-the-state-of-a-graphics-object"></a>管理 Graphics 对象的状态
该<xref:System.Drawing.Graphics>课程是 GDI® 的核心。 要绘制任何内容，请获取<xref:System.Drawing.Graphics>对象、设置其属性并调用其方法<xref:System.Drawing.Graphics.DrawLine%2A>、、<xref:System.Drawing.Graphics.DrawString%2A><xref:System.Drawing.Graphics.DrawImage%2A>等。  
  
 下面的示例调用<xref:System.Drawing.Graphics.DrawRectangle%2A><xref:System.Drawing.Graphics>对象的方法。 传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>方法的第一个参数是对象<xref:System.Drawing.Pen>。  
  
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
 对象<xref:System.Drawing.Graphics>的作用不仅仅是提供绘图方法，如<xref:System.Drawing.Graphics.DrawLine%2A>和<xref:System.Drawing.Graphics.DrawRectangle%2A>。 对象<xref:System.Drawing.Graphics>还维护图形状态，可以分为以下几类：  
  
- 质量设置  
  
- 转换  
  
- 剪切区域  
  
### <a name="quality-settings"></a>质量设置  
 对象<xref:System.Drawing.Graphics>具有多个属性，这些属性会影响所绘制的项的质量。 例如，<xref:System.Drawing.Graphics.TextRenderingHint%2A>可以将 属性设置为指定应用于文本的反锯齿类型（如果有）。 影响质量<xref:System.Drawing.Graphics.SmoothingMode%2A>的其他属性是 、<xref:System.Drawing.Graphics.CompositingMode%2A><xref:System.Drawing.Graphics.CompositingQuality%2A>和<xref:System.Drawing.Graphics.InterpolationMode%2A>。  
  
 下面的示例绘制两个椭圆，一个设置为平滑模式<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>，另一个将平滑模式设置为 ： <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>  
  
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
 对象<xref:System.Drawing.Graphics>维护应用于该<xref:System.Drawing.Graphics>对象绘制的所有项的两个转换（世界和页面）。 任何仿冒变换都可以储存在世界变换中。 仿法变换包括缩放、旋转、反射、倾斜和平移。 页面转换可用于缩放和更改单位（例如，像素到英寸）。 有关详细信息，请参阅[坐标系和变换](coordinate-systems-and-transformations.md)。  
  
 下面的示例设置<xref:System.Drawing.Graphics>对象的世界和页面转换。 世界转型设置为 30 度旋转。 设置页面变换，以便传递给第二<xref:System.Drawing.Graphics.DrawEllipse%2A>个坐标将被视为毫米而不是像素。 代码对<xref:System.Drawing.Graphics.DrawEllipse%2A>该方法进行两个相同的调用。 世界转换应用于第一个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用，并且两个转换（世界和页面）都应用于第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用。  
  
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
  
 下图显示了两个椭圆。 请注意，30 度旋转是关于坐标系的原点（工作区的左上角），而不是椭圆的中心。 另请注意，笔宽度 1 表示第一个椭圆的 1 像素，第二个椭圆的笔宽度为 1 毫米。  
  
 ![显示两个椭圆的插图：旋转和笔宽度。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>剪切区域  
 对象<xref:System.Drawing.Graphics>维护一个裁剪区域，该区域适用于该<xref:System.Drawing.Graphics>对象绘制的所有项目。 您可以通过调用<xref:System.Drawing.Graphics.SetClip%2A>方法来设置裁剪区域。  
  
 下面的示例通过形成两个矩形的合并来创建一个加形区域。 该区域被指定为<xref:System.Drawing.Graphics>对象的剪切区域。 然后，代码绘制两行，这些行仅限于裁剪区域的内部。  
  
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
  
 下图显示了剪切的线条：  
  
 ![显示有限剪辑区域的图表。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [使用嵌套的 Graphics 容器](using-nested-graphics-containers.md)
