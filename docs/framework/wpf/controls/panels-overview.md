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
ms.openlocfilehash: d77ce78fe914bf300c5b33019d7cf67aa4ad74c3
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291457"
---
# <a name="panels-overview"></a>面板概述
<xref:System.Windows.Controls.Panel> 元素是控制元素呈现（其大小和尺寸、其位置以及其子内容排列）的组件。 @No__t 提供了许多预定义的 @no__t 个元素以及构造自定义的 <xref:System.Windows.Controls.Panel> 元素的功能。  
  
 本主题包含以下各节：  
  
- [Panel 类](#Panels_view_from_10000_feet)  
  
- [Panel 元素公共成员](#Panels_declared_members)  
  
- [派生 Panel 元素](#Panels_derived_elements)  
  
- [用户界面 Panel](#Panels_main_UI_elements)  
  
- [嵌套 Panel 元素](#Panels_nested_panel_elements)  
  
- [自定义 Panel 元素](#Panels_custom_panel_elements)  
  
- [本地化/全球化支持](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Panel 类  
 @no__t 为 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中提供布局支持的所有元素的基类。 派生 <xref:System.Windows.Controls.Panel> 元素用于在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 和代码中放置和排列元素。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包含一套全面的派生面板实现，可支持许多复杂的布局。 这些派生类公开可实现大部分标准 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 方案的属性和方法。 找不到满足其需求的子排列行为的开发人员可以通过重写 @no__t 0 和 @no__t 1 方法来创建新的布局。 有关自定义布局行为的详细信息，请参阅[自定义 Panel 元素](#Panels_custom_panel_elements)。  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Panel 公共成员  
 所有 @no__t 0 元素都支持 @no__t 定义的基本大小调整和定位属性，包括 <xref:System.Windows.FrameworkElement.Height%2A>、<xref:System.Windows.FrameworkElement.Width%2A>、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>、<xref:System.Windows.FrameworkElement.Margin%2A> 和 @no__t。 有关 <xref:System.Windows.FrameworkElement> 定义的定位属性的其他信息，请参阅[对齐、边距和填充概述](../advanced/alignment-margins-and-padding-overview.md)。  
  
 <xref:System.Windows.Controls.Panel> 公开了了解和使用布局的重要重要性的其他属性。 @No__t-0 属性用于填充派生面板元素边界之间的区域，@no__t 为-1。 <xref:System.Windows.Controls.Panel.Children%2A> 表示 @no__t 为-1 的元素的子集合。 <xref:System.Windows.Controls.Panel.InternalChildren%2A> 表示 @no__t 集合的内容以及由数据绑定生成的成员。 两者均由父级 @no__t 中托管的 @no__t 0 的子元素组成。  
  
 面板还公开了一个 @no__t 0 附加属性，该属性可用于在派生 <xref:System.Windows.Controls.Panel> 中实现分层顺序。 具有更高 @no__t 值的面板的 @no__t 0 集合的成员将显示在具有较低 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> 值的面板上。 这对于诸如 @no__t 的面板和 <xref:System.Windows.Controls.Grid> （允许儿童共享同一坐标空间）特别有用。  
  
 @no__t 还定义了 <xref:System.Windows.Controls.Panel.OnRender%2A> 方法，该方法可用于重写 @no__t 的默认呈现行为。  
  
#### <a name="attached-properties"></a>附加属性  
 派生面板元素广泛使用附加属性。 附加属性是一种专用化的依赖项属性，不具有传统的公共语言运行时（CLR）属性 "包装器"。 附加属性在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中具有特殊化的语法，可在后面的几个示例中看到。  
  
 附加属性的一个用途是允许子元素存储实际上由父元素定义的属性的唯一值。 此功能的一项应用是让子元素通知父级它们希望如何在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中呈现，这对应用程序布局非常有用。 有关详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>派生 Panel 元素  
 许多对象都派生自 <xref:System.Windows.Controls.Panel>，但并不是所有对象都要用作根布局提供程序。 有六个已定义的面板类（<xref:System.Windows.Controls.Canvas>、<xref:System.Windows.Controls.DockPanel>、<xref:System.Windows.Controls.Grid>、<xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.VirtualizingStackPanel> 和 <xref:System.Windows.Controls.WrapPanel>）专门用于创建应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 每个面板元素都封装自己的特殊功能，如下表所示。  
  
|元素名称|是否为 UI 面板？|描述|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|是|定义一个区域，可在其中按相对于 @no__t 0 区域的坐标显式定位子元素。|  
|<xref:System.Windows.Controls.DockPanel>|是|定义一个区域，可在其中使子元素相互水平或垂直排列。|  
|<xref:System.Windows.Controls.Grid>|是|定义一个由列和行组成的灵活网格区域。 使用 @no__t 的属性可以精确定位 <xref:System.Windows.Controls.Grid> 的子元素。|  
|<xref:System.Windows.Controls.StackPanel>|是|将子元素排列成水平或垂直的一行。|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|否|处理 <xref:System.Windows.Controls.TabControl> 中选项卡按钮的布局。|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|否|在 <xref:System.Windows.Controls.ToolBar> 控件内排列内容。|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|否|<xref:System.Windows.Controls.Primitives.UniformGrid> 用于在网格中的所有单元格大小相等的情况排列子元素。|  
|<xref:System.Windows.Controls.VirtualizingPanel>|否|为可以“虚拟化”其子级集合的面板提供基类。|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|是|在水平或垂直方向上将内容排列为一行并使其虚拟化。|  
|<xref:System.Windows.Controls.WrapPanel>|是|<xref:System.Windows.Controls.WrapPanel> 按从左至右的顺序位置定位子元素，在包含框的边缘处将内容分解到下一行。 后续排序按从上到下或从右到左的顺序进行，具体取决于 @no__t 值为0的属性的值。|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>用户界面 Panel  
 @No__t-0 中提供了六个面板类，这些面板类经过优化，可支持 @no__t 方案： <xref:System.Windows.Controls.Canvas>、<xref:System.Windows.Controls.DockPanel>、<xref:System.Windows.Controls.Grid>、<xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.VirtualizingStackPanel> 和 @no__t 7。 这些面板元素易于使用、功能齐全并且可扩展，足以适用于大多数应用程序。  
  
 每个派生 @no__t 0 元素都以不同方式处理大小约束。 了解 <xref:System.Windows.Controls.Panel> 如何在水平方向或垂直方向处理约束可以使布局更具可预测性。  
  
|**Panel 名称**|**x 维度**|**y 维度**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|按内容约束|按内容约束|  
|<xref:System.Windows.Controls.DockPanel>|约束|约束|  
|<xref:System.Windows.Controls.StackPanel> （垂直方向）|约束|按内容约束|  
|<xref:System.Windows.Controls.StackPanel> （水平方向）|按内容约束|约束|  
|<xref:System.Windows.Controls.Grid>|约束|受约束，在 <xref:System.Windows.GridUnitType.Auto> 应用于行和列的情况下除外|  
|<xref:System.Windows.Controls.WrapPanel>|按内容约束|按内容约束|  
  
 可在下方找到其中每种元素的更多详细说明和使用示例。  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 @No__t-0 元素可根据绝对*x*和*y*坐标定位内容。 元素可以在唯一位置绘制；或者，如果元素占用了相同坐标，则这些元素在标记中显示的顺序决定它们的绘制顺序。  
  
 @no__t 为任何 @no__t 提供最灵活的布局支持。 "高度" 和 "宽度" 属性用于定义画布的面积，并为内的元素分配相对于父级 @no__t 的区域的绝对坐标。 四个附加属性 <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> 和 @no__t 3）允许在 @no__t 中精确控制对象位置，使开发人员能够在屏幕上精确地放置和排列元素。  
  
#### <a name="cliptobounds-within-a-canvas"></a>Canvas 内 ClipToBounds  
 <xref:System.Windows.Controls.Canvas> 可以将子元素定位在屏幕上的任意位置，甚至可以定位在其自身定义的 <xref:System.Windows.FrameworkElement.Height%2A> 和 <xref:System.Windows.FrameworkElement.Width%2A> 之外的坐标。 此外，@no__t 0 不受其子级的大小的影响。 因此，子元素可以过度绘制父级 <xref:System.Windows.Controls.Canvas> 的边框外的其他元素。 @No__t 的默认行为是允许在父 <xref:System.Windows.Controls.Canvas> 的边界之外绘制子级。 如果不需要此行为，可以将 <xref:System.Windows.UIElement.ClipToBounds%2A> 属性设置为 `true`。 这会导致 <xref:System.Windows.Controls.Canvas> 剪辑到其自身大小。 @no__t 为唯一的布局元素，它允许在其边界外绘制子级。  
  
 [宽度属性比较示例](https://go.microsoft.com/fwlink/?LinkID=160050)中以图形方式展示了此行为。  
  
#### <a name="defining-and-using-a-canvas"></a>定义和使用 Canvas  
 只需使用 @no__t 或代码，即可实例化 <xref:System.Windows.Controls.Canvas>。 下面的示例演示如何使用 <xref:System.Windows.Controls.Canvas> 来绝对定位内容。 此代码生成三个 100 像素正方形。 第一个正方形为红色，其左上角的 (*x, y*) 位置指定为 (0, 0)。 第二个正方形为绿色，其左上角位置为 (100, 100)，在第一个正方形的右下方。 第三个正方形为蓝色，其左上角为 (50, 50)，因此包含了第一个正方形的右下四分之一部分和第二个正方形的左上四分之一部分。 由于第三个正方形最后布置，因此它看起来在另外两个正方形上方，即，重叠部分采用第三个正方形的颜色。  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 Canvas 元素。](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 @No__t-0 元素使用在子 content 元素中设置的 @no__t 1 附加属性，沿容器边缘放置内容。 当 @no__t 设置为 <xref:System.Windows.Controls.Dock.Top> 或 <xref:System.Windows.Controls.Dock.Bottom> 时，它会将子元素定位在其上方或下方。 当 @no__t 设置为 <xref:System.Windows.Controls.Dock.Left> 或 <xref:System.Windows.Controls.Dock.Right> 时，它会将子元素定位到彼此的左侧或右侧。 @No__t-0 属性确定作为 @no__t 的子项添加的最后一个元素的位置。  
  
 您可以使用 <xref:System.Windows.Controls.DockPanel> 来定位一组相关的控件，例如一组按钮。 或者，可以使用它来创建 "平移" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，与在 Microsoft Outlook 中找到的内容类似。  
  
#### <a name="sizing-to-content"></a>按内容调整大小  
 如果未指定其 <xref:System.Windows.FrameworkElement.Height%2A> 和 <xref:System.Windows.FrameworkElement.Width%2A> 属性，则 @no__t 为其内容的2个大小。 大小可以增大或减小以容纳其子元素的大小。 但是，如果指定了这些属性，但没有足够的空间用于下一个指定的子元素，<xref:System.Windows.Controls.DockPanel> 不会显示该子元素或后续的子元素，也不会度量后续的子元素。  
  
#### <a name="lastchildfill"></a>LastChildFill  
 默认情况下，<xref:System.Windows.Controls.DockPanel> 元素的最后一个子元素将 "填充" 剩余的未分配空间。 如果不需要此行为，请将 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 属性设置为 `false`。  
  
#### <a name="defining-and-using-a-dockpanel"></a>定义和使用 DockPanel  
 下面的示例演示如何使用 <xref:System.Windows.Controls.DockPanel> 对空间进行分区。 五个 <xref:System.Windows.Controls.Border> 元素作为父级 @no__t 的子级添加。 每个都使用不同的 @no__t 0 的定位属性来分区空间。 最后一个元素"填充"剩余的未分配空间。  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 DockPanel 方案。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Grid  
 @No__t 0 元素合并绝对定位和表格数据控件的功能。 @No__t-0 使你能够轻松地定位和样式元素。 <xref:System.Windows.Controls.Grid> 允许定义灵活的行和列分组，甚至提供一种机制，用于在多个 @no__t 元素之间共享大小调整信息。  
  
#### <a name="how-is-grid-different-from-table"></a>网格与表格有何不同？  
 <xref:System.Windows.Documents.Table> 和 <xref:System.Windows.Controls.Grid> 共享某些常见功能，但每个功能最适合于不同的方案。 @No__t-0 设计为在流内容中使用（有关流内容的详细信息，请参阅[流文档概述](../advanced/flow-document-overview.md)）。 网格最适合在表单内（主要在流内容以外的任意位置）使用。 在 <xref:System.Windows.Documents.FlowDocument> 中，<xref:System.Windows.Documents.Table> 支持流内容行为，如分页、列重排和内容选择，而 <xref:System.Windows.Controls.Grid> 则不支持。 另一方面，<xref:System.Windows.Controls.Grid> 在 @no__t 的范围内最适用的原因有很多，包括 <xref:System.Windows.Controls.Grid> 基于行和列索引添加元素，而不是 <xref:System.Windows.Documents.Table>。 @No__t-0 元素允许将子内容分层，允许多个元素存在于单个 "单元" 中。 <xref:System.Windows.Documents.Table> 不支持分层。 @No__t-0 的子元素可相对于其 "单元格" 边界区域进行绝对定位。 <xref:System.Windows.Documents.Table> 不支持此功能。 最后，<xref:System.Windows.Controls.Grid> 比 @no__t 的权重更轻。  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>列和行的大小调整行为  
 在 @no__t 中定义的列和行可以利用 @no__t 的大小调整，以便按比例分配剩余空间。 如果选择 <xref:System.Windows.GridUnitType.Star> 作为行或列的高度或宽度，则该列或行将接收剩余可用空间的加权比例。 这与 <xref:System.Windows.GridUnitType.Auto> 相反，它会根据列或行中内容的大小均匀分配空间。 在使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 时，此值以 `*` 或 `2*` 的形式表示。 在第一种情况下，行或列将得到一倍的可用空间，在第二种情况下，将得到两倍的可用空间，依此类推。 通过将此方法与 @no__t 的 @no__t 0 和 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 值组合在一起可以按比例分配空间，可以按屏幕空间百分比分区布局空间。 <xref:System.Windows.Controls.Grid> 是唯一可以采用这种方式分布空间的布局面板。  
  
#### <a name="defining-and-using-a-grid"></a>定义和使用 Grid  
 下面的示例演示如何生成与在 Windows "开始" 菜单上提供的 "运行" 对话框中找到的 @no__t。  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 Grid 元素。](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 @No__t-0 使你可以按分配的方向 "stack" 元素。 默认堆叠方向为垂直方向。 @No__t-0 属性可用于控制内容流。  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel 与 DockPanel  
 尽管 @no__t 还可以 "stack" 子元素，<xref:System.Windows.Controls.DockPanel> 和 <xref:System.Windows.Controls.StackPanel> 在某些使用方案中不产生类似的结果。 例如，子元素的顺序会影响其在 <xref:System.Windows.Controls.DockPanel> 中，但不在 <xref:System.Windows.Controls.StackPanel> 中的大小。 这是因为 <xref:System.Windows.Controls.StackPanel> 按 @no__t 的堆栈方向测量，而 @no__t 2 仅度量可用大小。  
  
 以下示例演示此主要区别。  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 通过此图像可以看到呈现行为的区别。  
  
 ![Screenshot：StackPanel 与 DockPanel 屏幕截图](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>定义和使用 StackPanel  
 下面的示例演示如何使用 <xref:System.Windows.Controls.StackPanel> 创建一组垂直定位的按钮。 对于水平定位，将 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 属性设置为 <xref:System.Windows.Controls.Orientation.Horizontal>。  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 StackPanel 元素。](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 @no__t 还提供了 <xref:System.Windows.Controls.StackPanel> 元素的变体，该元素自动 "虚拟化" 数据绑定的子内容。 在此上下文中，“虚拟化”一词指的是一种技术：通过此技术根据屏幕上哪些项可见，从较多的数据项中生成一个元素子集。 如果在指定时刻只有少量 UI 元素位于屏幕上，则此时生成大量 UI 元素需要占用大量内存和处理器。 <xref:System.Windows.Controls.VirtualizingStackPanel> （通过 @no__t 提供的功能）计算可见项，并与 @no__t 3 中的 @no__t （例如 <xref:System.Windows.Controls.ListBox> 或 <xref:System.Windows.Controls.ListView>）一起使用，以仅为可见项创建元素。  
  
 @No__t-0 元素自动设置为控件的宿主，如 @no__t。 承载数据绑定集合时，只要内容在 @no__t 的边界内，就会自动虚拟化内容。 在承载许多子项时，这将大幅提高性能。  
  
 下面的标记演示了如何使用 <xref:System.Windows.Controls.VirtualizingStackPanel> 作为项宿主。 必须将 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> 附加属性设置为 `true` （默认值），才能进行虚拟化。  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> 用于按从左到右的顺序位置定位子元素，并在到达其父容器的边缘时将内容分解到下一行。 内容可以设置为水平或垂直方向。 <xref:System.Windows.Controls.WrapPanel> 适用于简单的流动 @no__t 方案。 它还可以用来将统一大小调整应用于其所有子元素。  
  
 下面的示例演示如何创建一个 <xref:System.Windows.Controls.WrapPanel>，以显示在其到达容器边缘时换行的 @no__t 1 控件。  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型 WrapPanel 元素。](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>嵌套 Panel 元素  
 <xref:System.Windows.Controls.Panel> 元素可以相互嵌套，以便生成复杂的布局。 这在以下情况下非常有用：一个 <xref:System.Windows.Controls.Panel> 适合于 @no__t 的一部分，但可能不满足 @no__t 的其他部分的需求。  
  
 对于应用程序可以支持的嵌套数量，并没有实际限制，但通常最好限制应用程序仅使用预期布局实际所需的面板。 在许多情况下，可以使用 @no__t 0 元素，而不是嵌套面板，因为它具有作为布局容器的灵活性。 这可以通过将不必要的元素排除在树以外来提高应用程序的性能。  
  
 下面的示例演示如何创建一个 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，它利用嵌套的 @no__t 1 元素来实现特定的布局。 在这种特定情况下，<xref:System.Windows.Controls.DockPanel> 元素用于提供 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 结构和嵌套的 <xref:System.Windows.Controls.StackPanel> 元素、<xref:System.Windows.Controls.Grid>，而 @no__t 用于在父级 <xref:System.Windows.Controls.DockPanel> 中精确定位子元素。  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![充分利用嵌套面板的 UI。](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>自定义 Panel 元素  
 虽然 @no__t 提供灵活的布局控件的数组，但也可以通过重写 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 和 @no__t 2 方法来实现自定义布局行为。 可以通过在这些重写方法内定义新的位置行为来实现自定义大小调整和位置。  
  
 同样，可以通过重写其 @no__t 2 和 @no__t 3 方法来定义基于派生类（如 <xref:System.Windows.Controls.Canvas> 或 <xref:System.Windows.Controls.Grid>）的自定义布局行为。  
  
 下面的标记演示了如何创建自定义 @no__t 0 元素。 此新 <xref:System.Windows.Controls.Panel> （定义为 `PlotPanel`）支持通过使用硬编码*x*和*y*坐标来定位子元素。 在此示例中，@no__t 0 元素（未显示）放置在绘图点50（*x*）和50（*y*）的位置。  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 若要查看更复杂的自定义面板实现，请参阅[创建自定义内容换行面板示例](https://go.microsoft.com/fwlink/?LinkID=159979)。  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>本地化/全球化支持  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 支持多种有助于创建可本地化的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的功能。  
  
 所有 panel 元素都以本机方式支持 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性，该属性可用于根据用户的区域设置或语言设置动态地重新流动内容。 有关详细信息，请参阅 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 。  
  
 @No__t-0 属性提供了一种机制，使应用程序开发人员能够预测本地化 @no__t 的需求。 使用此属性的 @no__t 0 值，父级 @no__t 始终动态调整大小以适应内容，并且不受人工高度或宽度限制的限制。  
  
 <xref:System.Windows.Controls.DockPanel>、@no__t 为-1，<xref:System.Windows.Controls.StackPanel> 是可本地化 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的不错选择。 但 <xref:System.Windows.Controls.Canvas> 不是一个不错的选择，因为它以绝对方式定位内容，因此很难进行本地化。  
  
 有关使用可本地化的用户界面（Ui）创建 @no__t 0 应用程序的其他信息，请参阅[使用自动布局概述](../advanced/use-automatic-layout-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [WPF 布局库示例](https://go.microsoft.com/fwlink/?LinkID=160054)
- [布局](../advanced/layout.md)
- [WPF 控件库示例](https://go.microsoft.com/fwlink/?LinkID=160053)
- [对齐、边距和填充概述](../advanced/alignment-margins-and-padding-overview.md)
- [创建自定义内容换行面板示例](https://go.microsoft.com/fwlink/?LinkID=159979)
- [附加属性概述](../advanced/attached-properties-overview.md)
- [使用自动布局概述](../advanced/use-automatic-layout-overview.md)
- [布局和示例](../advanced/optimizing-performance-layout-and-design.md)
