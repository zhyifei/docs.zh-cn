---
title: 在 GDI+ 中限制绘制图面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: b457e94acb334dc012f017090c63189de372592d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523918"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>在 GDI+ 中限制绘制图面
剪辑涉及将绘制限制为某些矩形或区域。 下图显示字符串"Hello"剪辑到心形区域。  
  
 ![受限绘制图面](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>区域使用剪辑  
 区域可以构造从路径，并且路径可以包含的字符串，概述了，因此你可用于剪辑的轮廓包围的文本。 下图显示了一套同心省略号剪辑到的文本字符串的内部。  
  
 ![受限绘制图面](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 若要绘制与剪辑，创建<xref:System.Drawing.Graphics>对象，设置其<xref:System.Drawing.Graphics.Clip%2A>属性，然后调用绘制方法相同<xref:System.Drawing.Graphics>对象：  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [使用区域](../../../../docs/framework/winforms/advanced/using-regions.md)
