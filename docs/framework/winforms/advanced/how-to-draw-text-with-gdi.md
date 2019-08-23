---
title: 如何：用 GDI 绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956543"
---
# <a name="how-to-draw-text-with-gdi"></a>如何：用 GDI 绘制文本
使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A> 类<xref:System.Windows.Forms.TextRenderer>中的方法, 可以访问用于在窗体或控件上绘制文本的 GDI 功能。 GDI 文本呈现通常提供比 GDI + 更好的性能和更准确的文本度量。  
  
> [!NOTE]
> <xref:System.Windows.Forms.TextRenderer>类的<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法不支持打印。 打印时, 请始终使用<xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics>类的方法。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法在一个矩形内的多行上绘制文本。  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 若要使用<xref:System.Windows.Forms.TextRenderer>类呈现文本, <xref:System.Drawing.IDeviceContext>需要一个, <xref:System.Drawing.Font>如<xref:System.Drawing.Graphics>和, 一个用于绘制文本的位置以及应在其中绘制文本的颜色。 (可选) 可以使用<xref:System.Windows.Forms.TextFormatFlags>枚举指定文本格式。  
  
 有关获取的<xref:System.Drawing.Graphics>详细信息, 请参阅[如何:为绘图](how-to-create-graphics-objects-for-drawing.md)创建图形对象。 有关构造的<xref:System.Drawing.Font>详细信息, 请参阅[如何:构造字体系列和字体](how-to-construct-font-families-and-fonts.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例旨在与 Windows 窗体一起使用, 并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`(参数<xref:System.Windows.Forms.PaintEventHandler>)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [使用字体和文本](using-fonts-and-text.md)
