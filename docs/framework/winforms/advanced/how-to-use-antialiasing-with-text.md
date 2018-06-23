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
ms.openlocfilehash: 2adb33e3d05e38ee71be8a12cdc2e20dc8c55c72
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338125"
---
# <a name="how-to-use-antialiasing-with-text"></a>如何：对文本使用抗锯齿效果
*抗锯齿*指的是平滑的粗糙边缘绘制的图形和文本，以提高其外观或可读性。 通过托管[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类，可以呈现高质量消除锯齿的文本，以及较低质量的文本。 通常情况下，呈现的质量越高采用更多的处理时间比较低质量呈现。 若要设置的文本质量级别，设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性<xref:System.Drawing.Graphics>到的元素之一<xref:System.Drawing.Text.TextRenderingHint>枚举  
  
## <a name="example"></a>示例  
 下面的代码示例绘制了两种不同的质量设置的文本。  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 下图显示示例代码的输出：  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
