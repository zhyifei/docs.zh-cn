---
title: "如何：手动管理缓冲图形"
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
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f545cf4689a2c8058e77f4b4721788ffb0e7247
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a>如何：手动管理缓冲图形
对于更高级的双缓冲方案，你可以使用[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]类来实现您自己双缓冲的逻辑。 类负责分配和管理各自的图形缓冲区是<xref:System.Drawing.BufferedGraphicsContext>类。 每个应用程序具有自己的默认<xref:System.Drawing.BufferedGraphicsContext>，管理所有默认双缓冲为该应用程序。 你可以通过调用检索到此实例的引用<xref:System.Drawing.BufferedGraphicsManager.Current%2A>。  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>若要获取对默认 BufferedGraphicsContext 的引用  
  
-   设置<xref:System.Drawing.BufferedGraphicsManager.Current%2A>属性，如下面的代码示例中所示。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  不需要调用`Dispose`方法<xref:System.Drawing.BufferedGraphicsContext>收到的引用<xref:System.Drawing.BufferedGraphicsManager>类。 <xref:System.Drawing.BufferedGraphicsManager>处理所有的内存分配和默认分发<xref:System.Drawing.BufferedGraphicsContext>实例。  
  
     对于如动画的图形密集型应用程序，你有时可以提高性能通过使用专用<xref:System.Drawing.BufferedGraphicsContext>而不是<xref:System.Drawing.BufferedGraphicsContext>由<xref:System.Drawing.BufferedGraphicsManager>。 这使您可以创建和管理图形缓冲区单独进行，而不会导致管理所有其他缓冲的图形与你的应用程序，但应用程序占用的内存将更大的性能开销。  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>若要创建专用的 BufferedGraphicsContext  
  
-   声明和创建的新实例<xref:System.Drawing.BufferedGraphicsContext>类，如下面的代码示例中所示。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [双缓冲的图形](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [如何：手动呈现缓冲的图形](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
