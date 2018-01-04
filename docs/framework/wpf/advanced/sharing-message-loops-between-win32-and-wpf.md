---
title: "在 Win32 和 WPF 之间共享消息循环"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3122100f93d15c04c109564e1abd2dc13f37990
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>在 Win32 和 WPF 之间共享消息循环
本主题介绍如何实现与互操作的消息循环[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]，通过使用现有消息中的循环公开<xref:System.Windows.Threading.Dispatcher>或通过创建单独的消息循环上[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]侧的互操作代码。  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher 和消息循环  
 间的互操作和键盘事件支持的一般方案是实现<xref:System.Windows.Interop.IKeyboardInputSink>，或从已实现的类的子类化<xref:System.Windows.Interop.IKeyboardInputSink>，如<xref:System.Windows.Interop.HwndSource>或<xref:System.Windows.Interop.HwndHost>。 但是，键盘接收器支持不能解决你可能必须发送和接收跨互操作边界的消息时的所有可能的消息循环需求。 若要帮助正式化应用程序消息循环的体系结构，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供<xref:System.Windows.Interop.ComponentDispatcher>类，该类定义消息循环，以按照简单协议。  
  
 <xref:System.Windows.Interop.ComponentDispatcher>是一个静态类，公开多个成员。 每个方法的作用域是隐式绑定到调用的线程。 消息循环必须调用其中一些[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]在关键时刻 （如在下一节中定义）。  
  
 <xref:System.Windows.Interop.ComponentDispatcher>提供 （例如键盘接收器中） 的其他组件可以侦听的事件。 <xref:System.Windows.Threading.Dispatcher>类调用所有相应<xref:System.Windows.Interop.ComponentDispatcher>恰当的顺序的方法。 如果你要实现您自己的消息循环，你的代码负责调用<xref:System.Windows.Interop.ComponentDispatcher>以类似的方式的方法。  
  
 调用<xref:System.Windows.Interop.ComponentDispatcher>在线程上的方法将仅调用在该线程注册的事件处理程序。  
  
## <a name="writing-message-loops"></a>写入消息循环  
 下面是清单<xref:System.Windows.Interop.ComponentDispatcher>如果你编写您自己的消息循环将使用的成员：  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>： 您的消息循环应调用此成员以指示该线程是模式。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>： 您的消息循环应调用此成员以指示线程已还原为非模式线程。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>： 您的消息循环应调用此成员，则指示<xref:System.Windows.Interop.ComponentDispatcher>应引发<xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>事件。 <xref:System.Windows.Interop.ComponentDispatcher>不会引发<xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>如果<xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>是`true`，但也可以选择消息循环调用<xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>即使<xref:System.Windows.Interop.ComponentDispatcher>无法响应在模式状态。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>： 您的消息循环应调用它表示一条新消息是否可用。 返回值指示是否为侦听器<xref:System.Windows.Interop.ComponentDispatcher>处理事件的消息。 如果<xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>返回`true`（处理），调度程序应进行任何进一步的消息。 如果返回值为`false`，调度程序需要调用[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]函数`TranslateMessage`，然后调用`DispatchMessage`。  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>使用 ComponentDispatcher 和现有消息处理  
 下面是清单<xref:System.Windows.Interop.ComponentDispatcher>成员将使用如果依赖于固有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]消息循环。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>： 返回应用程序是否已进入模式状态 （例如，模式的消息循环已推送）。 <xref:System.Windows.Interop.ComponentDispatcher>可以跟踪此状态，因为该类维护的计数<xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>和<xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>从消息循环的调用。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>和<xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>事件遵循标准规则进行委托调用。 未指定顺序调用委托和即使第一个将该消息标记为已处理调用所有委托。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>： 指示执行空闲处理适当和有效时间 （没有其他挂起消息线程）。 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>将不会引发如果线程是模式。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>： 引发的所有消息泵处理的消息。  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>： 为期间尚未处理的所有消息引发<xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>。  
  
 则认为该消息后的处理的如果<xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>事件或<xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>事件，`handled`通过在事件数据中的引用传递的参数是`true`。 事件处理程序应忽略该消息，如果`handled`是`true`，因为这意味着不同的处理程序首先处理该消息。 这两个事件的事件处理程序可以修改该消息。 调度程序应调度修改后的消息而非原始不变的消息。 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>传递到所有的侦听器，但体系结构的意图是仅包含目标的消息应从该处调用代码以响应消息的 HWND 的顶级窗口。  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>HwndSource 如何处理 ComponentDispatcher 事件  
 如果<xref:System.Windows.Interop.HwndSource>为顶级窗口 （没有父级 HWND），它将注册<xref:System.Windows.Interop.ComponentDispatcher>。 如果<xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>引发时，如果消息是否适用于<xref:System.Windows.Interop.HwndSource>或子窗口<xref:System.Windows.Interop.HwndSource>调用其<xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>， <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>，<xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A>键盘接收器序列。  
  
 如果<xref:System.Windows.Interop.HwndSource>不是顶级窗口 （具有父 HWND），不将任何处理。 只有顶级窗口应执行的处理，且存在预计会具有键盘接收器支持的最上层窗口作为任何互操作方案的一部分。  
  
 如果<xref:System.Windows.Interop.HwndHost.WndProc%2A>上<xref:System.Windows.Interop.HwndSource>调用而无需首先调用相应的键盘接收器方法，你的应用程序将接收更高的级别的键盘事件如<xref:System.Windows.UIElement.KeyDown>。 但是，任何键盘接收器方法将不调用，从而避开了所需的键盘输入的模型功能，例如访问密钥支持。 这可能是因为消息循环没有正确上通知相关线程<xref:System.Windows.Interop.ComponentDispatcher>，或因为父 HWND 未调用正确键盘接收器响应。  
  
 如果通过使用添加挂钩，该消息将转到键盘接收器一条消息可能不为 HWND 会发送<xref:System.Windows.Interop.HwndSource.AddHook%2A>方法。 消息可能已处理在消息泵级别直接而未提交给`DispatchMessage`函数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Interop.ComponentDispatcher>  
 <xref:System.Windows.Interop.IKeyboardInputSink>  
 [WPF 和 Win32 互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [线程模型](../../../../docs/framework/wpf/advanced/threading-model.md)  
 [输入概述](../../../../docs/framework/wpf/advanced/input-overview.md)
