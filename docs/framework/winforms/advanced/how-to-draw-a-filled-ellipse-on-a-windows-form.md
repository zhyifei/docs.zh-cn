---
title: "如何：在 Windows 窗体上绘制实心椭圆"
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
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12b17f92fc90cde1e0c1841fc7f9d63728d50294
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a>如何：在 Windows 窗体上绘制实心椭圆
此示例窗体上绘制实心的椭圆。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 无法调用此方法中<xref:System.Windows.Forms.Form.Load>事件处理程序。 不会重新绘制的内容的绘制，如果窗体调整大小或另一种形式被遮盖。 若要使你自动重绘的内容，则应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。  
  
## <a name="robust-programming"></a>可靠编程  
 始终应调用<xref:System.IDisposable.Dispose%2A>对任何对象所消耗的系统资源，如<xref:System.Drawing.Brush>和<xref:System.Drawing.Graphics>对象。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [图形编程入门](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [alpha 值混合处理直线和填充](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [使用画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
