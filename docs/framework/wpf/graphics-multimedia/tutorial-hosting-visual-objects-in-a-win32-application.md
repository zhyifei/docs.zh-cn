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
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>教程：在 Win32 应用程序中承载 Visual 对象
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当您对 Win32 代码进行大量投资时，向应用程序添加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]功能而不是重写代码可能更有效。 要支持应用程序中同时使用的 Win32 和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]图形子系统，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]请提供一种在 Win32 窗口中托管对象的机制。  
  
 本教程介绍如何编写示例应用程序，[即使用 Win32 互操作示例进行命中测试](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)，该[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]示例在 Win32 窗口中承载可视对象。  

<a name="requirements"></a>
## <a name="requirements"></a>要求  
 本教程假定对 Win32[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程和 Win32 编程基本熟悉。 有关[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]编程的基本介绍，请参阅[演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。 有关 Win32 编程的介绍，请参阅有关该主题的众多书籍中的任何一本书，特别是查尔斯·佩佐德的*编程 Windows。*  
  
> [!NOTE]
> 本教程包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 有关完整的示例代码，请参阅[使用 Win32 互操作示例进行命中测试](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)。  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a>创建宿主 Win32 窗口  
 在 Win32 窗口中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]对象的关键是<xref:System.Windows.Interop.HwndSource>类。 此类将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]对象包装在 Win32 窗口中，允许将它们作为子窗口合并到您的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]窗口中。  
  
 下面的示例显示了将<xref:System.Windows.Interop.HwndSource>对象创建为可视对象的 Win32 容器窗口的代码。 要设置 Win32 窗口的窗口样式、位置和其他参数，请使用 该<xref:System.Windows.Interop.HwndSourceParameters>对象。  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> 属性的值<xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A>不能设置为WS_EX_TRANSPARENT。 这意味着主机 Win32 窗口不能透明。 因此，主机 Win32 窗口的背景颜色设置为与其父窗口相同的背景颜色。  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a>将视觉对象添加到宿主 Win32 窗口  
 为可视对象创建主机 Win32 容器窗口后，可以向其添加可视对象。 您需要确保视觉对象的任何转换（如动画）不会超出主机 Win32 窗口的边界矩形的边界范围。  
  
 下面的示例显示了用于创建<xref:System.Windows.Interop.HwndSource>对象和向对象添加可视对象的代码。  
  
> [!NOTE]
> <xref:System.Windows.Interop.HwndSource>对象<xref:System.Windows.Interop.HwndSource.RootVisual%2A>的属性设置为添加到主机 Win32 窗口的第一个可视对象。 根视觉对象定义视觉对象树最顶层的节点。 添加到主机 Win32 窗口的任何后续可视对象都添加为子对象。  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a>实现 Win32 消息筛选器  
 视觉对象的主机 Win32 窗口需要窗口消息筛选器过程来处理从应用程序队列发送到窗口的消息。 窗口过程接收来自 Win32 系统的消息。 这些消息可以是输入消息，也可以是窗口管理消息。 可以选择在窗口过程中处理一条消息，或将消息传递到系统以供默认处理。  
  
 您<xref:System.Windows.Interop.HwndSource>定义为可视对象的父对象必须引用您提供的窗口消息筛选器过程。 创建对象时，<xref:System.Windows.Interop.HwndSource>将<xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A>属性设置为引用窗口过程。  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 下面的示例演示用于处理释放鼠标左键和右键消息的代码。 鼠标命中位置的坐标值包含在`lParam`参数的值中。  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a>处理 Win32 消息  
 以下示例中的代码显示如何针对主机 Win32 窗口中中包含的可视对象的层次结构执行命中测试。 通过使用<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法指定根可视对象和要命中测试的坐标值，可以识别点是否位于可视对象的几何体内。 在这种情况下，根可视对象是<xref:System.Windows.Interop.HwndSource.RootVisual%2A><xref:System.Windows.Interop.HwndSource>对象属性的值。  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 有关针对可视对象进行命中测试的详细信息，请参阅[可视化图层中的命中测试](hit-testing-in-the-visual-layer.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndSource>
- [使用 Win32 互操作进行命中测试示例](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
