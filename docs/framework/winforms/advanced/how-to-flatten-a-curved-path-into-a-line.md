---
title: "如何：将曲线路径展平为直线"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62dedc987c2b622dc3f3aa81dac3cdea6dd75740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>如何：将曲线路径展平为直线
A<xref:System.Drawing.Drawing2D.GraphicsPath>对象存储一系列行和贝塞尔样条。 可以将多种类型的曲线 （省略号、 弧、 基数样条） 添加到路径时，但之前存储在路径中，每个曲线转换为贝塞尔样条。 平展路径组成，将在路径中的每个贝塞尔样条转换为直线的序列。 下图显示路径之前和之后平展。  
  
 ![直线和曲线](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>若要将路径展平  
  
-   调用<xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收指定的平展的路径和原始路径之间的最大距离的平坦度自变量。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [构造并绘制路径](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
