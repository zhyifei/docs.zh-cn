---
title: 如何：将曲线路径平展为直线
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215152"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>如何：将曲线路径平展为直线
一个<xref:System.Drawing.Drawing2D.GraphicsPath>对象将存储一系列行和贝塞尔自由绘制曲线。 可以将多种类型的曲线 （省略号，弧线，基数样条） 添加到路径，但之后再将它存储在路径中的各段曲线转换为贝塞尔样条。 拉平路径组成，将在路径中的每个贝塞尔自由绘制曲线转换为一系列直线。 下图显示一个路径之前和之后平展。  
  
 ![直线和曲线](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>若要平展路径  
  
-   调用<xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法的<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收指定平展和原始路径之间的最大距离的展平自变量。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [直线、曲线和形状](lines-curves-and-shapes.md)
- [构造并绘制路径](constructing-and-drawing-paths.md)
