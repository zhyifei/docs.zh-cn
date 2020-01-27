---
title: Windows 窗体和 WPF 互操作输入体系结构
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
ms.openlocfilehash: f79971ba13691ccc36420e39696b7b8a46e5ce0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745049"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows Forms 및 WPF 상호 운용성 입력 아키텍처
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 之间的互操作要求两种技术都具有适当的键盘输入处理。 本主题介绍这些技术如何实现键盘和消息处理，以便在混合应用程序中实现平滑互操作。  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- 无模式窗体和对话框  
  
- System.windows.forms.integration.windowsformshost> 键盘和消息处理  
  
- ElementHost 键盘和消息处理  
  
## <a name="modeless-forms-and-dialog-boxes"></a>无模式窗体和对话框  
 对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素调用 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 方法，以便从基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中打开无模式窗体或对话框。  
  
 对 <xref:System.Windows.Forms.Integration.ElementHost> 控件调用 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 方法，以便在基于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]的应用程序中打开无模式 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页。  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>System.windows.forms.integration.windowsformshost> 键盘和消息处理  
 当由基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序承载时，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 键盘和消息处理包含以下内容：  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 类从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 消息循环获取消息，该消息循环由 <xref:System.Windows.Interop.ComponentDispatcher> 类实现。  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 类创建一个代理项 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 消息循环，以确保发生普通 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 键盘处理。  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 类实现 <xref:System.Windows.Interop.IKeyboardInputSink> 接口，以将焦点管理与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]进行协调。  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件会自行注册并启动其消息循环。  
  
 以下部分更详细地介绍了此过程的各个部分。  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>从 WPF 消息循环获取消息  
 <xref:System.Windows.Interop.ComponentDispatcher> 类实现 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的消息循环管理器。 <xref:System.Windows.Interop.ComponentDispatcher> 类提供挂钩，以允许外部客户端在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 处理消息之前对其进行筛选。  
  
 互操作实现处理 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 事件，使 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件之前处理消息。  
  
### <a name="surrogate-windows-forms-message-loop"></a>代理项 Windows 窗体消息循环  
 默认情况下，<xref:System.Windows.Forms.Application?displayProperty=nameWithType> 类包含 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 应用程序的主消息循环。 在互操作期间，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 消息循环不处理消息。 因此，必须重现此逻辑。 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 事件的处理程序执行以下步骤：  
  
1. 使用 <xref:System.Windows.Forms.IMessageFilter> 接口来筛选消息。  
  
2. <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> 메서드를 호출합니다.  
  
3. 如果需要，请转换并调度消息。  
  
4. 如果没有其他控件处理消息，则将消息传递给宿主控件。  
  
### <a name="ikeyboardinputsink-implementation"></a>System.windows.interop.ikeyboardinputsink> 实现  
 代理项消息循环处理键盘管理。 因此，<xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 方法是在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 类中唯一需要实现的 <xref:System.Windows.Interop.IKeyboardInputSink> 成员。  
  
 默认情况下，<xref:System.Windows.Interop.HwndHost> 类返回 <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 实现的 `false`。 这会阻止从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件到 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的 tab 键。  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 方法的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 实现执行以下步骤：  
  
1. 查找 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件包含的第一个或最后一个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件，该控件可以接收焦点。 控件选择取决于遍历信息。  
  
2. 将焦点设置到控件上并返回 `true`。  
  
3. 如果控件无法接收焦点，则返回 `false`。  
  
### <a name="windowsformshost-registration"></a>System.windows.forms.integration.windowsformshost> 注册  
 当创建 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的窗口句柄时，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将调用一个内部静态方法，该方法为消息循环注册其状态。  
  
 在注册期间，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将检查消息循环。 如果消息循环尚未启动，则创建 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 事件处理程序。 附加 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 事件处理程序时，消息循环被视为正在运行。  
  
 销毁窗口句柄时，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件会将其自身从注册中删除。  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost 键盘和消息处理  
 由 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 应用程序承载时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 键盘和消息处理包含以下内容：  
  
- <xref:System.Windows.Interop.HwndSource>、<xref:System.Windows.Interop.IKeyboardInputSink>和 <xref:System.Windows.Interop.IKeyboardInputSite> 接口实现。  
  
- Tab 键和箭头键。  
  
- 命令键和对话框键。  
  
- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 加速器处理。  
  
 以下部分更详细地介绍了这些部分。  
  
### <a name="interface-implementations"></a>接口实现  
 在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中，键盘消息将路由到具有焦点的控件的窗口句柄。 在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中，这些消息将路由到承载的元素。 为实现此目的，<xref:System.Windows.Forms.Integration.ElementHost> 控件提供 <xref:System.Windows.Interop.HwndSource> 实例。 如果 <xref:System.Windows.Forms.Integration.ElementHost> 控件具有焦点，则 <xref:System.Windows.Interop.HwndSource> 实例会路由大多数键盘输入，以便 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 类处理此类输入。  
  
 <xref:System.Windows.Interop.HwndSource> 类实现 <xref:System.Windows.Interop.IKeyboardInputSink> 和 <xref:System.Windows.Interop.IKeyboardInputSite> 接口。  
  
 键盘互操作依赖于实现 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 方法来处理将焦点移出托管元素的 TAB 键和箭头键输入。  
  
### <a name="tabbing-and-arrow-keys"></a>Tab 键和箭头键  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 选择逻辑映射到 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 并 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 方法来实现 TAB 键和箭头键导航。 重写 <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> 方法完成此映射。  
  
### <a name="command-keys-and-dialog-box-keys"></a>命令键和对话框键  
 为了使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 第一次处理命令键和对话框键的机会，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 命令预处理连接到 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 方法。 重写 <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> 方法会连接这两个技术。  
  
 利用 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 方法，承载的元素可以处理任何关键消息，如 WM_KEYDOWN、WM_KEYUP、WM_SYSKEYDOWN 或 WM_SYSKEYUP，包括命令键，如 TAB 键、ENTER 键、ESC 键和箭头键。 如果未处理某个关键消息，则会将该消息发送 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 祖先层次结构进行处理。  
  
### <a name="accelerator-processing"></a>加速器处理  
 若要正确处理快捷键，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 加速器处理必须连接到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 类。 此外，所有 WM_CHAR 消息都必须正确路由到托管元素。  
  
 由于 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> 方法的默认 <xref:System.Windows.Interop.HwndSource> 实现返回 `false`，因此使用以下逻辑处理 WM_CHAR 消息：  
  
- 重写 <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> 方法，以确保将所有 WM_CHAR 消息转发到承载的元素。  
  
- 如果按下了 ALT 键，则会 WM_SYSCHAR 消息。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 不通过 <xref:System.Windows.Forms.Control.IsInputChar%2A> 方法对此消息进行预处理。 因此，会重写 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 方法，以查询已注册快捷键的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>。 如果找到了已注册的加速器，<xref:System.Windows.Input.AccessKeyManager> 会对其进行处理。  
  
- 如果未按下 ALT 键，则 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 类处理未处理的输入。 如果输入是一个快捷键，则 <xref:System.Windows.Input.AccessKeyManager> 处理该输入。 对于未处理的 WM_CHAR 消息，将处理 <xref:System.Windows.Input.InputManager.PostProcessInput> 事件。  
  
 当用户按下 ALT 键时，将在整个窗体上显示快捷键视觉提示。 为了支持此行为，活动窗体上的所有 <xref:System.Windows.Forms.Integration.ElementHost> 控件都将接收 WM_SYSKEYDOWN 消息，而不管哪个控件具有焦点。  
  
 消息只发送到活动窗体中 <xref:System.Windows.Forms.Integration.ElementHost> 控件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
