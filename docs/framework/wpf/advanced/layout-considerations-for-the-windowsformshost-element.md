---
title: WindowsFormsHost 元素的布局注意事项
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 786e3adae6c5b8167fbba00aa140d4d728308dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548922"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>WindowsFormsHost 元素的布局注意事项
本主题介绍如何<xref:System.Windows.Forms.Integration.WindowsFormsHost>与交互元素[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局系统。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]支持不同，但类似的逻辑大小和位置上窗体或页面的元素。 当你创建混合用户界面 (UI) 承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中控制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素集成两种布局方案。  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>WPF 和 Windows 窗体之间的布局差异  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用独立于解析的布局。 所有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局维度使用指定*设备无关的像素*。 独立于设备的像素是在大小和分辨率无关英寸的 96，因此获取无论您 72 dpi 监视器或 19200 dpi 打印机上呈现，均类似的结果。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 此外基于*动态布局*。 这意味着 UI 元素会在窗体或根据其内容、 其父布局容器和可用的屏幕大小的页面上排列本身。 动态布局协助进行本地化，通过它们所包含的字符串改变长度时自动调整大小和 UI 元素的位置。  
  
 中的布局[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]是设备相关，很可能是静态的。 通常情况下，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件绝对方式来定位使用硬件以像素为单位的维度的窗体上。 但是，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]支持某些动态布局功能下, 表中进行了总结。  
  
|布局功能|描述|  
|--------------------|-----------------|  
|自动调整大小|某些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件调整大小以正确显示其内容。 有关详细信息，请参阅[AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)。|  
|锚定和停靠|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件支持定位和基于父容器的大小。 有关详细信息，请参阅 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>。|  
|自动缩放|容器控件来调整自身其子根据输出设备或的大小，以像素为单位，默认容器字体的分辨率。 有关详细信息，请参阅[Windows 窗体中的自动缩放](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)。|  
|布局容器|<xref:System.Windows.Forms.FlowLayoutPanel>和<xref:System.Windows.Forms.TableLayoutPanel>控件排列及其子控件，并根据其内容调整大小。|  
  
## <a name="layout-limitations"></a>布局限制  
 一般情况下，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]不能缩放控件，并将其转换为中可能的范围[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 以下列表介绍的已知的限制时<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素尝试将集成其托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局系统。  
  
-   某些情况下，不能调整 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的大小，或者大小只能调整为特定尺寸。 例如， [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox>控件支持仅单个高度由控件的字体大小定义。 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]其中元素可以拉伸垂直，一个承载的动态布局<xref:System.Windows.Forms.ComboBox>控件不会按预期方式拉伸。  
  
-   不能旋转或扭曲 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素引发<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>事件，如果将应用扭曲或旋转转换。 如果不处理<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>事件，<xref:System.InvalidOperationException>引发。  
  
-   大多数情况下，[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件不支持按比例缩放。 尽管该控件的整体尺寸将会缩放，但其子控件和组件元素可能不会按预期调整大小。 此限制取决于每个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件支持缩放的程度。 此外，不能缩放[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]缩小到 0 像素的小时的控件。  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件支持自动缩放，在其中窗体将自动调整自身的字号基于其控件。 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，更改字号不会改变整个布局的大小，但是可动态调整单个元素的大小。  
  
### <a name="z-order"></a>Z 顺序  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，可以更改元素的 z 顺序以控制重叠行为。 由于承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件是在单独的 HWND 中绘制的，所以始终在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素之上绘制它。  
  
 一个承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]基于任何还绘制控件<xref:System.Windows.Documents.Adorner>元素。  
  
## <a name="layout-behavior"></a>布局行为  
 以下各节描述了布局行为的特定方面，承载时[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中控制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>缩放、 单位转换和设备独立性  
 每当<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素执行操作涉及[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]涉及维度，两个坐标系： 独立于设备的像素[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和硬件像素[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。 因此，你必须应用适当的单位和缩放转换，以实现一致的布局。  
  
 坐标系统之间的转换取决于当前的设备分辨率和任何布局或呈现转换应用于<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素或其上级。  
  
 如果输出设备为 96 dpi，而不缩放已应用到<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素，一个独立于设备的像素等同于一个硬件像素。  
  
 所有其他情况下需要坐标系统缩放。 托管的控件不调整大小。 相反，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素尝试来缩放所承载的控件及其所有子控件。 因为[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]不完全支持缩放，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素可以扩展到由特定控件支持的程度。  
  
 重写<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A>方法以提供用于承载 Windows 窗体控件的自定义缩放行为。  
  
 除了向外，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素处理舍入和溢出的情况下下, 表中所述。  
  
|转换问题|描述|  
|----------------------|-----------------|  
|舍入|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 独立于设备的像素大小指定为`double`，和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]硬件像素大小指定为`int`。 在情况下其中`double`-基于的维度转换为`int`-基于维度，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用标准的舍入，以便小于 0.5 的小数部分的值是向下舍入为 0。|  
|溢出|当<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素将从转换`double`值复制到`int`值，可能会溢出。 值大于<xref:System.Int32.MaxValue>设置为<xref:System.Int32.MaxValue>。|  
  
### <a name="layout-related-properties"></a>布局相关的属性  
 控制布局中的行为的属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]适当地通过映射元素<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="layout-changes-in-the-hosted-control"></a>托管控件中的布局更改  
 中托管的布局更改[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件传播到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]以触发布局更新。 <xref:System.Windows.UIElement.InvalidateMeasure%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>确保托管控件中的布局更改会导致[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局引擎运行。  
  
### <a name="continuously-sized-windows-forms-controls"></a>连续大小 Windows 窗体控件  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 与控件支持连续伸缩完全交互[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局系统。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用<xref:System.Windows.FrameworkElement.MeasureOverride%2A>和<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>方法像往常一样来调整和排列托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。  
  
### <a name="sizing-algorithm"></a>大小调整算法  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用以下过程来托管的控件的大小：  
  
1.  <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素会替代<xref:System.Windows.FrameworkElement.MeasureOverride%2A>和<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>方法。  
  
2.  若要确定所承载控件的大小<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法调用托管的控件的<xref:System.Windows.Forms.Control.GetPreferredSize%2A>带有约束方法转换从传递给约束<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。  
  
3.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>方法尝试将托管的控件设置为给定的大小约束。  
  
4.  如果托管的控件的<xref:System.Windows.Forms.Control.Size%2A>属性匹配的指定的约束，托管的控件的大小为约束大小。  
  
 如果<xref:System.Windows.Forms.Control.Size%2A>属性与指定的约束不匹配，托管的控件不支持连续调整大小。 例如，<xref:System.Windows.Forms.MonthCalendar>控件，可以仅离散的大小。 对于此控件的允许的大小包含高度和宽度的整数 （表示的月数）。 在此情况下<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的行为，如下所示：  
  
-   如果<xref:System.Windows.Forms.Control.Size%2A>属性返回更大的大小大于指定的约束，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素裁剪所承载的控件。 高度和宽度将单独处理，因此承载的控件可能会剪裁在任一方向。  
  
-   如果<xref:System.Windows.Forms.Control.Size%2A>属性返回较小的大小大于指定的约束，<xref:System.Windows.Forms.Integration.WindowsFormsHost>接受此大小值，并返回到值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局系统。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [演练：在 WPF 中排列 Windows 窗体控件](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [排列 Windows 窗体控件在 WPF 示例](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Windows 窗体和 WPF 属性映射](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [迁移和互操作性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
