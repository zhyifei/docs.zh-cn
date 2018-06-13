---
title: 如何：绘制用纹理填充的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 1895c752340d8d764205b5a32b9af0861303841a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522183"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>如何：绘制用纹理填充的线条
而不是绘制一条线使用纯色，您可以绘制用纹理行。 若要绘制的直线和曲线用纹理，创建<xref:System.Drawing.TextureBrush>对象，并将其传递<xref:System.Drawing.TextureBrush>对象传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数。 使用纹理画笔相关联的位图可用于平铺平面 （不可见的方式），并当钢笔绘制线条或曲线，钢笔笔画发现特定的平铺的纹理的像素。  
  
## <a name="example"></a>示例  
 下面的示例创建<xref:System.Drawing.Bitmap>文件中的对象`Texture1.jpg`。 该位图用于构造<xref:System.Drawing.TextureBrush>对象，与<xref:System.Drawing.TextureBrush>对象用于构造<xref:System.Drawing.Pen>对象。 调用<xref:System.Drawing.Graphics.DrawImage%2A>绘制位图，并使用在其左上角 （0，0）。 调用<xref:System.Drawing.Graphics.DrawEllipse%2A>使用<xref:System.Drawing.Pen>对象中要绘制带纹理的椭圆。  
  
 下图显示位图和带纹理的椭圆。  
  
 ![钢笔](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。 前面将代码粘贴到<xref:System.Windows.Forms.Control.Paint>事件处理程序。 替换`Texture.jpg`你系统上有效的映像。  
  
## <a name="see-also"></a>请参阅  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
