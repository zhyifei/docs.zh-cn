---
title: 如何：手动管理缓冲的图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968602"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>如何：手动管理缓冲的图形
对于更高级的双缓冲方案, 可以使用 .NET Framework 类实现自己的双缓冲逻辑。 负责分配和管理单个图形缓冲区的类是<xref:System.Drawing.BufferedGraphicsContext>类。 每个应用程序都有<xref:System.Drawing.BufferedGraphicsContext>自己的默认设置, 它管理该应用程序的所有默认双缓冲。 可以通过调用<xref:System.Drawing.BufferedGraphicsManager.Current%2A>来检索对此实例的引用。  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>获取对默认 BufferedGraphicsContext 的引用  
  
- <xref:System.Drawing.BufferedGraphicsManager.Current%2A>设置属性, 如下面的代码示例中所示。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > 不需要对从`Dispose` <xref:System.Drawing.BufferedGraphicsManager>类接收的<xref:System.Drawing.BufferedGraphicsContext>引用调用方法。 <xref:System.Drawing.BufferedGraphicsManager>处理默认<xref:System.Drawing.BufferedGraphicsContext>实例的所有内存分配和分配。  
  
     对于具有动画效果的图形密集型应用程序, 有时可以使用专用<xref:System.Drawing.BufferedGraphicsContext>而不是<xref:System.Drawing.BufferedGraphicsContext>提供<xref:System.Drawing.BufferedGraphicsManager>的来提高性能。 这使您可以单独创建和管理图形缓冲区, 而不会产生管理与应用程序关联的所有其他缓冲图形的性能开销, 但应用程序使用的内存也将更大。  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>创建专用 BufferedGraphicsContext  
  
- 声明并创建<xref:System.Drawing.BufferedGraphicsContext>类的新实例, 如以下代码示例中所示。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Drawing.BufferedGraphicsContext>
- [双缓冲的图形](double-buffered-graphics.md)
- [如何：手动渲染缓冲图形](how-to-manually-render-buffered-graphics.md)
