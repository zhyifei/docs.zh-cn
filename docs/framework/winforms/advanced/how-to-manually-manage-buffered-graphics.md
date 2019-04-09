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
ms.openlocfilehash: 965e3225f8cf1af6d61b81434089ebacac8ad13a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138666"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="aedb7-102">如何：手动管理缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="aedb7-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="aedb7-103">对于更高级的双缓冲方案，可以使用[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]类以实现您自己的双缓冲逻辑。</span><span class="sxs-lookup"><span data-stu-id="aedb7-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="aedb7-104">负责分配和管理各个图形缓冲的类是<xref:System.Drawing.BufferedGraphicsContext>类。</span><span class="sxs-lookup"><span data-stu-id="aedb7-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="aedb7-105">每个应用程序具有自己的默认<xref:System.Drawing.BufferedGraphicsContext>管理所有默认双缓冲该应用程序。</span><span class="sxs-lookup"><span data-stu-id="aedb7-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="aedb7-106">可以通过调用检索到此实例的引用<xref:System.Drawing.BufferedGraphicsManager.Current%2A>。</span><span class="sxs-lookup"><span data-stu-id="aedb7-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="aedb7-107">若要获取对默认 BufferedGraphicsContext 的引用</span><span class="sxs-lookup"><span data-stu-id="aedb7-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="aedb7-108">设置<xref:System.Drawing.BufferedGraphicsManager.Current%2A>属性，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="aedb7-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="aedb7-109">不需要调用`Dispose`方法<xref:System.Drawing.BufferedGraphicsContext>引用接收来自<xref:System.Drawing.BufferedGraphicsManager>类。</span><span class="sxs-lookup"><span data-stu-id="aedb7-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="aedb7-110"><xref:System.Drawing.BufferedGraphicsManager>处理的所有内存分配和默认值的分布<xref:System.Drawing.BufferedGraphicsContext>实例。</span><span class="sxs-lookup"><span data-stu-id="aedb7-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="aedb7-111">如动画图形密集型应用程序，您有时可以提高性能使用的专用<xref:System.Drawing.BufferedGraphicsContext>而不是<xref:System.Drawing.BufferedGraphicsContext>提供的<xref:System.Drawing.BufferedGraphicsManager>。</span><span class="sxs-lookup"><span data-stu-id="aedb7-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="aedb7-112">这使您可以创建和管理图形缓冲区单独，而不会产生管理所有其他缓冲的图形与应用程序关联，但应用程序所占用的内存将更大的性能开销。</span><span class="sxs-lookup"><span data-stu-id="aedb7-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="aedb7-113">若要创建专用的 BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="aedb7-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="aedb7-114">声明和创建的新实例<xref:System.Drawing.BufferedGraphicsContext>类，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="aedb7-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="aedb7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="aedb7-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="aedb7-116">双缓冲图形</span><span class="sxs-lookup"><span data-stu-id="aedb7-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="aedb7-117">如何：手动呈现缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="aedb7-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
