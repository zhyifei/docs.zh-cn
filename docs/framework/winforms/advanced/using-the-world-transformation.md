---
title: "使用世界转换"
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
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5b2a8de0644e71a5e6ae1a5ca796f580f0c4f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-world-transformation"></a>使用世界转换
世界转换是的一个属性<xref:System.Drawing.Graphics>类。 指定的世界转换的数字以存储<xref:System.Drawing.Drawing2D.Matrix>对象，用于表示 3 × 3 矩阵。 <xref:System.Drawing.Drawing2D.Matrix>和<xref:System.Drawing.Graphics>类可以用多种方法用于设置数字的世界变换矩阵。  
  
## <a name="different-types-of-transformations"></a>不同类型的转换  
 在下面的示例中，代码将首先创建 50 × 50 矩形并将其定位在原点 （0，0）。 原点位于客户端区域的左上角。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 下面的代码应用通过 1.75 英寸 x 方向的因素，扩展矩形，并将该矩形收缩的 y 方向的 0.5 倍的缩放转换：  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 结果是一个矩形，即在 x 方向较长和短于原始 y 方向。  
  
 要旋转而不是扩展的矩形，请使用以下代码：  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 若要翻译矩形，请使用以下代码：  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [坐标系统和转换](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [在托管 GDI+ 中使用转换](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
