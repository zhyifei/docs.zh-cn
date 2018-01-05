---
title: "教程：在 Win32 应用程序中承载 Visual 对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 753e55e644a9edea90a0a034ba2930473ef53f61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>教程：在 Win32 应用程序中承载 Visual 对象
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当你有大量的投资[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]代码，它可能更有效地添加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到你的应用程序的功能而不是重写代码。 为提供支持[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]图形子系统的应用程序，以并发方式使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供用于承载中的对象的机制[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口。  
  
 本教程介绍如何编写的示例应用，[命中测试的 Win32 间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=159995)，则该主机[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中的 visual 对象[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口。  
  

  
<a name="requirements"></a>   
## <a name="requirements"></a>惠?  
 本教程假定你已基本熟悉 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 编程。 有关的基本介绍[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。 有关的简介[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]编程，请参阅任何大量的丛书有关该主题中，尤其是*编程 Windows* Charles Petzold 通过。  
  
> [!NOTE]
>  本教程包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 有关完整的示例代码，请参阅[命中测试的 Win32 间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=159995)。  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>创建宿主 Win32 窗口  
 承载的关键[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中的对象[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口<xref:System.Windows.Interop.HwndSource>类。 此类将包装[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中的对象[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口中，从而使它们可以合并到你[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]用作子窗口。  
  
 下面的示例演示用于创建的代码<xref:System.Windows.Interop.HwndSource>对象作为[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]视觉对象的容器窗口。 若要设置窗口样式、 位置和其他参数[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口中，使用<xref:System.Windows.Interop.HwndSourceParameters>对象。  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  值<xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A>属性不能设置为 WS_EX_TRANSPARENT。 这意味着，主机[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口不能是透明。 因此，主机的背景色[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口设置为其父窗口与相同的背景颜色。  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>将视觉对象添加到宿主 Win32 窗口  
 创建主机后[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]容器窗口为视觉对象，你可以向其添加视觉对象。 你将想要确保视觉对象，例如动画，任何转换不会超出边界的主机[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口的边框。  
  
 下面的示例演示用于创建的代码<xref:System.Windows.Interop.HwndSource>对象并向其中添加视觉对象。  
  
> [!NOTE]
>  <xref:System.Windows.Interop.HwndSource.RootVisual%2A>属性<xref:System.Windows.Interop.HwndSource>对象设置为向主机添加的第一个视觉对象[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口。 根视觉对象定义视觉对象树最顶层的节点。 任何后续的视觉对象添加到主机[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口添加为子对象。  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>实现 Win32 消息筛选器  
 主机[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口视觉对象需要窗口消息筛选器过程，以处理从应用程序队列发送到窗口的消息。 窗口过程接收消息从[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]系统。 这些消息可以是输入消息，也可以是窗口管理消息。 可以选择在窗口过程中处理一条消息，或将消息传递到系统以供默认处理。  
  
 <xref:System.Windows.Interop.HwndSource>定义为视觉对象的父级必须引用你提供的窗口消息筛选器过程的对象。 当你创建<xref:System.Windows.Interop.HwndSource>对象，设置<xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A>属性来引用窗口过程。  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 下面的示例演示用于处理释放鼠标左键和右键消息的代码。 鼠标的坐标值命中位置中的值包含`lParam`参数。  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>处理 Win32 消息  
 在下面的示例代码演示如何对主机中包含的视觉对象的层次结构执行命中的测试[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口。 你可以确定点是否处于的视觉对象的几何图形之内使用<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法，以指定的根视觉对象和要命中测试的坐标值。 在这种情况下，根视觉对象是值<xref:System.Windows.Interop.HwndSource.RootVisual%2A>属性<xref:System.Windows.Interop.HwndSource>对象。  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 有关对视觉对象进行命中测试的详细信息，请参阅[命中测试可视层中](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Interop.HwndSource>  
 [使用互操作的 Win32 示例命中测试](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [可视化层中的命中测试](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
