---
title: "如何：使用钢笔绘制线条"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 481200d1383fd6cc5e95379823af651c78275cb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>如何：使用钢笔绘制线条
若要绘制线条，你需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawLine%2A>方法，与<xref:System.Drawing.Pen>对象存储在行中，如颜色和宽度的功能。  
  
## <a name="example"></a>示例  
 下面的示例绘制中的一行 20 (10） 到 （300，100）。 第一个语句使用<xref:System.Drawing.Pen.%23ctor%2A>类构造函数来创建黑色钢笔。 一个自变量传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数是<xref:System.Drawing.Color>创建与对象<xref:System.Drawing.Color.FromArgb%2A>方法。 用于创建值<xref:System.Drawing.Color>对象 — （255，0，0，0）-对应于颜色的 alpha、 红色、 绿色和蓝色组件。 这些值定义不透明的黑色钢笔。  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Pen>  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [GDI+ 中的笔、直线和矩形](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
