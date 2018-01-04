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
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="73074-102">如何：通过对窗体和控件使用双缓冲来减少图形闪烁</span><span class="sxs-lookup"><span data-stu-id="73074-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="73074-103">双缓冲使用内容缓冲来解决与多个画图操作相关的闪烁问题。</span><span class="sxs-lookup"><span data-stu-id="73074-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="73074-104">启用双缓冲后，所有画图操作会首先呈现到内存缓冲而不是屏幕上的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="73074-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="73074-105">所有画图操作完成后，内存缓冲会直接复制到与之关联的绘图图面。</span><span class="sxs-lookup"><span data-stu-id="73074-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="73074-106">由于在屏幕上，执行只有一个图形操作消除了复杂的绘制操作相关联的图形闪烁。对于大多数应用程序，默认双缓冲提供的[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]将提供最佳结果。</span><span class="sxs-lookup"><span data-stu-id="73074-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="73074-107">标准 Windows 窗体控件都是双缓冲默认情况下。</span><span class="sxs-lookup"><span data-stu-id="73074-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="73074-108">你可以启用默认双缓冲你窗体中并编写两种方式的控件。</span><span class="sxs-lookup"><span data-stu-id="73074-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="73074-109">你可以设置<xref:System.Windows.Forms.Control.DoubleBuffered%2A>属性`true`，也可以调用<xref:System.Windows.Forms.Control.SetStyle%2A>方法以设置<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>标志切换为`true`。</span><span class="sxs-lookup"><span data-stu-id="73074-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="73074-110">这两种方法将启用默认双缓冲窗体或控件，并提供无闪烁的图形呈现。</span><span class="sxs-lookup"><span data-stu-id="73074-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="73074-111">调用<xref:System.Windows.Forms.Control.SetStyle%2A>方法建议仅对具有为其编写呈现的所有代码的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="73074-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="73074-112">对于更高级的双缓冲方案，例如动画或高级的内存管理，你可以实现你自己的双缓冲逻辑。</span><span class="sxs-lookup"><span data-stu-id="73074-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="73074-113">有关详细信息，请参阅[如何： 手动管理缓冲图形](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)。</span><span class="sxs-lookup"><span data-stu-id="73074-113">For more information, see [How to: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="73074-114">若要减少闪烁</span><span class="sxs-lookup"><span data-stu-id="73074-114">To reduce flicker</span></span>  
  
-   <span data-ttu-id="73074-115">将 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="73074-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="73074-116">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="73074-116">\- or -</span></span>  
  
-   <span data-ttu-id="73074-117">调用<xref:System.Windows.Forms.Control.SetStyle%2A>方法以设置<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>标志切换为`true`。</span><span class="sxs-lookup"><span data-stu-id="73074-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="73074-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="73074-118">See Also</span></span>  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [<span data-ttu-id="73074-119">双缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="73074-119">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="73074-120">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="73074-120">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
