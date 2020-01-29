---
title: Windows 窗体和 WPF 属性映射
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: 07e58f87d886212426e25be83f988037549ab642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735234"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Windows 窗体和 WPF 属性映射
[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 技术有两个类似但不同的属性模型。 *属性映射*支持两种体系结构之间的互操作，并提供以下功能：  
  
- 可以轻松地将主机环境中的相关属性更改映射到承载的控件或元素。  
  
- 提供用于映射最常使用的属性的默认处理。  
  
- 允许轻松删除、重写或扩展默认属性。  
  
- 确保自动检测主机上的属性值更改并将其转换为托管控件或元素。  
  
> [!NOTE]
> 属性更改事件不会向上传播到宿主控件或元素层次结构。 如果属性的本地值因为直接设置、样式、继承、数据绑定或其他更改属性值的机制而未更改，则不会执行属性转换。  
  
 使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 属性和 <xref:System.Windows.Forms.Integration.ElementHost> 控件上的 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 属性来访问属性映射。  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>与 System.windows.forms.integration.windowsformshost> 元素的属性映射  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素使用以下翻译表将默认 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性转换为其 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 等效项。  
  
|Windows Presentation Foundation 托管|Windows 窗体|互操作行为|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素设置寄宿的控件的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性和承载的控件的 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性。 使用以下规则执行映射：<br /><br /> -如果 <xref:System.Windows.Controls.Control.Background%2A> 为纯色，则将转换该颜色，并使用它来设置所承载控件的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性。 未在承载的控件上设置 <xref:System.Windows.Forms.Control.BackColor%2A> 属性，因为承载的控件可以继承 <xref:System.Windows.Forms.Control.BackColor%2A> 属性的值。 **注意：** 承载的控件不支持透明度。 分配给 <xref:System.Windows.Forms.Control.BackColor%2A> 的任何颜色必须完全不透明，alpha 值为0xFF。 <br /><br /> -如果 <xref:System.Windows.Controls.Control.Background%2A> 不是纯色，则 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将从 <xref:System.Windows.Controls.Control.Background%2A> 属性创建位图。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将此位图分配给寄宿控件的 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性。 这会提供类似于透明度的效果。 **注意：** 您可以重写此行为，或者可以删除 <xref:System.Windows.Controls.Control.Background%2A> 属性映射。|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|如果尚未重新分配默认映射，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将遍历其上级层次结构，直到它找到其 <xref:System.Windows.FrameworkElement.Cursor%2A> 属性集的上级。 此值将转换为最接近的相应 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 游标。<br /><br /> 如果未重新分配 <xref:System.Windows.FrameworkElement.ForceCursor%2A> 属性的默认映射，则遍历将在 <xref:System.Windows.FrameworkElement.ForceCursor%2A> 设置为 `true`的第一个上级处停止。|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> 映射到 <xref:System.Windows.Forms.RightToLeft.No>。<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> 映射到 <xref:System.Windows.Forms.RightToLeft.Yes>。<br /><br /> 未映射 <xref:System.Windows.Forms.RightToLeft.Inherit>。<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> 映射到 <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>。|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> 寄宿控件的 <xref:System.Drawing.Font?displayProperty=nameWithType>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性集转换为相应的 <xref:System.Drawing.Font>。 其中一个属性发生更改时，将创建一个新的 <xref:System.Drawing.Font>。 对于 <xref:System.Windows.FontStyles.Normal%2A>： <xref:System.Drawing.FontStyle.Italic> 处于禁用状态。 对于 <xref:System.Windows.FontStyles.Italic%2A> 或 <xref:System.Windows.FontStyles.Oblique%2A>： <xref:System.Drawing.FontStyle.Italic> 已启用。|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> 寄宿控件的 <xref:System.Drawing.Font?displayProperty=nameWithType>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性集转换为相应的 <xref:System.Drawing.Font>。 其中一个属性发生更改时，将创建一个新的 <xref:System.Drawing.Font>。 对于 <xref:System.Windows.FontWeights.Black%2A>、<xref:System.Windows.FontWeights.Bold%2A>、<xref:System.Windows.FontWeights.DemiBold%2A>、<xref:System.Windows.FontWeights.ExtraBold%2A>、<xref:System.Windows.FontWeights.Heavy%2A>、<xref:System.Windows.FontWeights.Medium%2A>、<xref:System.Windows.FontWeights.SemiBold%2A>或 <xref:System.Windows.FontWeights.UltraBold%2A>： <xref:System.Drawing.FontStyle.Bold> 已启用。 对于 <xref:System.Windows.FontWeights.ExtraLight%2A>、<xref:System.Windows.FontWeights.Light%2A>、<xref:System.Windows.FontWeights.Normal%2A>、<xref:System.Windows.FontWeights.Regular%2A>、<xref:System.Windows.FontWeights.Thin%2A>或 <xref:System.Windows.FontWeights.UltraLight%2A>： <xref:System.Drawing.FontStyle.Bold> 处于禁用状态。|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性集转换为相应的 <xref:System.Drawing.Font>。 其中一个属性发生更改时，将创建一个新的 <xref:System.Drawing.Font>。 承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件根据字号调整大小。<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的字体大小表示为一英寸的九十-6，在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 中为一英寸的七十秒。 对应的转换为：<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 字号 = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 字体大小 * 72.0/96.0。|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|使用以下规则执行 <xref:System.Windows.Controls.Control.Foreground%2A> 属性映射：<br /><br /> -如果 <xref:System.Windows.Controls.Control.Foreground%2A> 是 <xref:System.Windows.Media.SolidColorBrush>，请使用 <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Forms.Control.ForeColor%2A>。<br />-如果 <xref:System.Windows.Controls.Control.Foreground%2A> 是 <xref:System.Windows.Media.GradientBrush>，请使用 <xref:System.Windows.Forms.Control.ForeColor%2A>的最小偏移值的 <xref:System.Windows.Media.GradientStop> 颜色。<br />-对于任何其他 <xref:System.Windows.Media.Brush> 类型，保持 <xref:System.Windows.Forms.Control.ForeColor%2A> 不变。 这意味着使用默认值。|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|设置 <xref:System.Windows.UIElement.IsEnabled%2A> 后，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素将设置承载控件上的 <xref:System.Windows.Forms.Control.Enabled%2A> 属性。|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上 <xref:System.Windows.Forms.Control.Padding%2A> 属性的所有四个值都设置为相同的 <xref:System.Windows.Thickness> 值。<br /><br /> -大于 <xref:System.Int32.MaxValue> 的值设置为 <xref:System.Int32.MaxValue>。<br />-小于 <xref:System.Int32.MinValue> 的值设置为 <xref:System.Int32.MinValue>。|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> 映射到 <xref:System.Windows.Forms.Control.Visible%2A> = `true`。 承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件可见。 不建议将寄宿控件上的 <xref:System.Windows.Forms.Control.Visible%2A> 属性显式设置为 "`false`"。<br />-   <xref:System.Windows.Visibility.Collapsed> 映射到 <xref:System.Windows.Forms.Control.Visible%2A> = `true` 或 `false`。 不绘制宿主 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件，其区域处于折叠状态。<br />-   <xref:System.Windows.Visibility.Hidden>：寄宿 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件占据布局中的空间，但不可见。 在这种情况下，<xref:System.Windows.Forms.Control.Visible%2A> 属性设置为 `true`。 不建议将寄宿控件上的 <xref:System.Windows.Forms.Control.Visible%2A> 属性显式设置为 "`false`"。|  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素完全支持容器元素上的附加属性。  
  
 有关详细信息，请参阅[演练：使用 System.windows.forms.integration.windowsformshost> 元素映射属性](walkthrough-mapping-properties-using-the-windowsformshost-element.md)。  
  
## <a name="updates-to-parent-properties"></a>父属性的更新  
 对大多数父属性的更改会导致对承载的子控件的通知。 以下列表描述了在其值更改时不会导致通知的属性。  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 例如，如果更改 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Controls.Control.Background%2A> 属性的值，则承载的控件的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性不会更改。  
  
## <a name="property-mapping-with-the-elementhost-control"></a>与 ElementHost 控件的属性映射  
 以下属性提供内置的更改通知。 映射这些属性时，请不要调用 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 方法：  
  
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
  
- Enabled  
  
- 字体  
  
- ForeColor  
  
- Location  
  
- 边距  
  
- 填充  
  
- 父级  
  
- Region  
  
- RightToLeft  
  
- 大小  
  
- TabIndex  
  
- TabStop  
  
- 文本  
  
- 可见  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 控件使用以下翻译表将默认 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 属性转换为其 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 等效项。  
  
 有关详细信息，请参阅[演练：使用 ElementHost 控件映射属性](walkthrough-mapping-properties-using-the-elementhost-control.md)。  
  
|Windows 窗体托管|Windows Presentation Foundation|互操作行为|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 托管元素上的（<xref:System.Windows.Media.Brush?displayProperty=nameWithType>）|设置此属性将强制使用 <xref:System.Windows.Media.ImageBrush>进行重绘。 如果 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 属性设置为 `false` （默认值），则此 <xref:System.Windows.Media.ImageBrush> 基于 <xref:System.Windows.Forms.Integration.ElementHost> 控件的外观，包括其 <xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.BackgroundImage%2A>、<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 属性和任何附加的 paint 处理程序。<br /><br /> 如果 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 属性设置为 `true`，则 <xref:System.Windows.Media.ImageBrush> 基于 <xref:System.Windows.Forms.Integration.ElementHost> 控件的父级的外观，包括父级的 <xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.BackgroundImage%2A>、<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 属性和任何附加的 paint 处理程序。|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 托管元素上的（<xref:System.Windows.Media.Brush?displayProperty=nameWithType>）|设置此属性将导致与 <xref:System.Windows.Forms.Control.BackColor%2A> 映射相同的行为。|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 托管元素上的（<xref:System.Windows.Media.Brush?displayProperty=nameWithType>）|设置此属性将导致与 <xref:System.Windows.Forms.Control.BackColor%2A> 映射相同的行为。|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 标准游标将转换为相应的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 标准光标。 如果 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 不是标准游标，则分配默认值。|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|设置 <xref:System.Windows.Forms.Control.Enabled%2A> 后，<xref:System.Windows.Forms.Integration.ElementHost> 控件将在承载的元素上设置 <xref:System.Windows.UIElement.IsEnabled%2A> 属性。|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A> 值转换为相应的一组 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的字体属性。|  
|<xref:System.Drawing.Font.Bold%2A>|寄宿元素上的 <xref:System.Windows.Controls.Control.FontWeight%2A>|如果 <xref:System.Drawing.Font.Bold%2A> 为 `true`，则 <xref:System.Windows.Controls.Control.FontWeight%2A> 设置为 <xref:System.Windows.FontWeights.Bold%2A>。<br /><br /> 如果 <xref:System.Drawing.Font.Bold%2A> 为 `false`，则 <xref:System.Windows.Controls.Control.FontWeight%2A> 设置为 <xref:System.Windows.FontWeights.Normal%2A>。|  
|<xref:System.Drawing.Font.Italic%2A>|寄宿元素上的 <xref:System.Windows.Controls.Control.FontStyle%2A>|如果 <xref:System.Drawing.Font.Italic%2A> 为 `true`，则 <xref:System.Windows.Controls.Control.FontStyle%2A> 设置为 <xref:System.Windows.FontStyles.Italic%2A>。<br /><br /> 如果 <xref:System.Drawing.Font.Italic%2A> 为 `false`，则 <xref:System.Windows.Controls.Control.FontStyle%2A> 设置为 <xref:System.Windows.FontStyles.Normal%2A>。|  
|<xref:System.Drawing.Font.Strikeout%2A>|寄宿元素上的 <xref:System.Windows.TextDecorations>|仅当承载 <xref:System.Windows.Controls.TextBlock> 控件时才适用。|  
|<xref:System.Drawing.Font.Underline%2A>|寄宿元素上的 <xref:System.Windows.TextDecorations>|仅当承载 <xref:System.Windows.Controls.TextBlock> 控件时才适用。|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> 映射到 <xref:System.Windows.FlowDirection.LeftToRight>。<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> 映射到 <xref:System.Windows.FlowDirection.RightToLeft>。|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost> 控件使用以下规则设置寄宿元素上的 <xref:System.Windows.UIElement.Visibility%2A> 属性：<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` 映射到 <xref:System.Windows.Visibility.Visible>。<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` 映射到 <xref:System.Windows.Visibility.Hidden>。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [WPF 和 Windows 窗体互操作](wpf-and-windows-forms-interoperation.md)
- [演练：使用 WindowsFormsHost 元素映射属性](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [演练：使用 ElementHost 控件映射属性](walkthrough-mapping-properties-using-the-elementhost-control.md)
