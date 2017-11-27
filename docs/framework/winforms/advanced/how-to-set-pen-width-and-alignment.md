---
title: "如何：设置钢笔的宽度和对齐方式"
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
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ed2a28c49554c686abb5e2635ab35b746b83465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a>如何：设置钢笔的宽度和对齐方式
当你创建<xref:System.Drawing.Pen>，你可以作为构造函数的自变量之一提供钢笔的宽度。 你还可以更改钢笔的宽度与<xref:System.Drawing.Pen.Width%2A>属性<xref:System.Drawing.Pen>类。  
  
 理论上的行都有宽度为 0。 当你绘制为 1 个像素宽的行时，像素在理论上的行上居中。 如果绘制为多个像素宽的行，像素在理论上的行上或者居中或向理论的线条的一侧显示。 你可以设置的钢笔对齐属性<xref:System.Drawing.Pen>以确定将如何相对于理论线条放置用其绘制的像素。  
  
 值<xref:System.Drawing.Drawing2D.PenAlignment.Center>， <xref:System.Drawing.Drawing2D.PenAlignment.Outset>，和<xref:System.Drawing.Drawing2D.PenAlignment.Inset>显示在下面的代码示例是的成员<xref:System.Drawing.Drawing2D.PenAlignment>枚举。  
  
 下面的代码示例绘制一条线条两次： 一次使用黑色钢笔的宽度为 1，一次使用绿色钢笔的宽度为 10。  
  
### <a name="to-vary-the-width-of-a-pen"></a>改变钢笔的宽度  
  
-   设置的值<xref:System.Drawing.Pen.Alignment%2A>属性<xref:System.Drawing.Drawing2D.PenAlignment.Center>（默认） 指定，将在理论上的行上居中用绿色钢笔绘制的像素为单位。 下图显示生成的行。  
  
     ![钢笔](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")  
  
     下面的代码示例绘制矩形两次： 一次使用黑色钢笔的宽度为 1，一次使用绿色钢笔的宽度为 10。  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>若要更改钢笔的对齐方式  
  
-   设置的值<xref:System.Drawing.Pen.Alignment%2A>属性<xref:System.Drawing.Drawing2D.PenAlignment.Center>指定用绿色钢笔绘制的像素居于矩形的边界上。  
  
     下图显示生成的矩形。  
  
     ![钢笔](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>若要创建嵌入钢笔  
  
-   通过修改前面的代码示例中的第三个语句，如下所示更改绿色钢笔的对齐方式：  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     现在像素宽绿线显示矩形的内部下, 图中所示。  
  
     ![钢笔](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")  
  
## <a name="see-also"></a>另请参阅  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
