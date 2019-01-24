---
title: 如何：曲线的路径展行
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: aa47a655417cdf82d79fb222dc6ff6f6d8c3a947
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601813"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>如何：曲线的路径展行
一个<xref:System.Drawing.Drawing2D.GraphicsPath>对象将存储一系列行和贝塞尔自由绘制曲线。 可以将多种类型的曲线 （省略号，弧线，基数样条） 添加到路径，但之后再将它存储在路径中的各段曲线转换为贝塞尔样条。 拉平路径组成，将在路径中的每个贝塞尔自由绘制曲线转换为一系列直线。 下图显示一个路径之前和之后平展。  
  
 ![直线和曲线](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>若要平展路径  
  
-   调用<xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法的<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收指定平展和原始路径之间的最大距离的展平自变量。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [构造并绘制路径](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
