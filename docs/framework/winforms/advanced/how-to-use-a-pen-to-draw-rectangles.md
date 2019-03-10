---
title: 如何：使用笔绘制矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: 2441687cb36d0780b7fbc935c5cb0edc74bc6ba0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712170"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>如何：使用笔绘制矩形
若要绘制矩形，需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawRectangle%2A>方法，和<xref:System.Drawing.Pen>对象将存储的行中，如颜色和宽度的功能。  
  
## <a name="example"></a>示例  
 下面的示例绘制一个具有在其左上角的矩形 （10，10）。 矩形的宽度为 100，50 的高度。 第二个参数传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数指示钢笔的宽度为 5 像素。  
  
 当绘制矩形时，触笔上居中显示矩形的边界。 矩形的边钢笔的宽度为 5，因为所绘制的 5 个像素宽，因此绘制该 1 像素上边界本身，2 个像素绘制内，和 2 个像素绘制在外部。 有关笔对齐方式的更多详细信息，请参阅[如何：设置笔的宽度和对齐方式](how-to-set-pen-width-and-alignment.md)。  
  
 下图显示了所得矩形的大小。 点线显示，其中矩形已绘制如果钢笔的宽度必须被一个像素。 矩形的左上角的放大的视图显示胖黑色线条在这些点线上居中。  
  
 ![笔](./media/pens1.gif "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅
- [使用笔绘制直线和形状](using-a-pen-to-draw-lines-and-shapes.md)
