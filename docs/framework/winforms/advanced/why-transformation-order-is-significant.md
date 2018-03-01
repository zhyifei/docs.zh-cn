---
title: "为什么转换顺序非常重要"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd3363a1afb8658ed3bb27359259cb752464507d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="why-transformation-order-is-significant"></a>为什么转换顺序非常重要
单个<xref:System.Drawing.Drawing2D.Matrix>对象可以存储一次转换的序列。 后者称为复合转换。 复合转换的矩阵被获取的各个变换的矩阵相乘。  
  
## <a name="composite-transform-examples"></a>复合转换示例  
 在复合转换中，各个变换之间的顺序很重要。 例如，如果第一次旋转，则缩放，则转换，你获得不同的结果不是如果首先将转换，然后旋转，则缩放。 在[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，复合转换生成从左到右。 如果 S、 R 和 T 分别缩放、 旋转和平移矩阵，然后产品 （按此顺序） 的 SRT 是该第一个刻度的复合变换的矩阵，旋转，然后将转换。 生成产品的矩阵 SRT 是不同的生成的乘积 TRS 的矩阵。  
  
 顺序很重要的原因之一是，这样像旋转和缩放转换是针对坐标系统的原点。 缩放以原点中心的对象生成比缩放已离开源的对象不同的结果。 同样，轮换基于原点居中的对象生成已离开源的对象与旋转不同的结果。  
  
 下面的示例结合缩放、 旋转和平移 （按照这个顺序），以形成复合转换。 自变量<xref:System.Drawing.Drawing2D.MatrixOrder.Append>传递给<xref:System.Drawing.Graphics.RotateTransform%2A>方法指示旋转将遵循这样的缩放。 同样，参数<xref:System.Drawing.Drawing2D.MatrixOrder.Append>传递给<xref:System.Drawing.Graphics.TranslateTransform%2A>方法指示转换将遵循旋转。 <xref:System.Drawing.Drawing2D.MatrixOrder.Append>和<xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>成员的<xref:System.Drawing.Drawing2D.MatrixOrder>枚举。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 下面的示例使相同的方法调用与上面的示例中，但在调用的顺序相反。 生成的运算顺序平移、 依次旋转和缩放，这样会生成非常不同的结果比第一个刻度，然后旋转，转换。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 若要反转的复合转换中的各个转换顺序的一种方法是要反转的一系列方法调用的顺序。 第二种方法控制的运算顺序是更改矩阵顺序的参数。 下面的示例是前面示例中，但相同<xref:System.Drawing.Drawing2D.MatrixOrder.Append>已更改为<xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>。 矩阵乘法的顺序排序，其中 S、 R、 T 会缩放、 旋转的矩阵和翻译，分别。 复合转换的顺序第一个刻度，然后旋转，则转换。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 立即上述示例的结果作为本主题中的第一个示例的结果是相同的。 这是因为我们反转方法调用的顺序和矩阵乘法的顺序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [坐标系统和转换](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [在托管 GDI+ 中使用转换](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
