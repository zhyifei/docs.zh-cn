---
title: Windows 窗体和 WPF 互操作性输入体系结构
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
ms.openlocfilehash: 250f34e3e5420a613bc7b1035c62af90665e71ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows 窗体和 WPF 互操作性输入体系结构
之间的互操作[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]要求这两种技术具有相应的键盘输入的处理。 本主题介绍这些技术键盘和消息处理，以支持混合应用程序中的平滑互操作的实现。  
  
 本主题包含以下小节：  
  
-   无模式的表单和对话框  
  
-   WindowsFormsHost 键盘和消息处理  
  
-   ElementHost 键盘和消息处理  
  
## <a name="modeless-forms-and-dialog-boxes"></a>无模式的表单和对话框  
 调用<xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素以打开一个从无模式对话框窗体或对话框中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序。  
  
 调用<xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>打开无模式的控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页面[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-基于应用程序。  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost 键盘和消息处理  
 当由托管时[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]键盘和消息处理包含以下内容：  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost>类获取来自[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]消息循环，它由实现<xref:System.Windows.Interop.ComponentDispatcher>类。  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost>类创建一个代理项[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]消息循环，以确保该普通[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]键盘处理时发生。  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost>类实现<xref:System.Windows.Interop.IKeyboardInputSink>接口来协调使用焦点管理[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost>控件将其本身注册并启动其消息循环。  
  
 下列各节描述这些部分的更多详细信息中的过程。  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>获取从 WPF 消息循环的消息  
 <xref:System.Windows.Interop.ComponentDispatcher>类实现的消息循环管理器[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 <xref:System.Windows.Interop.ComponentDispatcher>类提供挂钩以启用外部客户端之前筛选消息[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]处理它们。  
  
 互操作实现句柄<xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>事件，它使[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件以处理消息之前[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件。  
  
### <a name="surrogate-windows-forms-message-loop"></a>Windows 窗体消息循环，代理项  
 默认情况下，<xref:System.Windows.Forms.Application?displayProperty=nameWithType>类包含的主消息循环[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]应用程序。 期间间的互操作，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]循环不处理消息的消息。 因此，必须重新生成此逻辑。 处理程序<xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>事件执行以下步骤：  
  
1.  筛选消息使用<xref:System.Windows.Forms.IMessageFilter>接口。  
  
2.  调用<xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>方法。  
  
3.  将转换，如有必要调度消息。  
  
4.  将该消息传递给承载的控件中，如果没有其他控件处理消息。  
  
### <a name="ikeyboardinputsink-implementation"></a>IKeyboardInputSink 实现  
 代理项消息循环处理键盘管理。 因此，<xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType>方法是唯一<xref:System.Windows.Interop.IKeyboardInputSink>要求中的实现的成员<xref:System.Windows.Forms.Integration.WindowsFormsHost>类。  
  
 默认情况下，<xref:System.Windows.Interop.HwndHost>类返回`false`有关其<xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>实现。 这可以防止从 tab 键切换[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控制转移到[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>实现<xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType>方法执行以下步骤：  
  
1.  查找第一个或最后一个[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]所包含的控件<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件，可以接收焦点。 控件选择取决于遍历信息。  
  
2.  将焦点设置到控件，并返回`true`。  
  
3.  如果没有控件可以接收焦点，则返回`false`。  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost 注册  
 当窗口的句柄<xref:System.Windows.Forms.Integration.WindowsFormsHost>创建控件，<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件调用注册其存在消息循环的内部静态方法。  
  
 注册，期间<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件将检查消息循环。 如果尚未启动消息循环，<xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>创建事件处理程序。 消息循环运行时被视为<xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>事件处理程序附加。  
  
 销毁窗口句柄时，<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件移除本身注册。  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost 键盘和消息处理  
 当由托管时[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]应用程序，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]键盘和消息处理包含以下内容：  
  
-   <xref:System.Windows.Interop.HwndSource><xref:System.Windows.Interop.IKeyboardInputSink>，和<xref:System.Windows.Interop.IKeyboardInputSite>接口实现。  
  
-   按 tab 键和箭头键。  
  
-   命令键和对话框键。  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 快捷键处理。  
  
 下列各节介绍了这些部分中更多详细信息。  
  
### <a name="interface-implementations"></a>接口实现  
 在[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]，键盘消息路由到具有焦点的控件的窗口句柄。 在<xref:System.Windows.Forms.Integration.ElementHost>控件，这些消息路由到承载的元素。 若要实现此目的，<xref:System.Windows.Forms.Integration.ElementHost>控件提供<xref:System.Windows.Interop.HwndSource>实例。 如果<xref:System.Windows.Forms.Integration.ElementHost>控件有焦点，<xref:System.Windows.Interop.HwndSource>实例路由大多数键盘输入，以便可以由处理[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.InputManager>类。  
  
 <xref:System.Windows.Interop.HwndSource>类实现<xref:System.Windows.Interop.IKeyboardInputSink>和<xref:System.Windows.Interop.IKeyboardInputSite>接口。  
  
 键盘间的互操作依赖于实现<xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A>方法句柄 TAB 键和箭头键将焦点移出托管元素的输入。  
  
### <a name="tabbing-and-arrow-keys"></a>Tabbing 和箭头键  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]选择逻辑映射到<xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>和<xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A>方法来实现选项卡和箭头键导航。 重写<xref:System.Windows.Forms.Integration.ElementHost.Select%2A>方法来实现此映射。  
  
### <a name="command-keys-and-dialog-box-keys"></a>命令键和对话框键  
 能够在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]处理命令键和对话框键的第一个机会[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]预处理命令连接到<xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>方法。 重写<xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType>方法连接这两种技术。  
  
 与<xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>方法，承载的元素可以处理任何键的消息，如 WM_KEYDOWN、 WM_KEYUP、 WM_SYSKEYDOWN 或 WM_SYSKEYUP，包括命令键，例如选项卡、 ENTER、 ESC、 和箭头键。 如果未处理键消息，则将它发送[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上级层次结构进行处理。  
  
### <a name="accelerator-processing"></a>快捷键处理  
 若要正确处理快捷键，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]快捷键处理必须连接到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.AccessKeyManager>类。 此外，必须正确路由所有的 WM_CHAR 消息到承载的元素。  
  
 因为默认值<xref:System.Windows.Interop.HwndSource>实现<xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>方法返回`false`，使用以下逻辑的 WM_CHAR 消息进行处理：  
  
-   <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType>方法被重写，以确保所有的 WM_CHAR 消息都转发至承载的元素。  
  
-   当按下 ALT 键，则消息将 WM_SYSCHAR。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 不进行预处理通过此消息<xref:System.Windows.Forms.Control.IsInputChar%2A>方法。 因此，<xref:System.Windows.Forms.Control.ProcessMnemonic%2A>方法被重写查询[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.AccessKeyManager>已注册的快捷键。 如果找到已注册的快捷键，则<xref:System.Windows.Input.AccessKeyManager>处理它。  
  
-   如果未按下 ALT 键， [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager>类处理未处理的输入。 如果输入是快捷键，<xref:System.Windows.Input.AccessKeyManager>处理它。 <xref:System.Windows.Input.InputManager.PostProcessInput>的未处理的 WM_CHAR 消息处理事件。  
  
 当用户按下 ALT 键时，整个窗体上显示快捷键的可视化提示。 若要支持此行为，所有<xref:System.Windows.Forms.Integration.ElementHost>活动窗体上的控件接收 WM_SYSKEYDOWN 消息，而在控件有焦点。  
  
 消息将仅发送给<xref:System.Windows.Forms.Integration.ElementHost>活动窗体中的控件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [演练：在 WPF 中托管 Windows 窗体复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [WPF 和 Win32 互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
