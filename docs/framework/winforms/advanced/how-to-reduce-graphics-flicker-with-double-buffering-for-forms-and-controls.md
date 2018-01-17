---
title: "如何：通过对窗体和控件使用双缓冲来减少图形闪烁"
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
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc782ba262527a319cbb05cc6d36ca568afc55c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>如何：通过对窗体和控件使用双缓冲来减少图形闪烁
双缓冲使用内容缓冲来解决与多个画图操作相关的闪烁问题。 启用双缓冲后，所有画图操作会首先呈现到内存缓冲而不是屏幕上的绘图图面。 所有画图操作完成后，内存缓冲会直接复制到与之关联的绘图图面。 由于在屏幕上，执行只有一个图形操作消除了复杂的绘制操作相关联的图形闪烁。对于大多数应用程序，默认双缓冲提供的[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]将提供最佳结果。 标准 Windows 窗体控件都是双缓冲默认情况下。 你可以启用默认双缓冲你窗体中并编写两种方式的控件。 你可以设置<xref:System.Windows.Forms.Control.DoubleBuffered%2A>属性`true`，也可以调用<xref:System.Windows.Forms.Control.SetStyle%2A>方法以设置<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>标志切换为`true`。 这两种方法将启用默认双缓冲窗体或控件，并提供无闪烁的图形呈现。 调用<xref:System.Windows.Forms.Control.SetStyle%2A>方法建议仅对具有为其编写呈现的所有代码的自定义控件。  
  
 对于更高级的双缓冲方案，例如动画或高级的内存管理，你可以实现你自己的双缓冲逻辑。 有关详细信息，请参阅[如何： 手动管理缓冲图形](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)。  
  
### <a name="to-reduce-flicker"></a>若要减少闪烁  
  
-   将 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 属性设置为 `true`。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- 或 -  
  
-   调用<xref:System.Windows.Forms.Control.SetStyle%2A>方法以设置<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>标志切换为`true`。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [双缓冲的图形](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
