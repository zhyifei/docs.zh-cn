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
ms.openlocfilehash: 621684e14f9d1b599c4ef60e3731f0f58f31aacd
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740161"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>教程：在 Win32 应用程序中承载 Visual 对象
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当你在 Win32 代码中有大量投资时，将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 功能添加到应用程序而不是重写你的代码可能会更有效。 若要为应用程序中同时使用的 Win32 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 图形子系统提供支持，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了一种机制，用于在 Win32 窗口中承载对象。  
  
 本教程介绍如何编写示例应用程序，[使用 Win32 互操作进行命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159995)，该应用程序在 win32 窗口中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的视觉对象。  

<a name="requirements"></a>   
## <a name="requirements"></a>需求  
 本教程假定你基本熟悉 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 Win32 编程。 有关 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 编程的基本简介，请参阅[演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。 有关 Win32 编程的介绍，请参阅主题中的任意一本书，如 Charles Petzold 的特定*编程窗口*中所述。  
  
> [!NOTE]
> 本教程包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 有关完整的示例代码，请参阅[通过 Win32 互操作进行命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159995)。  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>创建宿主 Win32 窗口  
 在 Win32 窗口中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 对象的关键是 <xref:System.Windows.Interop.HwndSource> 类。 此类在 Win32 窗口中包装 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的对象，从而使它们可以作为子窗口合并到 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中。  
  
 下面的示例演示了用于创建 <xref:System.Windows.Interop.HwndSource> 对象作为视觉对象的 Win32 容器窗口的代码。 若要设置 Win32 窗口的窗口样式、位置和其他参数，请使用 <xref:System.Windows.Interop.HwndSourceParameters> 对象。  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> 属性的值不能设置为 WS_EX_TRANSPARENT。 这意味着主机 Win32 窗口不能是透明的。 出于此原因，主机 Win32 窗口的背景色设置为与父窗口相同的背景色。  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>将视觉对象添加到宿主 Win32 窗口  
 为视觉对象创建宿主 Win32 容器窗口后，可以向其添加视觉对象。 你需要确保任何视觉对象的转换（如动画）不超出主机 Win32 窗口的边框的界限。  
  
 下面的示例演示用于创建 <xref:System.Windows.Interop.HwndSource> 对象并向其中添加视觉对象的代码。  
  
> [!NOTE]
> <xref:System.Windows.Interop.HwndSource> 对象的 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 属性设置为添加到 host Win32 窗口的第一个视觉对象。 根视觉对象定义视觉对象树最顶层的节点。 添加到主机 Win32 窗口中的任何后续视觉对象将添加为子对象。  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>实现 Win32 消息筛选器  
 视觉对象的宿主 Win32 窗口需要一个窗口消息筛选器过程来处理从应用程序队列发送到窗口的消息。 窗口过程接收来自 Win32 系统的消息。 这些消息可以是输入消息，也可以是窗口管理消息。 可以选择在窗口过程中处理一条消息，或将消息传递到系统以供默认处理。  
  
 您定义为视觉对象的父级的 <xref:System.Windows.Interop.HwndSource> 对象必须引用您提供的窗口消息筛选器过程。 创建 <xref:System.Windows.Interop.HwndSource> 对象时，请将 <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> 属性设置为引用该窗口过程。  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 下面的示例演示用于处理释放鼠标左键和右键消息的代码。 鼠标命中位置的坐标值包含在 `lParam` 参数的值中。  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>处理 Win32 消息  
 以下示例中的代码演示了如何针对主机 Win32 窗口中包含的视觉对象的层次结构执行命中测试。 可以通过使用 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 方法指定要对其进行命中测试的根可视对象和坐标值，来确定某个点是否在可视对象的几何图形内。 在这种情况下，根可视对象是 <xref:System.Windows.Interop.HwndSource> 对象的 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 属性的值。  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 有关对视觉对象进行命中测试的详细信息，请参阅[可视化层中的命中测试](hit-testing-in-the-visual-layer.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndSource>
- [通过 Win32 互操作进行命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159995)
- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
