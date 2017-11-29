---
title: "如何：绘制具有线帽的线条"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e2d5a5aba4a7634e0ea8480aa9744a5a7b9721d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a>如何：绘制具有线帽的线条
可以使用一个称为线帽的多个形状绘制的开始或行尾。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]支持多种的线帽，如循环、 方形、 菱形和箭头。  
  
## <a name="example"></a>示例  
 你可以指定开头的行 （起始线帽），行 （结束端） 的末尾或虚线 (dash cap) 的短划线的线帽。  
  
 下面的示例绘制某一端箭头与另一端圆端帽的线条。 图中显示生成的行：  
  
 ![钢笔](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。 示例将代码粘贴到<xref:System.Windows.Forms.Control.Paint>传递的事件处理程序`e`作为<xref:System.Windows.Forms.PaintEventArgs>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
