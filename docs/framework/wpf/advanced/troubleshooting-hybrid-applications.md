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
ms.openlocfilehash: b85a607d2e44d6253359a81118f90e6ee05d2d3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187316"
---
# <a name="troubleshooting-hybrid-applications"></a>混合应用程序疑难解答
<a name="introduction"></a>本主题列出了创作混合应用程序时可能出现的一些常见问题，这些应用程序同时使用 Windows[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]窗体技术。  

<a name="overlapping_controls"></a>
## <a name="overlapping-controls"></a>重叠控件  
 控件可能不按预期的方式重叠。 Windows 窗体为每个控件使用单独的 HWND。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 为一个页面上的所有内容使用一个 HWND。 这一实现差异会导致意外的重叠行为。  
  
 托管中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Windows 窗体控件始终显示在内容的顶部[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]托管在控件中<xref:System.Windows.Forms.Integration.ElementHost>的内容以<xref:System.Windows.Forms.Integration.ElementHost>控件的 z 顺序显示。 可以重叠<xref:System.Windows.Forms.Integration.ElementHost>控件，但托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容不组合或交互。  
  
<a name="child_property"></a>
## <a name="child-property"></a>子属性  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>和<xref:System.Windows.Forms.Integration.ElementHost>类只能承载一个子控件或元素。 若要承载多个控件或元素，则必须使用容器作为子内容。 例如，您可以将 Windows 窗体按钮和复选框控件添加到<xref:System.Windows.Forms.Panel?displayProperty=nameWithType>控件，然后将面板分配给<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件的属性。 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 但是，您不能将按钮和复选框控件单独添加到同一<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。  
  
<a name="scaling"></a>
## <a name="scaling"></a>扩展  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和 Windows 窗体具有不同的缩放模型。 某些[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]缩放转换对 Windows 窗体控件有意义，但其他扩展转换则没有意义。 例如，将 Windows 窗体控件缩放为 0 将起作用，但如果尝试将同一控件缩放回非零值，则控件的大小仍为 0。 有关详细信息，请参阅 [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)。  
  
<a name="adapter"></a>
## <a name="adapter"></a>适配器  
 在 和<xref:System.Windows.Forms.Integration.WindowsFormsHost><xref:System.Windows.Forms.Integration.ElementHost>类工作时可能存在混淆，因为它们包含一个隐藏的容器。 和 类都有一个隐藏的容器，称为适配器，它们用于承载内容。 *adapter* <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> 对于元素<xref:System.Windows.Forms.Integration.WindowsFormsHost>，适配器派生自类<xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType>。 对于<xref:System.Windows.Forms.Integration.ElementHost>控件，适配器派生自元素<xref:System.Windows.Controls.DockPanel>。 如果你发现其他互操作主题中提到了适配器，那么所讨论的就是此容器。  
  
<a name="nesting"></a>
## <a name="nesting"></a>嵌套  
 不支持将<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素嵌套在<xref:System.Windows.Forms.Integration.ElementHost>控件中。 不支持在<xref:System.Windows.Forms.Integration.ElementHost><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素内嵌套控件。  
  
<a name="focus"></a>
## <a name="focus"></a>Focus  
 焦点在 和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Windows 窗体中的工作方式不同，这意味着焦点问题可能发生在混合应用程序中。 例如，如果<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素内部具有焦点，并且最小化并还原页面或显示模式对话框，则元素内部的焦点<xref:System.Windows.Forms.Integration.WindowsFormsHost>可能会丢失。 元素<xref:System.Windows.Forms.Integration.WindowsFormsHost>仍有焦点，但元素内的控件可能没有。  
  
 焦点还会影响数据验证。 验证在<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素中工作，但它不能像从<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素中选项卡出来或在两个不同的<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素之间工作。  
  
<a name="property_mapping"></a>
## <a name="property-mapping"></a>属性映射  
 某些属性映射需要大量解释，以在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和 Windows 窗体技术之间桥接不同的实现。 属性映射可使代码对字体、颜色和其他属性的更改做出反应。 通常，属性映射的工作方式是侦听 *Property*Changed 事件或 On*Property* 调用，然后在子控件或其适配器上设置适当的属性。 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
<a name="layoutrelated_properties_on_hosted_content"></a>
## <a name="layout-related-properties-on-hosted-content"></a>所承载内容上的布局相关属性  
 分配<xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType>或<xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType>属性时，将自动设置托管内容上的多个与布局相关的属性。 更改这些内容属性可能会导致意外的布局行为。  
  
 托管内容停靠以填充<xref:System.Windows.Forms.Integration.WindowsFormsHost>和<xref:System.Windows.Forms.Integration.ElementHost>父内容。 为了启用此填充行为，在设置子属性时，将设置多个属性。 下表列出了 和<xref:System.Windows.Forms.Integration.ElementHost><xref:System.Windows.Forms.Integration.WindowsFormsHost>类设置的内容属性。  
  
|宿主类|内容属性|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 请勿在所承载的内容上直接设置这些属性。 有关详细信息，请参阅 [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)。  
  
<a name="navigation_applications"></a>
## <a name="navigation-applications"></a>导航应用程序  
 导航应用程序不能保持用户状态。 当<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在导航应用程序中使用时，它重新创建其控件。 当用户从承载元素的页面导航，然后返回到该元素时，<xref:System.Windows.Forms.Integration.WindowsFormsHost>将重新创建子控件。 用户已经键入的所有内容都将丢失。  
  
<a name="message_loop_interoperation"></a>
## <a name="message-loop-interoperation"></a>消息循环互操作  
 使用 Windows 窗体消息循环时，邮件可能无法按预期方式处理。 该方法<xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>由<xref:System.Windows.Forms.Integration.WindowsFormsHost>构造函数调用。 此方法将向 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 消息循环中添加消息筛选器。 如果 是消息<xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>的目标，<xref:System.Windows.Forms.Control?displayProperty=nameWithType>则此筛选器调用 方法，并转换/调度消息。  
  
 如果在 Windows<xref:System.Windows.Window>窗体消息循环中显示 ，<xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>则除非调用 方法，<xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>否则无法键入任何内容。 该方法<xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>采用 和<xref:System.Windows.Window>添加<xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>，将与键相关的消息重新路由到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]消息循环。 有关详细信息，请参阅 [Windows 窗体和 WPF 互操作性输入体系结构](windows-forms-and-wpf-interoperability-input-architecture.md)。  
  
<a name="opacity_and_layering"></a>
## <a name="opacity-and-layering"></a>不透明度和分层  
 类<xref:System.Windows.Interop.HwndHost>不支持分层。 <xref:System.Windows.UIElement.Opacity%2A>这意味着在<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素上设置属性不起作用，并且不会与设置为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Window.AllowsTransparency%2A>`true`的其他窗口进行混合。  
  
<a name="dispose"></a>
## <a name="dispose"></a>释放  
 未正确释放类可能会泄漏资源。 在混合应用程序中，请确保 已释放<xref:System.Windows.Forms.Integration.WindowsFormsHost>和<xref:System.Windows.Forms.Integration.ElementHost>类，否则可能会泄漏资源。 Windows 窗体在其<xref:System.Windows.Forms.Integration.ElementHost>非模式<xref:System.Windows.Forms.Form>父窗体关闭时释放控件。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]当应用程序<xref:System.Windows.Forms.Integration.WindowsFormsHost>关闭时释放元素。 可以在 Windows 窗体消息<xref:System.Windows.Forms.Integration.WindowsFormsHost>循环<xref:System.Windows.Window>中显示 元素。 在这种情况下，代码可能不会收到应用程序正在关闭的通知。  
  
<a name="enabling_visual_styles"></a>
## <a name="enabling-visual-styles"></a>启用视觉样式  
 可能无法启用 Windows 窗体控件上的 Microsoft Windows XP 可视样式。 该方法<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>在 Windows 窗体应用程序的模板中调用。 尽管默认情况下不调用此方法，但如果使用 Visual Studio 创建项目，如果 Comctl32.dll 的版本 6.0 可用，则将为控件获取 Microsoft Windows XP 可视样式。 在线程上创建<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>句柄之前，必须调用 方法。 有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](how-to-enable-visual-styles-in-a-hybrid-application.md)。  
  
<a name="licensed_controls"></a>
## <a name="licensed-controls"></a>授权控件  
 向用户显示消息框中许可信息的许可 Windows 窗体控件可能会导致混合应用程序的意外行为。 某些授权控件会显示一个对话框来响应创建句柄的操作。 例如，授权控件可能会通知用户需要许可证，或者用户还可以试用该控件三次。  
  
 元素<xref:System.Windows.Forms.Integration.WindowsFormsHost>派生自 类<xref:System.Windows.Interop.HwndHost>，并在<xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>方法内创建子控件的句柄。 类<xref:System.Windows.Interop.HwndHost>不允许在<xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>方法中处理消息，但显示对话框会导致发送消息。 要启用此许可方案，请<xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType>先调用控件上的方法，然后再将其指定为<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的子级。  
  
<a name="wpf_designer"></a>
## <a name="wpf-designer"></a>WPF 设计器  
 您可以使用可视化工作室的 WPF 设计器来设计 WPF 内容。 以下各节列出了使用 WPF 设计器创作混合应用程序时可能出现的一些常见问题。  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>在设计时忽略 BackColorTransparent  
 在<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>设计时，该属性可能无法按预期工作。  
  
 如果 WPF 控件不在可见的父级上，则 WPF 运行时将忽略<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>该值。 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>可能忽略的原因是对象<xref:System.Windows.Forms.Integration.ElementHost>是在单独的<xref:System.AppDomain>中创建的。 但是，当您运行应用程序时，<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>确实按预期工作。  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>删除 obj 文件夹时出现设计时错误列表  
 如果删除 obj 文件夹，会出现设计时错误列表。  
  
 使用 时，Windows<xref:System.Windows.Forms.Integration.ElementHost>窗体设计器使用项目 obj 文件夹中的"调试"或"释放"文件夹中生成的文件。 如果删除这些文件，将出现设计时错误列表。 若要解决此问题，请重新生成项目。 有关详细信息，请参阅 [Windows 窗体设计器中的设计时错误](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)。  
  
<a name="elementhost_and_ime"></a>
## <a name="elementhost-and-ime"></a>ElementHost 和 IME  
 当前托管在 的<xref:System.Windows.Forms.Integration.ElementHost>WPF 控件不支持<xref:System.Windows.Forms.Control.ImeMode%2A>该属性。 托管控件<xref:System.Windows.Forms.Control.ImeMode%2A>将忽略 对 的更改。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 设计器中的互操作性](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Windows 窗体和 WPF 互操作性输入体系结构](windows-forms-and-wpf-interoperability-input-architecture.md)
- [如何：在混合应用程序中启用视觉样式](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
- [Windows 窗体设计器中的设计时错误](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [迁移和互操作性](migration-and-interoperability.md)
