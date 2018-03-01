---
title: "如何：在 Windows 窗体上绘制线条"
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
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 78ad7d455f1de4b7077288d9575ea4907c3f218d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>如何：在 Windows 窗体上绘制线条
此示例窗体上绘制线条。 通常情况下，当你绘制在窗体上，你处理窗体的<xref:System.Windows.Forms.Control.Paint>事件并执行绘制使用<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>属性<xref:System.Windows.Forms.PaintEventArgs>，此示例中所示  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="robust-programming"></a>可靠编程  
 始终应调用<xref:System.IDisposable.Dispose%2A>对任何对象所消耗的系统资源，如<xref:System.Drawing.Pen>对象。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics.DrawLine%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [图形编程入门](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
