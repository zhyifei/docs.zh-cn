---
title: 如何：绘制填充有纹理的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004273"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>如何：绘制填充有纹理的线条
而不是绘制一条线使用纯色，可以绘制用纹理的行。 若要绘制的直线和曲线与纹理，创建<xref:System.Drawing.TextureBrush>对象，并将其传递<xref:System.Drawing.TextureBrush>对象传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数。 使用纹理画笔相关联的位图用于平铺平面 （不可见的方式），并且触笔的笔划时笔绘制直线或曲线，寻找特定的像素的平铺纹理。  
  
## <a name="example"></a>示例  
 下面的示例创建<xref:System.Drawing.Bitmap>文件中的对象`Texture1.jpg`。 该位图用于构造<xref:System.Drawing.TextureBrush>对象，并<xref:System.Drawing.TextureBrush>对象用来构造<xref:System.Drawing.Pen>对象。 对调用<xref:System.Drawing.Graphics.DrawImage%2A>绘制位图，其左上角位于 （0，0）。 在调用<xref:System.Drawing.Graphics.DrawEllipse%2A>使用<xref:System.Drawing.Pen>对象来绘制带纹理的椭圆。  
  
 下图显示了位图和带纹理的椭圆：  
  
 ![显示位图和带纹理的椭圆的屏幕截图。](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。 前面将代码粘贴到<xref:System.Windows.Forms.Control.Paint>事件处理程序。 替换为`Texture.jpg`你系统上有效的映像。  
  
## <a name="see-also"></a>请参阅

- [使用笔绘制直线和形状](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
