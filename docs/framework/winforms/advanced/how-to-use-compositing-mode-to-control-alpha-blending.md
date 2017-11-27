---
title: "如何：使用复合模式控制 Alpha 混合"
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
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564d46cb2d72ac63962657b39146489aaafd6a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>如何：使用复合模式控制 Alpha 混合
可能有些时候你想要创建具有以下特征屏幕位图操作：  
  
-   颜色的 alpha 值都小于 255。  
  
-   颜色未 alpha 混合相互创建位图。  
  
-   显示完成的位图时，位图中的颜色将为与显示设备上的背景色混合的字母。  
  
 若要创建这样的位图，请构造一个空白<xref:System.Drawing.Bitmap>对象，以及然后构造<xref:System.Drawing.Graphics>对象基于该位图。 设置的复合模式<xref:System.Drawing.Graphics>对象传递给<xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>。  
  
## <a name="example"></a>示例  
 下面的示例创建<xref:System.Drawing.Graphics>对象基于<xref:System.Drawing.Bitmap>对象。 该代码使用<xref:System.Drawing.Graphics>对象以及两个半透明的画笔 (字母 = 160) 来绘制位图上。 该代码填充红色椭圆和绿色椭圆使用半透明的画笔。 绿色椭圆重叠的红色椭圆，但由于不与红色混合绿色的复合模式<xref:System.Drawing.Graphics>对象设置为<xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>。  
  
 该代码在屏幕上绘制位图两次： 一次白色背景和上一次彩色背景。 这两个椭圆的一部分在位图中像素具有为 160 的 alpha 分量，因此省略号混合与屏幕上的背景颜色。  
  
 下图显示的代码示例的输出。 请注意，省略号混合和背景，但它们之间不相互进行混合。  
  
 ![源副本](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 此代码示例包含此语句：  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 如果你想省略号可与每个其他以及后台混合，则将该语句更改为以下：  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 下图显示修改后的代码的输出。  
  
 ![源通过](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [alpha 值混合处理直线和填充](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
