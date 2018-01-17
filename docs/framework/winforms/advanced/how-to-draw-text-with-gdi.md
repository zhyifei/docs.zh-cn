---
title: "如何：用 GDI 绘制文本"
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
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6c7fb4d8c6bd93481935a9f2ef7dd4b34af7e71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-with-gdi"></a>如何：用 GDI 绘制文本
与<xref:System.Windows.Forms.TextRenderer.DrawText%2A>中的方法<xref:System.Windows.Forms.TextRenderer>类，可以访问[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]在窗体或控件上绘制文本的功能。 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]文本呈现通常提供更好的性能和更准确的文本比测量[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法<xref:System.Windows.Forms.TextRenderer>不支持打印的类。 打印时，始终使用<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何在矩形使用中的多个行上绘制文本<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法。  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 呈现与文本<xref:System.Windows.Forms.TextRenderer>类，你需要<xref:System.Drawing.IDeviceContext>，如<xref:System.Drawing.Graphics>和<xref:System.Drawing.Font>，用于绘制文本，并在其中应绘制的颜色的位置。 或者，可以指定文本格式使用<xref:System.Windows.Forms.TextFormatFlags>枚举。  
  
 有关获取详细信息<xref:System.Drawing.Graphics>，请参阅[如何： 创建图形对象的绘图](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)。 有关构造<xref:System.Drawing.Font>，请参阅[如何： 构造字体系列和字体](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
