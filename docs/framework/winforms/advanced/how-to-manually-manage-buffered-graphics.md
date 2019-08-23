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
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="59a45-102">如何：手动管理缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="59a45-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="59a45-103">对于更高级的双缓冲方案, 可以使用 .NET Framework 类实现自己的双缓冲逻辑。</span><span class="sxs-lookup"><span data-stu-id="59a45-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="59a45-104">负责分配和管理单个图形缓冲区的类是<xref:System.Drawing.BufferedGraphicsContext>类。</span><span class="sxs-lookup"><span data-stu-id="59a45-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="59a45-105">每个应用程序都有<xref:System.Drawing.BufferedGraphicsContext>自己的默认设置, 它管理该应用程序的所有默认双缓冲。</span><span class="sxs-lookup"><span data-stu-id="59a45-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="59a45-106">可以通过调用<xref:System.Drawing.BufferedGraphicsManager.Current%2A>来检索对此实例的引用。</span><span class="sxs-lookup"><span data-stu-id="59a45-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="59a45-107">获取对默认 BufferedGraphicsContext 的引用</span><span class="sxs-lookup"><span data-stu-id="59a45-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="59a45-108"><xref:System.Drawing.BufferedGraphicsManager.Current%2A>设置属性, 如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="59a45-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="59a45-109">不需要对从`Dispose` <xref:System.Drawing.BufferedGraphicsManager>类接收的<xref:System.Drawing.BufferedGraphicsContext>引用调用方法。</span><span class="sxs-lookup"><span data-stu-id="59a45-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="59a45-110"><xref:System.Drawing.BufferedGraphicsManager>处理默认<xref:System.Drawing.BufferedGraphicsContext>实例的所有内存分配和分配。</span><span class="sxs-lookup"><span data-stu-id="59a45-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="59a45-111">对于具有动画效果的图形密集型应用程序, 有时可以使用专用<xref:System.Drawing.BufferedGraphicsContext>而不是<xref:System.Drawing.BufferedGraphicsContext>提供<xref:System.Drawing.BufferedGraphicsManager>的来提高性能。</span><span class="sxs-lookup"><span data-stu-id="59a45-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="59a45-112">这使您可以单独创建和管理图形缓冲区, 而不会产生管理与应用程序关联的所有其他缓冲图形的性能开销, 但应用程序使用的内存也将更大。</span><span class="sxs-lookup"><span data-stu-id="59a45-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="59a45-113">创建专用 BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="59a45-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="59a45-114">声明并创建<xref:System.Drawing.BufferedGraphicsContext>类的新实例, 如以下代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="59a45-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="59a45-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="59a45-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="59a45-116">双缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="59a45-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="59a45-117">如何：手动渲染缓冲图形</span><span class="sxs-lookup"><span data-stu-id="59a45-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
