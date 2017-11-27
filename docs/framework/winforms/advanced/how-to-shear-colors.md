---
title: "如何：修剪颜色"
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
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a>如何：修剪颜色
剪切增加或减少量将另一个颜色组件一定比例的颜色组件。 例如，考虑其中红色组件增加了一个半个蓝色分量的值的转换。 在此类转换，（0.2、 0.5，1） 的颜色将变为 （0.7、 0.5，1）。 新的红色组件是 0.2 + (1/2)(1) = 0.7。  
  
## <a name="example"></a>示例  
 下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars4.bmp 的对象。 然后该代码将应用到图像中的每个像素上一段中所述的倾斜转换。  
  
 下图右侧显示在左侧的原始映像和剪切后的图像。  
  
 ![切变颜色](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 下表列出的四个栏的颜色矢量之前和之后的倾斜转换。  
  
|原始|剪切|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 替换`ColorBars.bmp`用的映像名称和你系统上有效的路径。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [对图像重新着色](../../../../docs/framework/winforms/advanced/recoloring-images.md)
