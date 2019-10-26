---
title: 混合应用程序疑难解答
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: 541d71efa66d14855704797892cac68799215159
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919759"
---
# <a name="troubleshooting-hybrid-applications"></a>混合应用程序疑难解答
<a name="introduction"></a>本主题列出了在创作同时使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]技术的混合应用程序时可能发生的一些常见问题。  

<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>重叠控件  
 控件可能不按预期的方式重叠。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]为每个控件使用单独的 HWND。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 为一个页面上的所有内容使用一个 HWND。 这一实现差异会导致意外的重叠行为。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件总是出现在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容之上。  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 控件中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容以 <xref:System.Windows.Forms.Integration.ElementHost> 控件的 z 顺序显示。 可以重叠 <xref:System.Windows.Forms.Integration.ElementHost> 控件，但承载的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容不会合并或交互。  
  
<a name="child_property"></a>   
## <a name="child-property"></a>子属性  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 类只能承载一个子控件或元素。 若要承载多个控件或元素，则必须使用容器作为子内容。 例如，您可以将 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 按钮和复选框控件添加到 <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> 控件，然后将面板分配给 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 属性。 但是，不能将按钮和复选框控件分别添加到同一个 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件。  
  
<a name="scaling"></a>   
## <a name="scaling"></a>缩放  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]具有不同的缩放模型。 某些 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 缩放变换对于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件是有意义的，但其他变换是无意义的。 例如，将 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件缩放到 0 是可行的，但如果尝试将同一控件重新缩放回非零值，该控件的大小仍然为 0。 有关详细信息，请参阅 [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)。  
  
<a name="adapter"></a>   
## <a name="adapter"></a>适配器  
 在处理 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 类时可能会产生混淆，因为它们包含隐藏容器。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 类都有一个称为*适配器*的隐藏容器，用来承载内容。 对于 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素，适配器从 <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> 类派生。 对于 <xref:System.Windows.Forms.Integration.ElementHost> 控件，适配器派生自 <xref:System.Windows.Controls.DockPanel> 元素。 如果你发现其他互操作主题中提到了适配器，那么所讨论的就是此容器。  
  
<a name="nesting"></a>   
## <a name="nesting"></a>嵌套  
 不支持在 <xref:System.Windows.Forms.Integration.ElementHost> 控件内嵌套 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。 也不支持在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素中嵌套 <xref:System.Windows.Forms.Integration.ElementHost> 控件。  
  
<a name="focus"></a>   
## <a name="focus"></a>焦点  
 焦点在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中的工作方式是不同的，这意味着混合应用程序中可能发生焦点问题。 例如，如果焦点位于 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素内，并且最小化和还原页面或显示模式对话框，则 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素中的焦点可能会丢失。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素仍具有焦点，但它内部的控件可能不具有焦点。  
  
 焦点还会影响数据验证。 验证在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素中有效，但当您从 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素中或在两个不同的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素之间切换时，它不起作用。  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>属性映射  
 某些属性映射需要先进行大量的转译，才能将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]技术之间不同的实现桥接起来。 属性映射可使代码对字体、颜色和其他属性的更改做出反应。 通常，属性映射的工作方式是侦听 *Property*Changed 事件或 On*Property* 调用，然后在子控件或其适配器上设置适当的属性。 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>所承载内容上的布局相关属性  
 分配 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> 属性时，将自动设置托管内容上的多个与布局相关的属性。 更改这些内容属性可能会导致意外的布局行为。  
  
 承载的内容将停靠，以填充 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 父级。 为了启用此填充行为，在设置子属性时，将设置多个属性。 下表列出了 <xref:System.Windows.Forms.Integration.ElementHost> 和 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 类设置哪些内容属性。  
  
|宿主类|内容属性|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 请勿在所承载的内容上直接设置这些属性。 有关详细信息，请参阅 [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)。  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>导航应用程序  
 导航应用程序不能保持用户状态。 在导航应用程序中使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素时，将重新创建其控件。 当用户离开承载 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的页面，然后返回到该控件时，将会重新创建子控件。 用户已经键入的所有内容都将丢失。  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>消息循环互操作  
 在使用 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]消息循环时，可能无法按照预期方式处理消息。 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 方法由 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 构造函数调用。 此方法将向 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 消息循环中添加消息筛选器。 如果 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 是消息的目标，则此筛选器调用 <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> 方法，并转换/调度该消息。  
  
 如果在具有 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 消息循环中显示 <xref:System.Windows.Window>，则除非调用 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 方法，否则不能键入任何内容。 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 方法采用 <xref:System.Windows.Window> 并添加 <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>，这会将与键相关的消息重排到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 消息循环中。 有关详细信息，请参阅 [Windows 窗体和 WPF 互操作性输入体系结构](windows-forms-and-wpf-interoperability-input-architecture.md)。  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>不透明度和分层  
 <xref:System.Windows.Interop.HwndHost> 类不支持分层。 这意味着，在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素上设置 <xref:System.Windows.UIElement.Opacity%2A> 属性不起作用，并且其他 <xref:System.Windows.Window.AllowsTransparency%2A> 设置为 `true`的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口不会进行混合。  
  
<a name="dispose"></a>   
## <a name="dispose"></a>释放  
 未正确释放类可能会泄漏资源。 在混合应用程序中，请确保已释放 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 类，否则可能会泄漏资源。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 在其非模式 <xref:System.Windows.Forms.Form> 父项关闭时释放 <xref:System.Windows.Forms.Integration.ElementHost> 控件。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 在应用程序关闭时释放 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。 可以在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 消息循环的 <xref:System.Windows.Window> 中显示 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。 在这种情况下，代码可能不会收到应用程序正在关闭的通知。  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>启用视觉样式  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件上的 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 视觉样式可能未启用。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 应用程序的模板中调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法。 尽管默认情况下不会调用此方法，但如果你使用 Visual Studio 创建项目，则当 Comctl32.dll 版本6.0 可用时，你将获得控件 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 视觉样式。 在线程上创建句柄之前，必须先调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法。 有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](how-to-enable-visual-styles-in-a-hybrid-application.md)。  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>授权控件  
 授权的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件会在消息框中向用户显示许可信息，对于混合应用程序，这可能会导致意外行为。 某些授权控件会显示一个对话框来响应创建句柄的操作。 例如，授权控件可能会通知用户需要许可证，或者用户还可以试用该控件三次。  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素派生自 <xref:System.Windows.Interop.HwndHost> 类，子控件的句柄是在 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 方法中创建的。 <xref:System.Windows.Interop.HwndHost> 类不允许在 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 方法中处理消息，但显示一个对话框会导致发送消息。 若要启用此授权方案，请先对控件调用 <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> 方法，然后再将其分配为 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子元素。  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>WPF 设计器  
 可以使用 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 设计你的 WPF 内容。 以下部分列出了在使用 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 创作混合应用程序时可能发生的一些常见问题。  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>在设计时忽略 BackColorTransparent  
 在设计时，<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 属性可能不会按预期方式工作。  
  
 如果 WPF 控件不在可见父级上，WPF 运行时将忽略 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 值。 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 可能被忽略的原因是因为 <xref:System.Windows.Forms.Integration.ElementHost> 对象是在单独的 <xref:System.AppDomain>中创建的。 但是，当你运行应用程序时，<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 会按预期方式工作。  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>删除 obj 文件夹时出现设计时错误列表  
 如果删除 obj 文件夹，会出现设计时错误列表。  
  
 当你使用 <xref:System.Windows.Forms.Integration.ElementHost>进行设计时，Windows 窗体设计器将在项目的 obj 文件夹内的 "调试" 或 "发布" 文件夹中使用生成的文件。 如果删除这些文件，将出现设计时错误列表。 若要解决此问题，请重新生成项目。 有关详细信息，请参阅 [Windows 窗体设计器中的设计时错误](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)。  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost 和 IME  
 <xref:System.Windows.Forms.Integration.ElementHost> 中承载的 WPF 控件当前不支持 <xref:System.Windows.Forms.Control.ImeMode%2A> 属性。 所承载的控件将忽略对 <xref:System.Windows.Forms.Control.ImeMode%2A> 所做的更改。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 设计器中的互操作性](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Windows 窗体和 WPF 互操作性输入体系结构](windows-forms-and-wpf-interoperability-input-architecture.md)
- [如何：在混合应用程序中启用视觉对象样式](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
- [Windows 窗体设计器中的设计时错误](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [迁移和互操作性](migration-and-interoperability.md)
