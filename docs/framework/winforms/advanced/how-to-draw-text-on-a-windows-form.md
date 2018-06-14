---
title: 如何：在 Windows 窗体上绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: 9369a4ed26107bdc395d455ba6fb8420fd895d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524779"
---
# <a name="how-to-draw-text-on-a-windows-form"></a>如何：在 Windows 窗体上绘制文本
下面的代码示例演示如何使用<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>窗体上绘制文本。 或者，可以使用<xref:System.Windows.Forms.TextRenderer>窗体上绘制文本。 有关详细信息，请参阅[如何： 用 GDI 绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>编译代码  
 不能调用<xref:System.Drawing.Graphics.DrawString%2A>中的方法<xref:System.Windows.Forms.Form.Load>事件处理程序。 不会重新绘制的内容的绘制，如果窗体调整大小或另一种形式被遮盖。 若要使你自动重绘的内容，则应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。  
  
## <a name="robust-programming"></a>可靠编程  
 以下情况可能会导致异常：  
  
-   未安装 Arial 字体。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [图形编程入门](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [如何：用 GDI 绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
