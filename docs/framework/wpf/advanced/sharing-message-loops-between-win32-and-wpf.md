---
title: 在 Win32 和 WPF 之间共享消息循环
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: e1b96284d69645876d3e383beb03a2cc540d8b7b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731719"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>在 Win32 和 WPF 之间共享消息循环
本主题介绍如何通过在 <xref:System.Windows.Threading.Dispatcher> 中使用现有消息循环公开，或在互操作代码的 Win32 端创建单独的消息循环，来实现与 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]互操作的消息循环。  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher 和消息循环  
 互操作性和键盘事件支持的普通方案是实现 <xref:System.Windows.Interop.IKeyboardInputSink>或从已经实现 <xref:System.Windows.Interop.IKeyboardInputSink>的类（如 <xref:System.Windows.Interop.HwndSource> 或 <xref:System.Windows.Interop.HwndHost>）中实现子类。 但是，键盘接收器支持并不能解决通过互操作边界发送和接收消息时可能会遇到的所有可能的消息循环需求。 为了帮助实现应用程序消息循环体系结构的形式，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了 <xref:System.Windows.Interop.ComponentDispatcher> 类，该类定义消息循环遵循的简单协议。  
  
 <xref:System.Windows.Interop.ComponentDispatcher> 是公开多个成员的静态类。 每个方法的范围都隐式绑定到调用线程。 消息循环必须在关键时间（如下一部分所定义）调用某些 Api。  
  
 <xref:System.Windows.Interop.ComponentDispatcher> 提供其他组件（如键盘接收器）可以侦听的事件。 <xref:System.Windows.Threading.Dispatcher> 类按适当的顺序调用所有适当的 <xref:System.Windows.Interop.ComponentDispatcher> 方法。 如果要实现自己的消息循环，你的代码将负责以类似方式调用 <xref:System.Windows.Interop.ComponentDispatcher> 方法。  
  
 对线程调用 <xref:System.Windows.Interop.ComponentDispatcher> 方法将仅调用已在该线程上注册的事件处理程序。  
  
## <a name="writing-message-loops"></a>写入消息循环  
 下面是你编写自己的消息循环时将使用的 <xref:System.Windows.Interop.ComponentDispatcher> 成员的清单：  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>：消息循环应调用此来指示线程是模式的。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>：消息循环应调用此来指示线程已还原到变成。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>：消息循环应调用此来指示 <xref:System.Windows.Interop.ComponentDispatcher> 应引发 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 事件。 如果 `true`<xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>，则 <xref:System.Windows.Interop.ComponentDispatcher> 不会引发 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>，但是即使在模式状态下 <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> 无法对其做出响应，消息循环也可能选择调用 <xref:System.Windows.Interop.ComponentDispatcher>。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>：消息循环应调用此来指示新消息可用。 返回值指示 <xref:System.Windows.Interop.ComponentDispatcher> 事件的侦听器是否处理了该消息。 如果 <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> 返回 `true` （已处理），则调度程序不应对消息进行任何进一步的处理。 如果返回值为 `false`，则调度程序应调用 Win32 函数 `TranslateMessage`，然后调用 `DispatchMessage`。  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>使用 ComponentDispatcher 和现有消息处理  
 下面是依赖于固有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 消息循环的 <xref:System.Windows.Interop.ComponentDispatcher> 成员的清单。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>：返回应用程序是否已进入模式（例如，已推送模式消息循环）。 <xref:System.Windows.Interop.ComponentDispatcher> 可以跟踪此状态，因为类维护消息循环的 <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> 和 <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> 调用的计数。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 和 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 事件遵循委托调用的标准规则。 委托按未指定的顺序进行调用，即使第一个委托将消息标记为已处理，也会调用所有委托。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>：指示执行空闲处理的适当且有效的时间（线程没有其他挂起的消息）。 如果线程是模式的，则不会引发 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>：对消息泵处理的所有消息引发。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>： <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>期间未处理的所有消息引发。  
  
 如果在 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 事件或 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 事件之后，消息将被视为已处理，`true`事件数据中通过引用传递的 `handled` 参数。 如果 `handled` `true`，事件处理程序应忽略该消息，因为这意味着不同的处理程序会先处理该消息。 这两个事件的事件处理程序可能会修改消息。 调度程序应调度已修改的消息，而不是原始的未更改消息。 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 传递给所有侦听器，但体系结构的目的在于，只有包含目标的 HWND 的顶级窗口才能调用代码来响应消息。  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>HwndSource 如何处理 ComponentDispatcher 事件  
 如果 <xref:System.Windows.Interop.HwndSource> 是顶级窗口（无父 HWND），则它将注册到 <xref:System.Windows.Interop.ComponentDispatcher>中。 如果引发了 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>，并且消息是针对 <xref:System.Windows.Interop.HwndSource> 或子窗口的，则 <xref:System.Windows.Interop.HwndSource> 会调用其 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>，<xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A><xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> 键盘接收器序列。  
  
 如果 <xref:System.Windows.Interop.HwndSource> 不是顶级窗口（具有父 HWND），则不会进行任何处理。 仅顶级窗口应进行处理，并且在任何互操作方案中，都应有一个包含键盘接收器支持的顶级窗口。  
  
 如果在调用 <xref:System.Windows.Interop.HwndSource> 上的 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 时未首先调用适当的键盘接收器方法，则应用程序将接收更高级别的键盘事件，如 <xref:System.Windows.UIElement.KeyDown>。 但是，将不会调用键盘接收器方法，这会绕过所需的键盘输入模型功能，如访问密钥支持。 出现这种情况的原因可能是消息循环未正确地通知 <xref:System.Windows.Interop.ComponentDispatcher>上的相关线程，或是父 HWND 未调用正确的键盘接收器响应。  
  
 如果使用 <xref:System.Windows.Interop.HwndSource.AddHook%2A> 方法为该消息添加了挂钩，则发送到键盘接收器的消息可能不会发送到 HWND。 消息可能已在消息泵级别直接处理，未提交到 `DispatchMessage` 函数。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [线程模型](threading-model.md)
- [输入概述](input-overview.md)
