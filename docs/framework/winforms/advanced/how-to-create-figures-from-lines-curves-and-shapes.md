---
title: "如何：使用线条、曲线和形状创建图形"
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
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b382e0e1a627d7f61ce8ac664ac47d98c3725cad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>如何：使用线条、曲线和形状创建图形
若要创建一个数字，构造<xref:System.Drawing.Drawing2D.GraphicsPath>，然后调用方法，如<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>和<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>，以将基元添加到路径。  
  
## <a name="example"></a>示例  
 下面的代码示例创建具有图形的路径：  
  
-   第一个示例创建具有单一图的路径。 图包含一段弧。圆弧有扫描角度为-180 度，这是默认坐标系统中按逆时针方向。  
  
-   第二个示例创建具有两个图片的路径。 第一个图是一段弧线后, 跟行。 第二个图是后跟一条线的曲线接行。 第一张图处于打开状态，并关闭第二个图。  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它们要求<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [构造并绘制路径](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
