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
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947822"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>如何：在绘制的文本中设置制表位
<xref:System.Drawing.StringFormat.SetTabStops%2A>可以通过调用<xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.StringFormat>对象的方法, 然后将该对象传递给类的方法, 为文本设置制表位。 <xref:System.Drawing.StringFormat>  
  
> [!NOTE]
> 虽然您可以<xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType>使用标志展开现有制表位, 但不支持向绘制文本添加制表位。 <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>  
  
## <a name="example"></a>示例  
 下面的示例将制表位设置为150、250和350。 然后, 该代码显示名称和测试分数的选项卡式列表。  
  
 下图显示了选项卡式文本:  
  
 ![显示姓名和分数的选项卡式列表的屏幕截图。](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 下面的代码将两个参数传递<xref:System.Drawing.StringFormat.SetTabStops%2A>给方法。 第二个参数是包含制表符偏移量的数组。 传递给<xref:System.Drawing.StringFormat.SetTabStops%2A>的第一个参数为 0, 指示数组中的第一个偏移量是从位置 0 (边框的左边缘) 度量的。  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
- 前面的示例旨在与 Windows 窗体一起使用, 并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`, <xref:System.Windows.Forms.PaintEventHandler>这是的参数。  
  
## <a name="see-also"></a>请参阅

- [使用字体和文本](using-fonts-and-text.md)
- [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)
