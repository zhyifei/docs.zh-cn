---
title: GDI+ 中的基数样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 93ae09c72415fa489e62f753e51e5a3ffcfb2425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="cardinal-splines-in-gdi"></a>GDI+ 中的基数样条
基数样条是一系列的单个连接起来形成较大的曲线的曲线。 样条指定的点和张力参数数组中。 基数样条平滑地通过数组; 中的每个点有没有尖锐的角和曲线的拟合度在任何突然更改。 下图显示一组点和经过集中的每个点的基数样条。  
  
 ![基数样条](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>物理和数学样条  
 物理样条是一块薄木材或其他灵活的材料。 之前数学样条出现，设计器用于物理样条绘制曲线。 设计器将在一张纸上放置样条和锚定到给定的一组点。 设计器无法创建一条曲线样条沿绘制由应与笔或铅笔。 给定的一组点可能会产生大量的曲线，具体取决于物理样条的属性。 例如，使用极不易弯曲的样条会产生极其灵活样条曲线是不同。  
  
 数学样条的公式基于弹性棒的属性，因此生成的数学样条曲线是类似于一次生成用物理样条曲线的曲线。 就像物理样条的不同张力将生成不同的曲线通过给定的一组点，具有不同的张力参数值的数学样条将生成不同的曲线通过给定的一组点。 下图显示相同的点集通过传递的四个基本样条。 每个样条都显示了张力。 0 张力对应于无限物理张力，以强制曲线才能点之间最短的路径 （直线）。 张力为 1 对应于没有物理张力，使样条采用最小完全弯曲的路径。 张力值大于 1，曲线表现得像压缩 spring，推送到需要较长的路径。  
  
 ![基数样条曲线](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 在上图中四个样条共享的起始点处的相同切线。 的正切值是从起始点绘制到曲线的下一个点的行。 同样，在结束点的共享正切值是从结束的点到上一个点上绘制曲线的行。  
  
 若要绘制的基数样条，你需要的实例<xref:System.Drawing.Graphics>类， <xref:System.Drawing.Pen>，和的数组<xref:System.Drawing.Point>对象的实例<xref:System.Drawing.Graphics>类提供<xref:System.Drawing.Graphics.DrawCurve%2A>方法，该绘制样条，方法与<xref:System.Drawing.Pen>存储样条曲线的角度，如线条宽度和颜色的特性。 数组<xref:System.Drawing.Point>对象将存储曲线将通过传递的点。 下面的代码示例演示如何绘制通过的点的基数样条`myPointArray`。 第三个参数是张力。  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>请参阅  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [构造并绘制曲线](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
