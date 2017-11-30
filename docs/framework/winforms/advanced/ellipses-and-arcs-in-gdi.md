---
title: "GDI+ 中的椭圆和弧线"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ebeae1d076a0ebcf36d52dee1af0c0ad5f04fdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a>GDI+ 中的椭圆和弧线
您可以轻松地绘制椭圆和弧使用<xref:System.Drawing.Graphics.DrawEllipse%2A>和<xref:System.Drawing.Graphics.DrawArc%2A>方法<xref:System.Drawing.Graphics>类。  
  
## <a name="drawing-an-ellipse"></a>绘制椭圆  
 若要绘制一个椭圆，你需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawEllipse%2A>方法，与<xref:System.Drawing.Pen>对象存储特性，如宽度和用于呈现椭圆的线条颜色。 <xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawEllipse%2A>方法。 其余的自变量传递给<xref:System.Drawing.Graphics.DrawEllipse%2A>方法指定椭圆的边框。 下图显示以及其边界的矩形的椭圆。  
  
 ![椭圆和弧](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 下面的示例绘制一个椭圆;边界的矩形的宽度为 80，高度为 40 和的左上角都 （100，50）：  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>属于重载的方法的<xref:System.Drawing.Graphics>类，因此有几种方法，你可以向其提供自变量。 例如，可以构造<xref:System.Drawing.Rectangle>并将传递<xref:System.Drawing.Rectangle>到<xref:System.Drawing.Graphics.DrawEllipse%2A>作为自变量的方法：  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>绘制一段弧线，  
 一段弧线，是椭圆的的一部分。 若要绘制一段弧线，请调用<xref:System.Drawing.Graphics.DrawArc%2A>方法<xref:System.Drawing.Graphics>类。 参数<xref:System.Drawing.Graphics.DrawArc%2A>方法都是相同的参数作为<xref:System.Drawing.Graphics.DrawEllipse%2A>方法，只不过<xref:System.Drawing.Graphics.DrawArc%2A>需要起始角度和扫描角度。 下面的示例绘制一段弧线，使用 30 度起始角度和扫描角度为 180 度：  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 下图显示弧、 椭圆和的边框。  
  
 ![椭圆和弧](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [如何：创建笔](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [如何：绘制显示边框的形状](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
