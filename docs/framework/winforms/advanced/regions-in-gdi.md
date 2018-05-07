---
title: GDI+ 中的区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: dc7f10571163d447802c90cd61d71b11d0e695d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="regions-in-gdi"></a>GDI+ 中的区域
区域是输出设备的显示区域的一部分。 区域可以是简单 （单个矩形） 或复杂 （多边形和闭合的曲线的组合）。 下图显示了两个区域： 一个从一个矩形、 构造和路径中的其他构造。  
  
 ![区域](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>使用区域  
 区域通常用于剪辑和命中测试。 剪辑涉及将绘制限制到特定区域的显示区域中，通常需要更新的部分。 命中测试包括检查以确定指示光标是否屏幕的某些区域中按下鼠标按钮时发生。  
  
 您可以构造从矩形或路径的区域。 你还可以通过组合现有区域创建复杂的区域。 <xref:System.Drawing.Region>类提供了以下方法将组合区域： <xref:System.Drawing.Region.Intersect%2A>， <xref:System.Drawing.Region.Union%2A>， <xref:System.Drawing.Region.Xor%2A>， <xref:System.Drawing.Region.Exclude%2A>，和<xref:System.Drawing.Region.Complement%2A>。  
  
 两个区域的交集是属于两个区域的所有点的集合。 联合是组属于一个或另一个或两个区域的所有点。 区域的补集是一套不在区域的所有点。 下图显示了交集和在上图中所示的两个区域的联合。  
  
 ![区域](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 <xref:System.Drawing.Region.Xor%2A>方法应用于一对区域，可生成，包含所有属于一个区域或另一个，而不是两个数据点的区域。 <xref:System.Drawing.Region.Exclude%2A>方法应用于一对区域，可生成，包含中的第一个区域不在第二个区域的所有点的区域。 下图显示来自应用的区域<xref:System.Drawing.Region.Xor%2A>和<xref:System.Drawing.Region.Exclude%2A>到本主题开头的两个区域的方法。  
  
 ![区域](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 若要填充区域，你需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Brush>对象，和一个<xref:System.Drawing.Region>对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.FillRegion%2A>方法，与<xref:System.Drawing.Brush>对象存储填充，如颜色或图案的特性。 下面的示例填充具有纯色的区域。  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [使用区域](../../../../docs/framework/winforms/advanced/using-regions.md)
