---
title: "使用转换来调整颜色"
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7515f34858ef6f4b0495ac6fc545ae498d45c7f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-transformations-to-scale-colors"></a>使用转换来调整颜色
缩放变换乘以一个或多个由大量的四个颜色组件。 下表给出颜色矩阵条目，用于表示缩放。  
  
|组件可按比例|矩阵条目|  
|----------------------------|------------------|  
|红色|[0][0]|  
|绿色|[1][1]|  
|蓝色|[2][2]|  
|Alpha|[3][3]|  
  
## <a name="scaling-one-color"></a>缩放的一种颜色  
 下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars2.bmp 的对象。 然后代码蓝色分量每个像素的图像中的 2 倍。 转换后的图像旁边绘制原始图像。  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 下图右侧显示在左侧的原始映像和缩放的图像。  
  
 ![调整颜色](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 下表列出的四个栏的颜色矢量之前和之后的蓝色缩放。 请注意，第四个颜色栏中的蓝色组件发送给 0.6 了从 0.8。 这是因为[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]保留仅结果的小数部分。 例如，(2)(0.8) = 1.6 版和 1.6 的小数部分为 0.6。 保留仅的小数部分可确保结果也始终在间隔 [0，1]。  
  
|原始|缩放|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>缩放多个颜色  
 下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars2.bmp 的对象。 然后，该代码缩放图像中的每个像素的红色、 绿色和蓝色组件。 红色的组件按比例缩小 25%、 绿色组件按比例缩小 35%和蓝色分量缩小了 50%。  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 下图右侧显示在左侧的原始映像和缩放的图像。  
  
 ![调整颜色](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 下表列出的四个栏的颜色矢量之前和之后的红色、 绿色和蓝色的缩放。  
  
|原始|缩放|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [对图像重新着色](../../../../docs/framework/winforms/advanced/recoloring-images.md)
