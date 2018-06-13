---
title: 向量图形概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 31fec6d0d3769251d21783b4657d00b06431e942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528333"
---
# <a name="vector-graphics-overview"></a>向量图形概述
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 坐标系统上绘制线条、 矩形和其他形状。 你可以选择使用不同的坐标系统，但默认坐标系统有原点左上角 x 轴指向右和向下 y 轴。 默认坐标系统中单位是度量的像素。  
  
## <a name="the-building-blocks-of-gdi"></a>GDI + 构建基块  
 ![矢量图形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 计算机监视器上的点调用图片元素或像素的矩形数组创建其显示。 有所不同到下一行，一个监视器的屏幕显示的像素数并且在单个监视器显示的像素数通常可以将在某种程度上由用户。  
  
 ![矢量图形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 当你使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]若要绘制线条、 矩形或曲线，提供有关要绘制的项的某些关键信息。 例如，你可以通过提供两个点，指定的行，并可以通过提供一个点、 高度和宽度指定矩形。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 显示驱动程序软件，以确定哪些像素必须打开以显示行、 矩形或曲线协同工作。 下图显示已打开，可以显示一条线的 （4，2） 的点到点 （12、 8） 的像素。  
  
 ![矢量图形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 随着时间推移，某些基本的构建基块已被公认为最适用于创建二维图片。 这些构建基块，所有支持的[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，给定以下列表中：  
  
-   直线  
  
-   矩形  
  
-   省略号  
  
-   弧  
  
-   多边形  
  
-   基本样条  
  
-   贝塞尔曲线样条  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>进行绘制与图形对象的方法  
 <xref:System.Drawing.Graphics>类[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供在前面的列表中绘制项的以下方法： <xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawRectangle%2A>， <xref:System.Drawing.Graphics.DrawEllipse%2A>， <xref:System.Drawing.Graphics.DrawPolygon%2A>， <xref:System.Drawing.Graphics.DrawArc%2A>， <xref:System.Drawing.Graphics.DrawCurve%2A> （对于基本样条），和<xref:System.Drawing.Graphics.DrawBezier%2A>. 上述每种方法将重载;也就是说，每个方法都支持几个不同的参数列表。 例如，一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和四个整数，而另一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和第二个<xref:System.Drawing.Point>对象。  
  
 绘制线条、 矩形和贝塞尔样条的方法具有复数形式伴随方法，可在单个调用中绘制多个项： <xref:System.Drawing.Graphics.DrawLines%2A>， <xref:System.Drawing.Graphics.DrawRectangles%2A>，和<xref:System.Drawing.Graphics.DrawBeziers%2A>。 此外，<xref:System.Drawing.Graphics.DrawCurve%2A>方法具有助理方法<xref:System.Drawing.Graphics.DrawClosedCurve%2A>，关闭一条曲线的曲线的结束点连接到的起始点。  
  
 所有的绘制方法<xref:System.Drawing.Graphics>类结合工作<xref:System.Drawing.Pen>对象。 若要绘制任何内容，必须创建至少两个对象：<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。 <xref:System.Drawing.Pen>对象存储特性，如线条宽度和颜色，要绘制的项。 <xref:System.Drawing.Pen>对象作为一个参数传递给绘制的方法。 例如，一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和四个整数中绘制的矩形宽度为 100，高度为 50 到的左上角的以下示例所示 （20，10）：  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
