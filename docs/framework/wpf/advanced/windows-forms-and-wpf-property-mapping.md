---
title: Windows 窗体和 WPF 属性映射
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: ae4a97bc96a4f9e93942b4995f488c427fda3134
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917501"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Windows 窗体和 WPF 属性映射
[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]技术有两个类似但不同的属性模型。 *属性映射*支持两种体系结构之间的互操作, 并提供以下功能:  
  
- 可以轻松地将主机环境中的相关属性更改映射到承载的控件或元素。  
  
- 提供用于映射最常使用的属性的默认处理。  
  
- 允许轻松删除、重写或扩展默认属性。  
  
- 确保自动检测主机上的属性值更改并将其转换为托管控件或元素。  
  
> [!NOTE]
> 属性更改事件不会向上传播到宿主控件或元素层次结构。 如果属性的本地值因为直接设置、样式、继承、数据绑定或其他更改属性值的机制而未更改, 则不会执行属性转换。  
  
 使用元素上的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 属性和<xref:System.Windows.Forms.Integration.ElementHost>控件上的属性来访问属性映射。 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>与 System.windows.forms.integration.windowsformshost> 元素的属性映射  
 元素使用以下翻译[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]表将默认[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]属性转换为其等效项。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
  
|Windows Presentation Foundation 托管|Windows 窗体|互操作行为|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|元素设置寄宿的控件的<xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性和承载的控件的属性。<xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost> 使用以下规则执行映射:<br /><br /> -如果<xref:System.Windows.Controls.Control.Background%2A>为纯色, 则将转换该颜色, 并使用它来<xref:System.Windows.Forms.Control.BackColor%2A>设置所承载控件的属性。 未在承载的控件上设置<xref:System.Windows.Forms.Control.BackColor%2A> 属性,因为承载的控件可以继承属性的值。<xref:System.Windows.Forms.Control.BackColor%2A> **注意：** 承载的控件不支持透明度。 分配给<xref:System.Windows.Forms.Control.BackColor%2A>的任何颜色都必须是完全不透明的, alpha 值为0xff。 <br /><br /> -如果<xref:System.Windows.Controls.Control.Background%2A>不是纯色, 则<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件从<xref:System.Windows.Controls.Control.Background%2A>属性创建位图。 控件将此位图分配<xref:System.Windows.Forms.Control.BackgroundImage%2A>给寄宿控件的属性。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 这会提供类似于透明度的效果。 **注意：** 您可以重写此行为, 也可以删除<xref:System.Windows.Controls.Control.Background%2A>属性映射。|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|如果尚未重新分配默认映射, 控制将<xref:System.Windows.Forms.Integration.WindowsFormsHost>遍历其上级层次结构, 直到找到其<xref:System.Windows.FrameworkElement.Cursor%2A>属性集的祖先。 此值将转换为最接近的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]相应光标。<br /><br /> 如果尚未重新分配<xref:System.Windows.FrameworkElement.ForceCursor%2A>属性的默认映射, 遍历<xref:System.Windows.FrameworkElement.ForceCursor%2A>将在设置为`true`的第一个上级处停止。|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>映射到<xref:System.Windows.Forms.RightToLeft.No>。<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>映射到<xref:System.Windows.Forms.RightToLeft.Yes>。<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>未映射。<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>映射到<xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>。|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>在承载的控件的<xref:System.Drawing.Font?displayProperty=nameWithType>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性集转换为相应<xref:System.Drawing.Font>的。 当其中一个属性发生更改时, 将<xref:System.Drawing.Font>创建一个新的。 对于<xref:System.Windows.FontStyles.Normal%2A> :<xref:System.Drawing.FontStyle.Italic>已禁用。 对于<xref:System.Windows.FontStyles.Italic%2A>或<xref:System.Windows.FontStyles.Oblique%2A> :<xref:System.Drawing.FontStyle.Italic>已启用。|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>在承载的控件的<xref:System.Drawing.Font?displayProperty=nameWithType>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性集转换为相应<xref:System.Drawing.Font>的。 当其中一个属性发生更改时, 将<xref:System.Drawing.Font>创建一个新的。 对于<xref:System.Windows.FontWeights.Black%2A> <xref:System.Windows.FontWeights.Bold%2A> 、<xref:System.Windows.FontWeights.ExtraBold%2A>、、、 、<xref:System.Windows.FontWeights.UltraBold%2A>、或:已<xref:System.Drawing.FontStyle.Bold>启用。 <xref:System.Windows.FontWeights.Medium%2A> <xref:System.Windows.FontWeights.Heavy%2A> <xref:System.Windows.FontWeights.DemiBold%2A> <xref:System.Windows.FontWeights.SemiBold%2A> 对于<xref:System.Windows.FontWeights.ExtraLight%2A> 、<xref:System.Windows.FontWeights.Light%2A>、 、<xref:System.Windows.FontWeights.Thin%2A>、或:<xref:System.Windows.FontWeights.UltraLight%2A>已禁用<xref:System.Drawing.FontStyle.Bold> 。 <xref:System.Windows.FontWeights.Normal%2A> <xref:System.Windows.FontWeights.Regular%2A>|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性集转换为相应<xref:System.Drawing.Font>的。 当其中一个属性发生更改时, 将<xref:System.Drawing.Font>创建一个新的。 根据字号[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]调整承载的控件的大小。<br /><br /> 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的字体大小表示为每英寸九十到一英寸, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]以一英寸的七十秒为单位。 对应的转换为:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]字号 = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]字体大小 * 72.0/96.0。|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|使用以下规则执行属性映射:<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> -如果<xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.SolidColorBrush.Color%2A>为, 则使用<xref:System.Windows.Forms.Control.ForeColor%2A>。 <xref:System.Windows.Media.SolidColorBrush><br />-如果<xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.GradientStop>为, 则将的颜色用于的最小偏移值<xref:System.Windows.Forms.Control.ForeColor%2A>。 <xref:System.Windows.Media.GradientBrush><br />-对于任何其他<xref:System.Windows.Media.Brush>类型, 保持<xref:System.Windows.Forms.Control.ForeColor%2A>不变。 这意味着使用默认值。|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|设置<xref:System.Windows.UIElement.IsEnabled%2A>后, <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素会在承载<xref:System.Windows.Forms.Control.Enabled%2A>的控件上设置属性。|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|<xref:System.Windows.Thickness>承载<xref:System.Windows.Forms.Control.Padding%2A> 控件上的属性的所有四个值都设置为相同的值。[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<br /><br /> -大于<xref:System.Int32.MaxValue>的值设置为<xref:System.Int32.MaxValue>。<br />-小于<xref:System.Int32.MinValue>的值设置为<xref:System.Int32.MinValue>。|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>映射到<xref:System.Windows.Forms.Control.Visible%2A>。  =  `true` 承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]的控件可见。 不建议将<xref:System.Windows.Forms.Control.Visible%2A>托管控件上的属性显式`false`设置为。<br />-   <xref:System.Windows.Visibility.Collapsed>映射到<xref:System.Windows.Forms.Control.Visible%2A>  =  或。`true` `false` 不绘制[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]承载的控件, 其区域处于折叠状态。<br />-   <xref:System.Windows.Visibility.Hidden>:承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]的控件占据布局空间, 但不可见。 在这种情况下<xref:System.Windows.Forms.Control.Visible%2A> , 属性设置为`true`。 不建议将<xref:System.Windows.Forms.Control.Visible%2A>托管控件上的属性显式`false`设置为。|  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素完全支持容器元素上的附加属性。  
  
 有关详细信息，请参见[演练：使用 System.windows.forms.integration.windowsformshost> 元素](walkthrough-mapping-properties-using-the-windowsformshost-element.md)映射属性。  
  
## <a name="updates-to-parent-properties"></a>父属性的更新  
 对大多数父属性的更改会导致对承载的子控件的通知。 以下列表描述了在其值更改时不会导致通知的属性。  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 例如, 如果更改了<xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的属性的值, <xref:System.Windows.Forms.Control.BackColor%2A>则承载的控件的属性将不会更改。  
  
## <a name="property-mapping-with-the-elementhost-control"></a>与 ElementHost 控件的属性映射  
 以下属性提供内置的更改通知。 当映射这些属性<xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>时, 请不要调用方法:  
  
- AutoSize  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursor  
  
- 停靠  
  
- 已启用  
  
- 字体  
  
- ForeColor  
  
- 位置  
  
- 边距  
  
- 填充  
  
- 父级  
  
- 地区  
  
- RightToLeft  
  
- Size  
  
- TabIndex  
  
- TabStop  
  
- 文本  
  
- 可见  
  
 控件使用以下翻译[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]表将默认[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性转换为其等效项。 <xref:System.Windows.Forms.Integration.ElementHost>  
  
 有关详细信息，请参见[演练：使用 ElementHost 控件](walkthrough-mapping-properties-using-the-elementhost-control.md)映射属性。  
  
|Windows 窗体托管|Windows Presentation Foundation|互操作行为|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 托管<xref:System.Windows.Media.Brush?displayProperty=nameWithType>元素上的 ()|设置此属性将强制使用<xref:System.Windows.Media.ImageBrush>重绘。 <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Media.ImageBrush> `false` <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> <xref:System.Windows.Forms.Control.BackgroundImage%2A>如果将<xref:System.Windows.Forms.Integration.ElementHost>属性设置为 (默认值), 则此属性将基于控件的外观, 包括控件的、、属性和任何附加的 paint <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>处理器.<br /><br /> <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Forms.Control.BackgroundImage%2A> <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> <xref:System.Windows.Forms.Control.BackColor%2A>如果将`true`属性设置为, 则将基于<xref:System.Windows.Forms.Integration.ElementHost>控件的父级的外观, 包括父级的、、属性和任何附加的 paint <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>处理器.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 托管<xref:System.Windows.Media.Brush?displayProperty=nameWithType>元素上的 ()|设置此属性将导致<xref:System.Windows.Forms.Control.BackColor%2A>映射所述的相同行为。|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 托管<xref:System.Windows.Media.Brush?displayProperty=nameWithType>元素上的 ()|设置此属性将导致<xref:System.Windows.Forms.Control.BackColor%2A>映射所述的相同行为。|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|标准光标转换为相应[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的标准光标。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 如果不[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]是标准游标, 则分配默认值。|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|设置<xref:System.Windows.Forms.Control.Enabled%2A>后<xref:System.Windows.Forms.Integration.ElementHost> , 控件将在承载的<xref:System.Windows.UIElement.IsEnabled%2A>元素上设置属性。|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|值转换为一组相应的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]字体属性。 <xref:System.Windows.Forms.Control.Font%2A>|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>在托管元素上|如果 <xref:System.Drawing.Font.Bold%2A> 为 `true`，则 <xref:System.Windows.Controls.Control.FontWeight%2A> 设置为 <xref:System.Windows.FontWeights.Bold%2A>。<br /><br /> 如果 <xref:System.Drawing.Font.Bold%2A> 为 `false`，则 <xref:System.Windows.Controls.Control.FontWeight%2A> 设置为 <xref:System.Windows.FontWeights.Normal%2A>。|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>在托管元素上|如果 <xref:System.Drawing.Font.Italic%2A> 为 `true`，则 <xref:System.Windows.Controls.Control.FontStyle%2A> 设置为 <xref:System.Windows.FontStyles.Italic%2A>。<br /><br /> 如果 <xref:System.Drawing.Font.Italic%2A> 为 `false`，则 <xref:System.Windows.Controls.Control.FontStyle%2A> 设置为 <xref:System.Windows.FontStyles.Normal%2A>。|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>在托管元素上|仅在承载<xref:System.Windows.Controls.TextBlock>控件时应用。|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>在托管元素上|仅在承载<xref:System.Windows.Controls.TextBlock>控件时应用。|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>映射到<xref:System.Windows.FlowDirection.LeftToRight>。<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>映射到<xref:System.Windows.FlowDirection.RightToLeft>。|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|控件使用以下规则<xref:System.Windows.UIElement.Visibility%2A>设置承载的元素上的属性: <xref:System.Windows.Forms.Integration.ElementHost><br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`映射到<xref:System.Windows.Visibility.Visible>。<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`映射到<xref:System.Windows.Visibility.Hidden>。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [WPF 和 Windows 窗体互操作](wpf-and-windows-forms-interoperation.md)
- [演练：使用 System.windows.forms.integration.windowsformshost> 元素映射属性](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [演练：使用 ElementHost 控件映射属性](walkthrough-mapping-properties-using-the-elementhost-control.md)
