---
title: GDI+ 中的图形路径
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 66d30b949fbfe8190b9e2ae2ea7896ac36bf0bac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="graphics-paths-in-gdi"></a>GDI+ 中的图形路径
路径是通过组合线条、 矩形和简单曲线而形成。 回想一下，从[向量图形概述](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md)以下的基本构建基块已证明绘制图片的最有用：  
  
-   直线  
  
-   矩形  
  
-   省略号  
  
-   弧  
  
-   多边形  
  
-   基本样条  
  
-   贝塞尔样条  
  
 在 GDI + 中，<xref:System.Drawing.Drawing2D.GraphicsPath>对象允许你收集到单个单元这些构建基块的序列。 就可以调用一次绘制线条、 矩形、 多边形和曲线的整个序列<xref:System.Drawing.Graphics.DrawPath%2A>方法<xref:System.Drawing.Graphics>类。 下图显示通过结合线条、 一段弧线，贝塞尔样条和的基数样条创建的路径。  
  
 ![路径](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>使用的路径  
 <xref:System.Drawing.Drawing2D.GraphicsPath>类提供用于创建要绘制的项的序列的以下方法： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> （对于基本样条），和<xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>。 上述每种方法将重载;也就是说，每个方法都支持几个不同的参数列表。 例如，一个变体<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>方法将收到四个整数和另一个变体<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>方法接收两个<xref:System.Drawing.Point>对象。  
  
 将线条、 矩形和贝塞尔样条添加到路径的方法具有复数形式伴随方法，可将多个项添加到单个调用中的路径： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>，和<xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>。 此外，<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>和<xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>方法具有助理方法<xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A>和<xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>，将闭合的曲线或饼图添加到路径。  
  
 若要绘制的路径，你需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Pen>对象，和一个<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawPath%2A>方法，与<xref:System.Drawing.Pen>对象存储特性，如宽度和用于呈现路径的线条颜色。 <xref:System.Drawing.Drawing2D.GraphicsPath>对象存储的序列的直线和曲线组成的路径。 <xref:System.Drawing.Pen>对象和<xref:System.Drawing.Drawing2D.GraphicsPath>对象作为参数传递给<xref:System.Drawing.Graphics.DrawPath%2A>方法。 下面的示例绘制一条线、 椭圆和的贝塞尔样条组成的路径：  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 下图显示的路径。  
  
 ![路径](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 除了添加到的路径的线条、 矩形和曲线，你可以将路径添加到路径。 这允许您组合现有的路径来形成大型、 复杂的路径。  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 有两个可以向路径添加其他项： 字符串和扇形。 饼图是内部的椭圆的的一部分。 下面的示例创建从一段弧线，、 的基数样条、 字符串和饼图的一个路径：  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 下图显示的路径。 请注意，路径不需要连接;分隔弧线、 基数样条、 字符串和饼图。  
  
 ![路径](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [构造并绘制路径](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
