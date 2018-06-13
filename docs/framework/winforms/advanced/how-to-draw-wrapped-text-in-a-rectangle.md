---
title: 如何：在矩形中绘制换行文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524968"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>如何：在矩形中绘制换行文本
你可以在矩形中绘制换行的文本，通过使用<xref:System.Drawing.Graphics.DrawString%2A>重载的方法的<xref:System.Drawing.Graphics>采用类<xref:System.Drawing.Rectangle>或<xref:System.Drawing.RectangleF>参数。 你还将使用<xref:System.Drawing.Brush>和<xref:System.Drawing.Font>。  
  
 您还可以绘制换行的文本矩形内使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载的方法的<xref:System.Windows.Forms.TextRenderer>采用<xref:System.Drawing.Rectangle>和<xref:System.Windows.Forms.TextFormatFlags>参数。 你还将使用<xref:System.Drawing.Color>和<xref:System.Drawing.Font>。  
  
 下图显示当你使用在矩形中绘制的文本的输出<xref:System.Drawing.Graphics.DrawString%2A>方法。  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>绘制换行文本中使用 GDI + 矩形  
  
1.  使用<xref:System.Drawing.Graphics.DrawString%2A>重载方法，并传递所需的文本<xref:System.Drawing.Rectangle>或<xref:System.Drawing.RectangleF>，<xref:System.Drawing.Font>和<xref:System.Drawing.Brush>。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>绘制换行文本中使用 GDI 矩形  
  
1.  使用<xref:System.Windows.Forms.TextFormatFlags>枚举值，以指定的文本应与包装<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载方法，并传递所需的文本<xref:System.Drawing.Rectangle>，<xref:System.Drawing.Font>和<xref:System.Drawing.Color>。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例需要：  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 [如何：用 GDI 绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [如何：构造字体系列和字体](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [如何：在指定位置绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
