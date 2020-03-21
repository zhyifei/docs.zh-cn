---
title: 面板概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: 7810bfbf4f5bedf51e0797a4b9017f589e0b0a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187582"
---
# <a name="panels-overview"></a>面板概述
<xref:System.Windows.Controls.Panel>元素是控制元素呈现的组件，其大小和尺寸、位置及其子内容的排列。 提供了[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]许多预定义<xref:System.Windows.Controls.Panel>元素以及构造自定义<xref:System.Windows.Controls.Panel>元素的能力。  
  
 本主题包含以下各节。  
  
- [Panel 类](#Panels_view_from_10000_feet)  
  
- [Panel 元素公共成员](#Panels_declared_members)  
  
- [派生 Panel 元素](#Panels_derived_elements)  
  
- [用户界面 Panel](#Panels_main_UI_elements)  
  
- [嵌套 Panel 元素](#Panels_nested_panel_elements)  
  
- [自定义 Panel 元素](#Panels_custom_panel_elements)  
  
- [本地化/全球化支持](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>
## <a name="the-panel-class"></a>Panel 类  
 <xref:System.Windows.Controls.Panel>是 提供 布局支持的所有元素的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]基类。 派生<xref:System.Windows.Controls.Panel>元素用于在 和 代码中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定位和排列元素。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包含一套全面的派生面板实现，可支持许多复杂的布局。 这些派生类公开可实现大部分标准 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 方案的属性和方法。 找不到满足其需求的子排列行为的开发人员可以通过重写<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法创建新布局。 有关自定义布局行为的详细信息，请参阅[自定义 Panel 元素](#Panels_custom_panel_elements)。  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Panel 公共成员  
 所有<xref:System.Windows.Controls.Panel>元素都支持由 定义的<xref:System.Windows.FrameworkElement>基大小调整和定位属性，包括<xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.FrameworkElement.Margin%2A>、、、、和<xref:System.Windows.FrameworkElement.LayoutTransform%2A>。 有关 定义的<xref:System.Windows.FrameworkElement>定位属性的其他信息，请参阅[对齐、边距和填充概述](../advanced/alignment-margins-and-padding-overview.md)。  
  
 <xref:System.Windows.Controls.Panel>公开对理解和使用布局至关重要的其他属性。 该<xref:System.Windows.Controls.Panel.Background%2A>属性用于使用 填充派生面板元素的边界之间的区域<xref:System.Windows.Media.Brush>。 <xref:System.Windows.Controls.Panel.Children%2A>表示 由 的元素的<xref:System.Windows.Controls.Panel>子集合。 <xref:System.Windows.Controls.Panel.InternalChildren%2A>表示<xref:System.Windows.Controls.Panel.Children%2A>集合的内容以及数据绑定生成的成员。 两者都由父<xref:System.Windows.Controls.UIElementCollection>级中托管的子元素组成<xref:System.Windows.Controls.Panel>。  
  
 面板还公开了一<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>个附加属性，该属性可用于在派生<xref:System.Windows.Controls.Panel>中实现分层顺序。 具有较高<xref:System.Windows.Controls.Panel.Children%2A><xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>值的面板集合的成员显示在值较低的<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>集合前面。 这对于允许子级共享相同坐标空间的<xref:System.Windows.Controls.Canvas><xref:System.Windows.Controls.Grid>面板特别有用。  
  
 <xref:System.Windows.Controls.Panel>还定义了<xref:System.Windows.Controls.Panel.OnRender%2A>方法，该方法可用于重写 的<xref:System.Windows.Controls.Panel>默认表示行为。  
  
#### <a name="attached-properties"></a>附加属性  
 派生面板元素广泛使用附加属性。 附加属性是依赖项属性的专用形式，没有常规通用语言运行时 （CLR） 属性"包装器"。 附加属性在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中具有特殊化的语法，可在后面的几个示例中看到。  
  
 附加属性的一个用途是允许子元素存储实际上由父元素定义的属性的唯一值。 此功能的一项应用是让子元素通知父级它们希望如何在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中呈现，这对应用程序布局非常有用。 有关详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>派生 Panel 元素  
 许多对象派生自<xref:System.Windows.Controls.Panel>，但并非所有对象都用作根布局提供程序。 有六个定义的面板类<xref:System.Windows.Controls.Canvas><xref:System.Windows.Controls.DockPanel>（、、、、、<xref:System.Windows.Controls.WrapPanel>[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]<xref:System.Windows.Controls.Grid><xref:System.Windows.Controls.StackPanel><xref:System.Windows.Controls.VirtualizingStackPanel>和 ）是专门为创建应用程序而设计的。  
  
 每个面板元素都封装自己的特殊功能，如下表所示。  
  
|元素名称|是否为 UI 面板？|说明|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|是|定义一个区域，您可以在其中通过相对于区域的<xref:System.Windows.Controls.Canvas>坐标显式定位子元素。|  
|<xref:System.Windows.Controls.DockPanel>|是|定义一个区域，从中可以按相对位置水平或垂直排列各个子元素。|  
|<xref:System.Windows.Controls.Grid>|是|定义一个由列和行组成的灵活网格区域。 的<xref:System.Windows.Controls.Grid>子元素可以使用 属性<xref:System.Windows.FrameworkElement.Margin%2A>精确定位。|  
|<xref:System.Windows.Controls.StackPanel>|是|将子元素排列成水平或垂直的一行。|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|否|处理 中的选项卡按钮的布局<xref:System.Windows.Controls.TabControl>。|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|否|在<xref:System.Windows.Controls.ToolBar>控件中排列内容。|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|否|<xref:System.Windows.Controls.Primitives.UniformGrid>用于在具有所有相同单元格大小的网格中排列子级。|  
|<xref:System.Windows.Controls.VirtualizingPanel>|否|为可以“虚拟化”其子级集合的面板提供基类。|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|是|在水平或垂直方向上将内容排列为一行并使其虚拟化。|  
|<xref:System.Windows.Controls.WrapPanel>|是|<xref:System.Windows.Controls.WrapPanel>将子元素从左向右定位为顺序位置，将内容分解到包含框边缘的下一行。 后续排序按顺序从上到下或从右向左进行，具体取决于<xref:System.Windows.Controls.WrapPanel.Orientation%2A>属性的值。|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>用户界面 Panel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]有[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]六个面板类可用于支持方案： <xref:System.Windows.Controls.Canvas>、 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>、 <xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.VirtualizingStackPanel>和<xref:System.Windows.Controls.WrapPanel>。 这些面板元素易于使用、功能齐全并且可扩展，足以适用于大多数应用程序。  
  
 每个派生<xref:System.Windows.Controls.Panel>元素都以不同的方式处理大小调整约束。 了解水平或<xref:System.Windows.Controls.Panel>垂直方向的句柄约束如何使布局更加可预测。  
  
|**面板名称**|**x 维度**|**y 维度**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|按内容约束|按内容约束|  
|<xref:System.Windows.Controls.DockPanel>|约束|约束|  
|<xref:System.Windows.Controls.StackPanel>（垂直方向）|约束|按内容约束|  
|<xref:System.Windows.Controls.StackPanel>（水平方向）|按内容约束|约束|  
|<xref:System.Windows.Controls.Grid>|约束|约束，但应用于行和<xref:System.Windows.GridUnitType.Auto>列的情况除外|  
|<xref:System.Windows.Controls.WrapPanel>|按内容约束|按内容约束|  
  
 可在下方找到其中每种元素的更多详细说明和使用示例。  
  
<a name="Panels_overview_Canvas_subsection"></a>
### <a name="canvas"></a>画布  
 该<xref:System.Windows.Controls.Canvas>元素允许根据绝对*x 和*y*坐标*定位内容。 元素可以在唯一位置绘制；或者，如果元素占用了相同坐标，则这些元素在标记中显示的顺序决定它们的绘制顺序。  
  
 <xref:System.Windows.Controls.Canvas>提供任何<xref:System.Windows.Controls.Panel>最灵活的布局支持。 高度和宽度属性用于定义画布的区域，其中的元素相对于父<xref:System.Windows.Controls.Canvas>区域分配绝对坐标。 四个附加属性<xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>和 允许精细控制对象放置在<xref:System.Windows.Controls.Canvas>， 允许开发人员在屏幕上精确定位和排列元素.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Canvas 内 ClipToBounds  
 <xref:System.Windows.Controls.Canvas>可以将子元素放置在屏幕上的任何位置，即使在超出其自身定义的<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>的坐标处也是如此。 此外，<xref:System.Windows.Controls.Canvas>不受其子女规模的影响。 因此，子元素可以透支父<xref:System.Windows.Controls.Canvas>矩形的边界矩形之外的其他元素。 的默认行为<xref:System.Windows.Controls.Canvas>是允许将子级绘制到父<xref:System.Windows.Controls.Canvas>项的边界之外。 如果此行为不可取，则可以<xref:System.Windows.UIElement.ClipToBounds%2A>将 属性设置为`true`。 这将导致<xref:System.Windows.Controls.Canvas>剪辑到其自己的大小。 <xref:System.Windows.Controls.Canvas>是唯一允许将子元素绘制在其边界之外的布局元素。  
  
 [宽度属性比较示例](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)中以图形方式展示了此行为。  
  
#### <a name="defining-and-using-a-canvas"></a>定义和使用 Canvas  
 <xref:System.Windows.Controls.Canvas>只需使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]或 代码即可实例化 。 下面的示例演示如何使用<xref:System.Windows.Controls.Canvas>来绝对定位内容。 此代码生成三个 100 像素正方形。 第一个正方形为红色，其左上角的 (*x, y*) 位置指定为 (0, 0)。 第二个正方形为绿色，其左上角位置为 (100, 100)，在第一个正方形的右下方。 第三个正方形为蓝色，其左上角为 (50, 50)，因此包含了第一个正方形的右下四分之一部分和第二个正方形的左上四分之一部分。 由于第三个正方形最后布置，因此它看起来在另外两个正方形上方，即，重叠部分采用第三个正方形的颜色。  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 Canvas 元素。](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 元素<xref:System.Windows.Controls.DockPanel>使用子内容<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>元素中设置的附加属性沿容器的边缘放置内容。 当<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>设置为<xref:System.Windows.Controls.Dock.Top>或<xref:System.Windows.Controls.Dock.Bottom>时，它将子元素分别位于或下方。 设置为<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType><xref:System.Windows.Controls.Dock.Left>或<xref:System.Windows.Controls.Dock.Right>时，它将子元素定位到彼此的左侧或右侧。 属性<xref:System.Windows.Controls.DockPanel.LastChildFill%2A>确定作为 的子元素添加的最终元素的位置<xref:System.Windows.Controls.DockPanel>。  
  
 可以使用<xref:System.Windows.Controls.DockPanel>来定位一组相关控件，如一组按钮。 或者，您可以使用它创建一个"平移"，类似于在[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Microsoft Outlook 中找到的"  
  
#### <a name="sizing-to-content"></a>按内容调整大小  
 如果未指定<xref:System.Windows.FrameworkElement.Height%2A>其<xref:System.Windows.FrameworkElement.Width%2A>和属性，则<xref:System.Windows.Controls.DockPanel>对其内容的大小。 大小可以增大或减小以容纳其子元素的大小。 但是，当指定这些属性并且不再具有下一个指定子元素的空间时，<xref:System.Windows.Controls.DockPanel>不会显示该子元素或后续子元素，并且不测量后续子元素。  
  
#### <a name="lastchildfill"></a>LastChildFill  
 默认情况下，元素的最后一个<xref:System.Windows.Controls.DockPanel>子级将"填充"剩余的未分配空间。 如果不需要此行为，则将<xref:System.Windows.Controls.DockPanel.LastChildFill%2A>属性设置为`false`。  
  
#### <a name="defining-and-using-a-dockpanel"></a>定义和使用 DockPanel  
 下面的示例演示如何使用 分区空间<xref:System.Windows.Controls.DockPanel>。 五<xref:System.Windows.Controls.Border>个元素作为父<xref:System.Windows.Controls.DockPanel>元素的子元素添加。 每个都使用不同的定位属性<xref:System.Windows.Controls.DockPanel>来分区空间。 最后一个元素"填充"剩余的未分配空间。  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 DockPanel 方案。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Grid  
 该<xref:System.Windows.Controls.Grid>元素合并了绝对定位和表格数据控制的功能。 A<xref:System.Windows.Controls.Grid>使您能够轻松定位和样式元素。 <xref:System.Windows.Controls.Grid>允许您定义灵活的行和列分组，甚至提供在多个<xref:System.Windows.Controls.Grid>元素之间共享大小调整信息的机制。  
  
#### <a name="how-is-grid-different-from-table"></a>网格与表格有何不同？  
 <xref:System.Windows.Documents.Table>并<xref:System.Windows.Controls.Grid>共享一些通用功能，但每个功能最适合不同的方案。 A<xref:System.Windows.Documents.Table>设计用于流内容中（有关流内容的详细信息，请参阅[流文档概述](../advanced/flow-document-overview.md)）。 网格最适合在表单中（主要在流内容以外的任意位置）使用。 在<xref:System.Windows.Documents.FlowDocument>中<xref:System.Windows.Documents.Table>，支持流内容行为，如分页、列重流和内容选择，而<xref:System.Windows.Controls.Grid>不支持。 另<xref:System.Windows.Controls.Grid>一方面，由于许多原因，包括<xref:System.Windows.Documents.FlowDocument><xref:System.Windows.Controls.Grid>添加基于行和列索引的元素，<xref:System.Windows.Documents.Table>最好在 外部使用。 该<xref:System.Windows.Controls.Grid>元素允许分层子内容，允许多个元素存在于单个"单元格"中。 <xref:System.Windows.Documents.Table>不支持分层。 子<xref:System.Windows.Controls.Grid>元素的子元素可以相对于其"单元格"边界区域绝对定位。 <xref:System.Windows.Documents.Table>不支持此功能。 最后，比<xref:System.Windows.Controls.Grid>的重量轻。 <xref:System.Windows.Documents.Table>  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>列和行的大小调整行为  
 在 中定义的列和<xref:System.Windows.Controls.Grid>行可以利用<xref:System.Windows.GridUnitType.Star>大小调整，以便按比例分配剩余空间。 当<xref:System.Windows.GridUnitType.Star>选择为行或列的高度或宽度时，该列或行将接收剩余可用空间的加权比例。 这与 相反<xref:System.Windows.GridUnitType.Auto>，后者将根据列或行中的内容大小均匀分布空间。 在使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 时，此值以 `*` 或 `2*` 的形式表示。 在第一种情况下，行或列将得到一倍的可用空间，在第二种情况下，将得到两倍的可用空间，依此类推。 通过将此技术与 和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A><xref:System.Windows.FrameworkElement.VerticalAlignment%2A>值`Stretch`按比例分配空间，可以按屏幕空间的百分比对布局空间进行分区。 <xref:System.Windows.Controls.Grid>是唯一可以以这种方式分配空间的布局面板。  
  
#### <a name="defining-and-using-a-grid"></a>定义和使用 Grid  
 下面的示例演示如何构建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]类似于 Windows 开始菜单上的"运行"对话框中找到的。  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的网格元素。](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 A<xref:System.Windows.Controls.StackPanel>使您能够在指定的方向"堆叠"元素。 默认堆叠方向为垂直方向。 该<xref:System.Windows.Controls.StackPanel.Orientation%2A>属性可用于控制内容流。  
  
#### <a name="stackpanel-vs-dockpanel"></a>堆栈面板与码头面板  
 虽然<xref:System.Windows.Controls.DockPanel>也可以"堆叠"子元素，<xref:System.Windows.Controls.DockPanel>并且<xref:System.Windows.Controls.StackPanel>在某些使用方案中不会产生类似的结果。 例如，子元素的顺序可能会影响其在 中<xref:System.Windows.Controls.DockPanel>的大小，但不能在 中。 <xref:System.Windows.Controls.StackPanel> 这是因为<xref:System.Windows.Controls.StackPanel>在 的堆叠方向度量<xref:System.Double.PositiveInfinity>，而<xref:System.Windows.Controls.DockPanel>仅测量可用大小。  
  
 以下示例演示此主要区别。  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 通过此图像可以看到呈现行为的区别。  
  
 ![屏幕快照：StackPanel 与 DockPanel 对比屏幕快照](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>定义和使用 StackPanel  
 下面的示例演示如何使用<xref:System.Windows.Controls.StackPanel>创建一组垂直定位的按钮。 对于水平定位，将<xref:System.Windows.Controls.StackPanel.Orientation%2A>属性设置为<xref:System.Windows.Controls.Orientation.Horizontal>。  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 StackPanel 元素。](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]还提供了自动"虚拟化"<xref:System.Windows.Controls.StackPanel>数据绑定子内容的元素的变体。 在此上下文中，“虚拟化”一词指的是一种技术：通过此技术根据屏幕上哪些项可见，从较多的数据项中生成一个元素子集。 如果在指定时刻只有少量 UI 元素位于屏幕上，则此时生成大量 UI 元素需要占用大量内存和处理器。 <xref:System.Windows.Controls.VirtualizingStackPanel>（通过<xref:System.Windows.Controls.VirtualizingPanel>提供的功能计算可见项，并与<xref:System.Windows.Controls.ItemContainerGenerator>从<xref:System.Windows.Controls.ItemsControl>（如<xref:System.Windows.Controls.ListBox>）<xref:System.Windows.Controls.ListView>到仅为可见项创建元素。  
  
 元素<xref:System.Windows.Controls.VirtualizingStackPanel>将自动设置为控件（如 ）<xref:System.Windows.Controls.ListBox>的项主机。 托管数据绑定集合时，只要内容在 的边界内，内容就会自动虚拟化<xref:System.Windows.Controls.ScrollViewer>。 在承载许多子项时，这将大幅提高性能。  
  
 以下标记演示如何将 用作<xref:System.Windows.Controls.VirtualizingStackPanel>项目主机。 必须<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType>将附加属性设置为`true`（默认）才能进行虚拟化。  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>用于将子元素从左到右定位在顺序位置，当它到达其父容器的边缘时，将内容分解到下一行。 内容可以设置为水平或垂直方向。 <xref:System.Windows.Controls.WrapPanel>对于简单的流动[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]方案很有用。 它还可以用来将统一大小调整应用于其所有子元素。  
  
 下面的示例演示如何创建<xref:System.Windows.Controls.WrapPanel>以显示<xref:System.Windows.Controls.Button>在到达容器边缘时换行的控件。  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 WrapPanel 元素。](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>嵌套 Panel 元素  
 <xref:System.Windows.Controls.Panel>元素可以嵌套在彼此中，以便生成复杂的布局。 这可以证明非常有用的情况下，一个是<xref:System.Windows.Controls.Panel>理想的部分[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，但可能不能满足不同部分的需要。 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
 对于应用程序可以支持的嵌套数量，并没有实际限制，但通常最好限制应用程序仅使用预期布局实际所需的面板。 在许多情况下，<xref:System.Windows.Controls.Grid>元素作为布局容器的灵活性，可以使用元素而不是嵌套面板。 这可以通过将不必要的元素排除在树以外来提高应用程序的性能。  
  
 下面的示例演示如何创建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]利用嵌套<xref:System.Windows.Controls.Panel>元素来实现特定布局的 。 在此<xref:System.Windows.Controls.DockPanel>特定情况下，元素用于提供[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]结构，嵌套<xref:System.Windows.Controls.StackPanel>元素 、a<xref:System.Windows.Controls.Grid>和 a<xref:System.Windows.Controls.Canvas>用于精确地将子元素放置在父<xref:System.Windows.Controls.DockPanel>元素 中。  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![利用嵌套面板的 UI。](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>自定义 Panel 元素  
 虽然[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供了一系列灵活的布局控件，但自定义布局行为也可以通过重写<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法来实现。 可以通过在这些重写方法内定义新的位置行为来实现自定义大小调整和位置。  
  
 同样，<xref:System.Windows.Controls.Canvas>基于派生类（如 或<xref:System.Windows.Controls.Grid>）的自定义布局行为可以通过重写其<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和方法<xref:System.Windows.FrameworkElement.MeasureOverride%2A>来定义。  
  
 下面的标记演示如何创建自定义<xref:System.Windows.Controls.Panel>元素。 这种定义为<xref:System.Windows.Controls.Panel>的新，`PlotPanel`支持使用硬编码*的x和**y*坐标定位子元素。 在此示例中，<xref:System.Windows.Shapes.Rectangle>元素（未显示）位于绘图点 50 *（x*） 和 50 *（y*） 处。  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 若要查看更复杂的自定义面板实现，请参阅[创建自定义内容换行面板示例](https://go.microsoft.com/fwlink/?LinkID=159979)。  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>本地化/全球化支持  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 支持多种有助于创建可本地化的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的功能。  
  
 所有面板元素都本机支持该<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性，该属性可用于根据用户的区域设置或语言设置动态重新流内容。 有关详细信息，请参阅 <xref:System.Windows.FrameworkElement.FlowDirection%2A>。  
  
 该<xref:System.Windows.Window.SizeToContent%2A>属性提供了一种机制，使应用程序开发人员能够预测本地化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的需求。 使用此属性<xref:System.Windows.SizeToContent.WidthAndHeight>的值，父级<xref:System.Windows.Window>始终动态调整大小以适合内容，并且不受人工高度或宽度限制的限制。  
  
 <xref:System.Windows.Controls.DockPanel>，<xref:System.Windows.Controls.Grid>并且<xref:System.Windows.Controls.StackPanel>都是可[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]本地化的好选择。 <xref:System.Windows.Controls.Canvas>然而，这不是一个不错的选择，因为它绝对定位内容，使得本地化变得困难。  
  
 有关使用可本地化用户界面[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]（UI） 创建应用程序的其他信息，请参阅[使用自动布局概述](../advanced/use-automatic-layout-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [WPF 布局库示例](https://go.microsoft.com/fwlink/?LinkID=160054)
- [布局](../advanced/layout.md)
- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
- [Alignment、Margin 和 Padding 概述](../advanced/alignment-margins-and-padding-overview.md)
- [创建自定义内容换行面板示例](https://go.microsoft.com/fwlink/?LinkID=159979)
- [附加属性概述](../advanced/attached-properties-overview.md)
- [使用自动布局概述](../advanced/use-automatic-layout-overview.md)
- [布局和设计](../advanced/optimizing-performance-layout-and-design.md)
