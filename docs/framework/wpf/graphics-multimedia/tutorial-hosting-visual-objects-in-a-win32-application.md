---
title: 教程：在 Win32 应用程序中承载 Visual 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: d04357e0770bbf8eebe8f40a86a19ddc9baae3ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187429"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a><span data-ttu-id="66262-102">教程：在 Win32 应用程序中承载 Visual 对象</span><span class="sxs-lookup"><span data-stu-id="66262-102">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="66262-103">提供了用于创建应用程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="66262-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="66262-104">但是，当您对 Win32 代码进行大量投资时，向应用程序添加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]功能而不是重写代码可能更有效。</span><span class="sxs-lookup"><span data-stu-id="66262-104">However, when you have a substantial investment in Win32 code, it might be more effective to add [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] functionality to your application rather than rewrite your code.</span></span> <span data-ttu-id="66262-105">要支持应用程序中同时使用的 Win32 和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]图形子系统，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]请提供一种在 Win32 窗口中托管对象的机制。</span><span class="sxs-lookup"><span data-stu-id="66262-105">To provide support for Win32 and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics subsystems used concurrently in an application, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a mechanism for hosting objects in a Win32 window.</span></span>  
  
 <span data-ttu-id="66262-106">本教程介绍如何编写示例应用程序，[即使用 Win32 互操作示例进行命中测试](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)，该[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]示例在 Win32 窗口中承载可视对象。</span><span class="sxs-lookup"><span data-stu-id="66262-106">This tutorial describes how to write a sample application, [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting), that hosts [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual objects in a Win32 window.</span></span>  

<a name="requirements"></a>
## <a name="requirements"></a><span data-ttu-id="66262-107">要求</span><span class="sxs-lookup"><span data-stu-id="66262-107">Requirements</span></span>  
 <span data-ttu-id="66262-108">本教程假定对 Win32[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程和 Win32 编程基本熟悉。</span><span class="sxs-lookup"><span data-stu-id="66262-108">This tutorial assumes a basic familiarity with both [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and Win32 programming.</span></span> <span data-ttu-id="66262-109">有关[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程的基本介绍，请参阅[演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="66262-109">For a basic introduction to [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] programming, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span> <span data-ttu-id="66262-110">有关 Win32 编程的介绍，请参阅有关该主题的众多书籍中的任何一本书，特别是查尔斯·佩佐德的*编程 Windows。*</span><span class="sxs-lookup"><span data-stu-id="66262-110">For an introduction to Win32 programming, see any of the numerous books on the subject, in particular *Programming Windows* by Charles Petzold.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66262-111">本教程包括来自相关示例的一些代码示例。</span><span class="sxs-lookup"><span data-stu-id="66262-111">This tutorial includes a number of code examples from the associated sample.</span></span> <span data-ttu-id="66262-112">但是，出于可读性考虑，不包括完整的示例代码。</span><span class="sxs-lookup"><span data-stu-id="66262-112">However, for readability, it does not include the complete sample code.</span></span> <span data-ttu-id="66262-113">有关完整的示例代码，请参阅[使用 Win32 互操作示例进行命中测试](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)。</span><span class="sxs-lookup"><span data-stu-id="66262-113">For the complete sample code, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a><span data-ttu-id="66262-114">创建宿主 Win32 窗口</span><span class="sxs-lookup"><span data-stu-id="66262-114">Creating the Host Win32 Window</span></span>  
 <span data-ttu-id="66262-115">在 Win32 窗口中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]对象的关键是<xref:System.Windows.Interop.HwndSource>类。</span><span class="sxs-lookup"><span data-stu-id="66262-115">The key to hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objects in a Win32 window is the <xref:System.Windows.Interop.HwndSource> class.</span></span> <span data-ttu-id="66262-116">此类将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]对象包装在 Win32 窗口中，允许将它们作为子窗口合并到您的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]窗口中。</span><span class="sxs-lookup"><span data-stu-id="66262-116">This class wraps the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objects in a Win32 window, allowing them to be incorporated into your [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] as a child window.</span></span>  
  
 <span data-ttu-id="66262-117">下面的示例显示了将<xref:System.Windows.Interop.HwndSource>对象创建为可视对象的 Win32 容器窗口的代码。</span><span class="sxs-lookup"><span data-stu-id="66262-117">The following example shows the code for creating the <xref:System.Windows.Interop.HwndSource> object as the Win32 container window for the visual objects.</span></span> <span data-ttu-id="66262-118">要设置 Win32 窗口的窗口样式、位置和其他参数，请使用 该<xref:System.Windows.Interop.HwndSourceParameters>对象。</span><span class="sxs-lookup"><span data-stu-id="66262-118">To set the window style, position, and other parameters for the Win32 window, use the <xref:System.Windows.Interop.HwndSourceParameters> object.</span></span>  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> <span data-ttu-id="66262-119">属性的值<xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A>不能设置为WS_EX_TRANSPARENT。</span><span class="sxs-lookup"><span data-stu-id="66262-119">The value of the <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> property cannot be set to WS_EX_TRANSPARENT.</span></span> <span data-ttu-id="66262-120">这意味着主机 Win32 窗口不能透明。</span><span class="sxs-lookup"><span data-stu-id="66262-120">This means that the host Win32 window cannot be transparent.</span></span> <span data-ttu-id="66262-121">因此，主机 Win32 窗口的背景颜色设置为与其父窗口相同的背景颜色。</span><span class="sxs-lookup"><span data-stu-id="66262-121">For this reason, the background color of the host Win32 window is set to the same background color as its parent window.</span></span>  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a><span data-ttu-id="66262-122">将视觉对象添加到宿主 Win32 窗口</span><span class="sxs-lookup"><span data-stu-id="66262-122">Adding Visual Objects to the Host Win32 Window</span></span>  
 <span data-ttu-id="66262-123">为可视对象创建主机 Win32 容器窗口后，可以向其添加可视对象。</span><span class="sxs-lookup"><span data-stu-id="66262-123">Once you have created a host Win32 container window for the visual objects, you can add visual objects to it.</span></span> <span data-ttu-id="66262-124">您需要确保视觉对象的任何转换（如动画）不会超出主机 Win32 窗口的边界矩形的边界范围。</span><span class="sxs-lookup"><span data-stu-id="66262-124">You will want to ensure that any transformations of the visual objects, such as animations, do not extend beyond the bounds of the host Win32 window's bounding rectangle.</span></span>  
  
 <span data-ttu-id="66262-125">下面的示例显示了用于创建<xref:System.Windows.Interop.HwndSource>对象和向对象添加可视对象的代码。</span><span class="sxs-lookup"><span data-stu-id="66262-125">The following example shows the code for creating the <xref:System.Windows.Interop.HwndSource> object and adding visual objects to it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66262-126"><xref:System.Windows.Interop.HwndSource>对象<xref:System.Windows.Interop.HwndSource.RootVisual%2A>的属性设置为添加到主机 Win32 窗口的第一个可视对象。</span><span class="sxs-lookup"><span data-stu-id="66262-126">The <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object is set to the first visual object added to the host Win32 window.</span></span> <span data-ttu-id="66262-127">根视觉对象定义视觉对象树最顶层的节点。</span><span class="sxs-lookup"><span data-stu-id="66262-127">The root visual object defines the top-most node of the visual object tree.</span></span> <span data-ttu-id="66262-128">添加到主机 Win32 窗口的任何后续可视对象都添加为子对象。</span><span class="sxs-lookup"><span data-stu-id="66262-128">Any subsequent visual objects added to the host Win32 window are added as child objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a><span data-ttu-id="66262-129">实现 Win32 消息筛选器</span><span class="sxs-lookup"><span data-stu-id="66262-129">Implementing the Win32 Message Filter</span></span>  
 <span data-ttu-id="66262-130">视觉对象的主机 Win32 窗口需要窗口消息筛选器过程来处理从应用程序队列发送到窗口的消息。</span><span class="sxs-lookup"><span data-stu-id="66262-130">The host Win32 window for the visual objects requires a window message filter procedure to handle messages that are sent to the window from the application queue.</span></span> <span data-ttu-id="66262-131">窗口过程接收来自 Win32 系统的消息。</span><span class="sxs-lookup"><span data-stu-id="66262-131">The window procedure receives messages from the Win32 system.</span></span> <span data-ttu-id="66262-132">这些消息可以是输入消息，也可以是窗口管理消息。</span><span class="sxs-lookup"><span data-stu-id="66262-132">These may be input messages or window-management messages.</span></span> <span data-ttu-id="66262-133">可以选择在窗口过程中处理一条消息，或将消息传递到系统以供默认处理。</span><span class="sxs-lookup"><span data-stu-id="66262-133">You can optionally handle a message in your window procedure or pass the message to the system for default processing.</span></span>  
  
 <span data-ttu-id="66262-134">您<xref:System.Windows.Interop.HwndSource>定义为可视对象的父对象必须引用您提供的窗口消息筛选器过程。</span><span class="sxs-lookup"><span data-stu-id="66262-134">The <xref:System.Windows.Interop.HwndSource> object that you defined as the parent for the visual objects must reference the window message filter procedure you provide.</span></span> <span data-ttu-id="66262-135">创建对象时，<xref:System.Windows.Interop.HwndSource>将<xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A>属性设置为引用窗口过程。</span><span class="sxs-lookup"><span data-stu-id="66262-135">When you create the <xref:System.Windows.Interop.HwndSource> object, set the <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> property to reference the window procedure.</span></span>  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 <span data-ttu-id="66262-136">下面的示例演示用于处理释放鼠标左键和右键消息的代码。</span><span class="sxs-lookup"><span data-stu-id="66262-136">The following example shows the code for handling the left and right mouse button up messages.</span></span> <span data-ttu-id="66262-137">鼠标命中位置的坐标值包含在`lParam`参数的值中。</span><span class="sxs-lookup"><span data-stu-id="66262-137">The coordinate value of the mouse hit position is contained in the value of the `lParam` parameter.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a><span data-ttu-id="66262-138">处理 Win32 消息</span><span class="sxs-lookup"><span data-stu-id="66262-138">Processing the Win32 Messages</span></span>  
 <span data-ttu-id="66262-139">以下示例中的代码显示如何针对主机 Win32 窗口中中包含的可视对象的层次结构执行命中测试。</span><span class="sxs-lookup"><span data-stu-id="66262-139">The code in the following example shows how a hit test is performed against the hierarchy of visual objects contained in the host Win32 window.</span></span> <span data-ttu-id="66262-140">通过使用<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法指定根可视对象和要命中测试的坐标值，可以识别点是否位于可视对象的几何体内。</span><span class="sxs-lookup"><span data-stu-id="66262-140">You can identify whether a point is within the geometry of a visual object, by using the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to specify the root visual object and the coordinate value to hit test against.</span></span> <span data-ttu-id="66262-141">在这种情况下，根可视对象是<xref:System.Windows.Interop.HwndSource.RootVisual%2A><xref:System.Windows.Interop.HwndSource>对象属性的值。</span><span class="sxs-lookup"><span data-stu-id="66262-141">In this case, the root visual object is the value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="66262-142">有关针对可视对象进行命中测试的详细信息，请参阅[可视化图层中的命中测试](hit-testing-in-the-visual-layer.md)。</span><span class="sxs-lookup"><span data-stu-id="66262-142">For more information on hit testing against visual objects, see [Hit Testing in the Visual Layer](hit-testing-in-the-visual-layer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66262-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66262-143">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="66262-144">使用 Win32 互操作进行命中测试示例</span><span class="sxs-lookup"><span data-stu-id="66262-144">Hit Test with Win32 Interoperation Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [<span data-ttu-id="66262-145">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="66262-145">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
