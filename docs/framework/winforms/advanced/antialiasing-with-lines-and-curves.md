---
title: "用直线和曲线抗锯齿"
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
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d69d635fbdd8720937cd189826c1496b8126ddef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="antialiasing-with-lines-and-curves"></a>用直线和曲线抗锯齿
当你使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]绘制线条，提供的起始点和结束点的行，但不是需要在行上提供有关单个像素的任何信息。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]显示驱动程序软件，以确定哪些像素将打开以显示特定显示设备上的行与协同工作。  
  
## <a name="aliasing"></a>别名  
 请考虑从点 （4，2） 转到 （16，10） 的点的垂直红线。 假定坐标系统中的左上角有其源的度量单位是像素。 此外假定指向到右侧和 y 轴点的 x 轴下方。 下图显示在彩色背景上绘制的红色行的放大的视图。  
  
 ![行、 未抗锯齿](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 用于呈现行的红色像素是不透明的。 在行中有任何半透明的像素。 行呈现的此类型使行交错的外观，并在行查找有点像楼梯。 表示带有楼梯的线的这种技术称为别名;楼梯是理论的线条的别名。  
  
## <a name="antialiasing"></a>抗锯齿  
 一种用于呈现一条线的更复杂的方法涉及使用半透明的像素，以及不透明的像素为单位。 设置为纯红色的像素为单位的红色和背景色混合，具体取决于如何关闭其或到行。 这种类型的呈现称为抗锯齿和结果人眼视为更平滑的行中。 下图显示如何将特定的像素混合和背景来生成抗锯齿的直线。  
  
 ![消除直线的锯齿](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 抗锯齿功能，也称为平滑，也可以应用于曲线。 下图显示了平滑椭圆的放大的视图。  
  
 ![消除曲线的锯齿](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 下图显示其实际大小，一次没有抗锯齿，一次使用抗锯齿功能中的同一个椭圆。  
  
 ![抗锯齿示例](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 若要绘制的直线和曲线使用抗锯齿效果，创建的实例<xref:System.Drawing.Graphics>类，然后设置其<xref:System.Drawing.Graphics.SmoothingMode%2A>属性<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>或<xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>。 然后调用绘制方法之一，同一<xref:System.Drawing.Graphics>类。  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：对文本使用抗锯齿效果](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
