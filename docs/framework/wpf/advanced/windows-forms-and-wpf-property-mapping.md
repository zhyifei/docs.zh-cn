---
title: "Windows 窗体和 WPF 属性映射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 615d46b949a70c337204552b7bcf8b2934054b77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Windows 窗体和 WPF 属性映射
[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]技术具有两个相似但不同属性模型。 *属性映射*支持两种体系结构之间进行互操作，并提供以下功能：  
  
-   可以轻松将宿主环境中的相关属性更改映射到承载的控件或元素。  
  
-   提供使用默认处理映射最常用的属性。  
  
-   允许轻松删除，重写，或扩展的默认属性。  
  
-   确保主机上的属性值更改自动检测并转换为托管的控件或元素。  
  
> [!NOTE]
>  属性更改事件不会传播到宿主控件或元素层次结构。 如果属性的本地值不会更改由于直接设置、 样式、 继承、 数据绑定或更改属性的值的其他机制不会执行属性转换。  
  
 使用<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素和<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>属性<xref:System.Windows.Forms.Integration.ElementHost>控件，用于访问属性映射。  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>与 WindowsFormsHost 元素的属性映射  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素将转换默认[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性设置为其[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]使用以下转换表的等效项。  
  
|Windows Presentation Foundation 承载|Windows 窗体|互操作行为|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素集<xref:System.Windows.Forms.Control.BackColor%2A>所承载控件的属性和<xref:System.Windows.Forms.Control.BackgroundImage%2A>所承载控件的属性。 要执行映射，请使用以下规则：<br /><br /> -如果<xref:System.Windows.Controls.Control.Background%2A>是一种纯色，将它转换和用于设置<xref:System.Windows.Forms.Control.BackColor%2A>所承载控件的属性。 <xref:System.Windows.Forms.Control.BackColor%2A>由于托管的控件可以继承的值，因此未在托管控件上，设置属性<xref:System.Windows.Forms.Control.BackColor%2A>属性。 **注意：**所承载的控件不支持透明度。 分配给任何颜色<xref:System.Windows.Forms.Control.BackColor%2A>必须是完全不透明，alpha 值为 0xFF。 <br /><br /> -如果<xref:System.Windows.Controls.Control.Background%2A>不是一种纯色，<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件创建从一个位图<xref:System.Windows.Controls.Control.Background%2A>属性。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>控件将分配到此位图<xref:System.Windows.Forms.Control.BackgroundImage%2A>所承载控件的属性。 这提供了类似于透明度效果。 **注意：**可以重写此行为，或者可以删除<xref:System.Windows.Controls.Control.Background%2A>属性映射。|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|如果尚未重新分配的默认映射，<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件将遍历其上级层次结构直到找到包含上级其<xref:System.Windows.FrameworkElement.Cursor%2A>属性集。 此值将转换为最接近的对应[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]光标。<br /><br /> 如果的默认映射<xref:System.Windows.FrameworkElement.ForceCursor%2A>属性尚未重新分配，遍历停止上包含的第一个上级<xref:System.Windows.FrameworkElement.ForceCursor%2A>设置为`true`。|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> 映射到 <xref:System.Windows.Forms.RightToLeft.No>。<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> 映射到 <xref:System.Windows.Forms.RightToLeft.Yes>。<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>未映射。<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> 映射到 <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>。|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>对承载的控件<xref:System.Drawing.Font?displayProperty=nameWithType>|一套[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性转换为相应<xref:System.Drawing.Font>。 当其中一个属性更改时，新<xref:System.Drawing.Font>创建。 有关<xref:System.Windows.FontStyles.Normal%2A>:<xref:System.Drawing.FontStyle.Italic>处于禁用状态。 有关<xref:System.Windows.FontStyles.Italic%2A>或<xref:System.Windows.FontStyles.Oblique%2A>:<xref:System.Drawing.FontStyle.Italic>已启用。|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>对承载的控件<xref:System.Drawing.Font?displayProperty=nameWithType>|一套[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性转换为相应<xref:System.Drawing.Font>。 当其中一个属性更改时，新<xref:System.Drawing.Font>创建。 有关<xref:System.Windows.FontWeights.Black%2A>， <xref:System.Windows.FontWeights.Bold%2A>， <xref:System.Windows.FontWeights.DemiBold%2A>， <xref:System.Windows.FontWeights.ExtraBold%2A>， <xref:System.Windows.FontWeights.Heavy%2A>， <xref:System.Windows.FontWeights.Medium%2A>， <xref:System.Windows.FontWeights.SemiBold%2A>，或<xref:System.Windows.FontWeights.UltraBold%2A>:<xref:System.Drawing.FontStyle.Bold>已启用。 有关<xref:System.Windows.FontWeights.ExtraLight%2A>， <xref:System.Windows.FontWeights.Light%2A>， <xref:System.Windows.FontWeights.Normal%2A>， <xref:System.Windows.FontWeights.Regular%2A>， <xref:System.Windows.FontWeights.Thin%2A>，或<xref:System.Windows.FontWeights.UltraLight%2A>:<xref:System.Drawing.FontStyle.Bold>处于禁用状态。|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|一套[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性转换为相应<xref:System.Drawing.Font>。 当其中一个属性更改时，新<xref:System.Drawing.Font>创建。 将托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件将基于字体大小的调整大小。<br /><br /> 中的字体大小[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]表示为 96 英寸，并在[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]作为英寸的 72。 相应的转换是：<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]字体大小 =[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]字体大小 * 72.0 / 96.0。|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Foreground%2A>属性映射执行通过使用以下规则：<br /><br /> -如果<xref:System.Windows.Controls.Control.Foreground%2A>是<xref:System.Windows.Media.SolidColorBrush>，使用<xref:System.Windows.Media.SolidColorBrush.Color%2A>为<xref:System.Windows.Forms.Control.ForeColor%2A>。<br />-如果<xref:System.Windows.Controls.Control.Foreground%2A>是<xref:System.Windows.Media.GradientBrush>，使用的颜色<xref:System.Windows.Media.GradientStop>的最低的偏移量值与<xref:System.Windows.Forms.Control.ForeColor%2A>。<br />-对于任何其他<xref:System.Windows.Media.Brush>键入、 保持<xref:System.Windows.Forms.Control.ForeColor%2A>不变。 这意味着使用默认值。|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|当<xref:System.Windows.UIElement.IsEnabled%2A>设置，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素集<xref:System.Windows.Forms.Control.Enabled%2A>托管控件的属性。|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|所有四个值<xref:System.Windows.Forms.Control.Padding%2A>上托管的属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件设置为相同<xref:System.Windows.Thickness>值。<br /><br /> 值大于<xref:System.Int32.MaxValue>设置为<xref:System.Int32.MaxValue>。<br />的值小于<xref:System.Int32.MinValue>设置为<xref:System.Int32.MinValue>。|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>映射到<xref:System.Windows.Forms.Control.Visible%2A>  =  `true`。 将托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件是否可见。 显式设置<xref:System.Windows.Forms.Control.Visible%2A>到托管控件的属性`false`不建议。<br />-   <xref:System.Windows.Visibility.Collapsed>映射到<xref:System.Windows.Forms.Control.Visible%2A>  =  `true`或`false`。 将托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]不绘制控件，而其区域处于折叠状态。<br />-   <xref:System.Windows.Visibility.Hidden>： 将托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件占用空间在布局中，但不可见。 在这种情况下，<xref:System.Windows.Forms.Control.Visible%2A>属性设置为`true`。 显式设置<xref:System.Windows.Forms.Control.Visible%2A>到托管控件的属性`false`不建议。|  
  
 附加的属性上的容器元素完全受<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。  
  
 有关详细信息，请参阅[演练： 使用 WindowsFormsHost 元素的映射属性](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)。  
  
## <a name="updates-to-parent-properties"></a>更新到父属性  
 对大多数父属性的更改会导致通知给托管的子控件。 以下列表介绍其值更改时不会导致通知的属性。  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 例如，如果你更改的值<xref:System.Windows.Controls.Control.Background%2A>属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素，<xref:System.Windows.Forms.Control.BackColor%2A>所承载控件的属性不会更改。  
  
## <a name="property-mapping-with-the-elementhost-control"></a>使用 ElementHost 控件的属性映射  
 以下属性提供内置的更改通知。 不要调用<xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>映射这些属性的方法：  
  
-   AutoSize  
  
-   背景色  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   这  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursor  
  
-   停靠  
  
-   已启用  
  
-   字体  
  
-   前景色  
  
-   位置  
  
-   边距  
  
-   填充  
  
-   父级  
  
-   Region  
  
-   RightToLeft  
  
-   大小  
  
-   TabIndex  
  
-   制表位  
  
-   Text  
  
-   可见  
  
 <xref:System.Windows.Forms.Integration.ElementHost>控件将转换默认[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]属性设置为其[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通过使用以下转换表的等效项。  
  
 有关详细信息，请参阅[演练： 使用 ElementHost 控件映射属性](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)。  
  
|承载 Windows 窗体|Windows Presentation Foundation|互操作行为|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) 上承载的元素|设置此属性会强行与重绘<xref:System.Windows.Media.ImageBrush>。 如果<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>属性设置为`false`（默认值），这<xref:System.Windows.Media.ImageBrush>基于的外观<xref:System.Windows.Forms.Integration.ElementHost>控制，包括其<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>，<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>属性和任何附加的绘图处理程序。<br /><br /> 如果<xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>属性设置为`true`、<xref:System.Windows.Media.ImageBrush>基于的外观<xref:System.Windows.Forms.Integration.ElementHost>控件的父级，包括父<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>，<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>属性和任何附加的绘图处理程序。|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) 上承载的元素|设置此属性将导致所述的相同的行为<xref:System.Windows.Forms.Control.BackColor%2A>映射。|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) 上承载的元素|设置此属性将导致所述的相同的行为<xref:System.Windows.Forms.Control.BackColor%2A>映射。|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]标准光标将转换为相应[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]标准光标。 如果[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]不是标准的光标，分配默认值。|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|当<xref:System.Windows.Forms.Control.Enabled%2A>设置，<xref:System.Windows.Forms.Integration.ElementHost>控件将设置<xref:System.Windows.UIElement.IsEnabled%2A>上承载的元素的属性。|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A>值转换为对应的一组[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]字体属性。|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>上承载的元素|如果 <xref:System.Drawing.Font.Bold%2A> 为 `true`，则 <xref:System.Windows.Controls.Control.FontWeight%2A> 设置为 <xref:System.Windows.FontWeights.Bold%2A>。<br /><br /> 如果 <xref:System.Drawing.Font.Bold%2A> 为 `false`，则 <xref:System.Windows.Controls.Control.FontWeight%2A> 设置为 <xref:System.Windows.FontWeights.Normal%2A>。|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>上承载的元素|如果 <xref:System.Drawing.Font.Italic%2A> 为 `true`，则 <xref:System.Windows.Controls.Control.FontStyle%2A> 设置为 <xref:System.Windows.FontStyles.Italic%2A>。<br /><br /> 如果 <xref:System.Drawing.Font.Italic%2A> 为 `false`，则 <xref:System.Windows.Controls.Control.FontStyle%2A> 设置为 <xref:System.Windows.FontStyles.Normal%2A>。|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>上承载的元素|仅当承载时应用<xref:System.Windows.Controls.TextBlock>控件。|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>上承载的元素|仅当承载时应用<xref:System.Windows.Controls.TextBlock>控件。|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> 映射到 <xref:System.Windows.FlowDirection.LeftToRight>。<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> 映射到 <xref:System.Windows.FlowDirection.RightToLeft>。|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost>控件将设置<xref:System.Windows.UIElement.Visibility%2A>属性上承载的元素，通过使用以下规则：<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`映射到<xref:System.Windows.Visibility.Visible>。<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`映射到<xref:System.Windows.Visibility.Hidden>。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 和 Win32 互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [WPF 和 Windows 窗体互操作](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [演练：使用 WindowsFormsHost 元素映射属性](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)  
 [演练：使用 ElementHost 控件映射属性](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)
