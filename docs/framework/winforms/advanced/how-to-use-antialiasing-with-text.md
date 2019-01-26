---
title: 如何：对文本使用抗锯齿效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 64b1c27b9e8b7d405dde5add105ff2e682f8ad87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534093"
---
# <a name="how-to-use-antialiasing-with-text"></a>如何：对文本使用抗锯齿效果
*抗锯齿*指进行绘制的图形和文本，以提高它们的外观或可读性的锯齿状边缘平滑处理。 与托管[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类，您可以呈现高质量消除锯齿的文本，以及较低质量的文本。 通常情况下，更高质量呈现花费的处理时间超过较低质量呈现。 若要设置的文本质量级别，设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>的属性<xref:System.Drawing.Graphics>的元素之一<xref:System.Drawing.Text.TextRenderingHint>枚举  
  
## <a name="example"></a>示例  
 下面的代码示例绘制了两种不同的质量设置的文本。  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 下图显示了示例代码的输出：  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例设计为使用 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅
- [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
