---
title: "如何：对文本使用抗锯齿效果"
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
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb5a57f8bcbdc1edad78dcd48ad495a187bbb44a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a>如何：对文本使用抗锯齿效果
*抗锯齿*指的是平滑的粗糙边缘绘制的图形和文本，以提高其外观或可读性。 通过托管[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类，可以呈现高质量消除锯齿的文本，以及较低质量的文本。 通常情况下，呈现的质量越高采用更多的处理时间比较低质量呈现。 若要设置的文本质量级别，设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性<xref:System.Drawing.Graphics>到的元素之一<xref:System.Drawing.Text.TextRenderingHint>枚举  
  
## <a name="example"></a>示例  
 下面的代码示例绘制了两种不同的质量设置的文本。  
  
 下图显示 cod 的输出示例代码。  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>另请参阅  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
