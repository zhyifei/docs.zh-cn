---
title: 如何：在绘制的文本中设置制表位
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 4bf9328b63be88f487995f7b9691683167271c46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635801"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>如何：在绘制的文本中设置制表位
可以通过调用设置文本的所有制表位<xref:System.Drawing.StringFormat.SetTabStops%2A>方法<xref:System.Drawing.StringFormat>对象，然后将其传递<xref:System.Drawing.StringFormat>对象传递给<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>不支持添加制表位与绘制的文本，尽管您可以扩展现有选项卡会停止使用的作用<xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType>标志。  
  
## <a name="example"></a>示例  
 下面的示例在 150、 250 和 350 设置制表位。 然后，代码显示选项卡式的列表的名称和测试分数。  
  
 下图显示的选项卡式的文本。  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 以下代码将传递到两个参数<xref:System.Drawing.StringFormat.SetTabStops%2A>方法。 第二个参数是一个数组，包含制表位偏移量。 第一个参数传递给<xref:System.Drawing.StringFormat.SetTabStops%2A>为 0，指示数组中的第一个偏移量从边界的矩形的左边缘的位置 0，来度量。  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。  
  
## <a name="see-also"></a>请参阅
- [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [如何：用 GDI 绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
