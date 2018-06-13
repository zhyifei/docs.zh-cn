---
title: GDI+ 中的多边形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 3ac6b9b651e65a45612cf2bd8ff17990c5cfba0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525842"
---
# <a name="polygons-in-gdi"></a>GDI+ 中的多边形
多边形是有三个或多个直条边的闭合的形状。 例如，一个三角形是有三条边的多边形、 矩形是有四条边的多边形和形是有五条边的多边形。 下图显示了几个多边形。  
  
 ![多边形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>绘制多边形  
 若要绘制多边形，你需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Pen>对象和数组的<xref:System.Drawing.Point>(或<xref:System.Drawing.PointF>) 对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawPolygon%2A>方法。 <xref:System.Drawing.Pen>对象存储特性，如宽度和用于呈现多边形、 和的数组的线条的颜色，<xref:System.Drawing.Point>对象将存储要由直线连接的点。 <xref:System.Drawing.Pen>对象和数组<xref:System.Drawing.Point>对象作为参数传递给<xref:System.Drawing.Graphics.DrawPolygon%2A>方法。 下面的示例绘制三双侧多边形。 请注意，有中的只有三个点`myPointArray`: （0，0），（50、 30） 和 （30、 60）。 <xref:System.Drawing.Graphics.DrawPolygon%2A>方法会自动关闭多边形通过绘制中的一行 （30、 60） 返回到起始点 （0，0）。  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 下图显示多边形。  
  
 ![多边形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：创建笔](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
