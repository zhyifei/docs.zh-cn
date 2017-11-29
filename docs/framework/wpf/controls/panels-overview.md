---
title: "面板概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f89ea3308d0e6cffc3ed50809f0e87e7ba854ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="panels-overview"></a>面板概述
<xref:System.Windows.Controls.Panel>元素是控制元素的呈现的组件，其大小和维度、 其位置和其子内容的排列方式。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供了许多预定义<xref:System.Windows.Controls.Panel>元素，以及能够构造自定义<xref:System.Windows.Controls.Panel>元素。  
  
 本主题包含以下各节：  
  
-   [Panel 类](#Panels_view_from_10000_feet)  
  
-   [Panel 元素公共成员](#Panels_declared_members)  
  
-   [派生 Panel 元素](#Panels_derived_elements)  
  
-   [用户界面 Panel](#Panels_main_UI_elements)  
  
-   [嵌套 Panel 元素](#Panels_nested_panel_elements)  
  
-   [自定义 Panel 元素](#Panels_custom_panel_elements)  
  
-   [本地化/全球化支持](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Panel 类  
 <xref:System.Windows.Controls.Panel>是的基类，提供布局的所有元素支持在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。 派生<xref:System.Windows.Controls.Panel>元素用于放置和排列中的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]和代码。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包含一套全面的派生面板实现，可支持许多复杂的布局。 这些派生类公开可实现大部分标准 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 方案的属性和方法。 开发人员找不到满足其需求的子排列行为可以通过重写创建新的布局<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。 有关自定义布局行为的详细信息，请参阅[自定义 Panel 元素](#Panels_custom_panel_elements)。  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Panel 公共成员  
 所有<xref:System.Windows.Controls.Panel>元素支持的基大小调整和定位属性定义<xref:System.Windows.FrameworkElement>，包括<xref:System.Windows.FrameworkElement.Height%2A>， <xref:System.Windows.FrameworkElement.Width%2A>， <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>， <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>， <xref:System.Windows.FrameworkElement.Margin%2A>，和<xref:System.Windows.FrameworkElement.LayoutTransform%2A>。 有关其他信息定义的定位属性<xref:System.Windows.FrameworkElement>，请参阅[对齐、 边距和填充概述](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)。  
  
 <xref:System.Windows.Controls.Panel>公开至关重要的一点是了解和使用布局中的其他的属性。 <xref:System.Windows.Controls.Panel.Background%2A>属性用来填充的派生的面板元素的边界之间的区域<xref:System.Windows.Media.Brush>。 <xref:System.Windows.Controls.Panel.Children%2A>表示元素的子集合，<xref:System.Windows.Controls.Panel>组成。 <xref:System.Windows.Controls.Panel.InternalChildren%2A>表示的内容<xref:System.Windows.Controls.Panel.Children%2A>集合以及由数据绑定生成这些成员。 同时组成<xref:System.Windows.Controls.UIElementCollection>承载父项中的子元素<xref:System.Windows.Controls.Panel>。  
  
 Panel 也公开<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>附加属性，可以用于实现分层的顺序派生的<xref:System.Windows.Controls.Panel>。 一个面板成员<xref:System.Windows.Controls.Panel.Children%2A>较高的集合<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>值显示于较低的那些<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>值。 这是特别有用面板的如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.Grid>它们允许子元素共享相同的坐标空间。  
  
 <xref:System.Windows.Controls.Panel>此外定义<xref:System.Windows.Controls.Panel.OnRender%2A>方法，可以使用重写的默认演示文稿行为<xref:System.Windows.Controls.Panel>。  
  
#### <a name="attached-properties"></a>附加属性  
 派生面板元素广泛使用附加属性。 附加属性是没有常规 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 属性“包装器”的依赖属性的特殊化形式。 附加属性在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中具有特殊化的语法，可在后面的几个示例中看到。  
  
 附加属性的一个用途是允许子元素存储实际上由父元素定义的属性的唯一值。 此功能的一项应用是让子元素通知父级它们希望如何在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中呈现，这对应用程序布局非常有用。 有关详细信息，请参阅[附加属性概述](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)。  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>派生 Panel 元素  
 许多对象派生自<xref:System.Windows.Controls.Panel>，但不是所有作为根布局提供程序专供使用。 有六个定义的面板类 (<xref:System.Windows.Controls.Canvas>， <xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.Grid>， <xref:System.Windows.Controls.StackPanel>， <xref:System.Windows.Controls.VirtualizingStackPanel>，和<xref:System.Windows.Controls.WrapPanel>)，专为创建应用程序设计[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 每个面板元素都封装自己的特殊功能，如下表所示。  
  
|元素名称|是否为 UI 面板？|描述|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|是|定义一个区域，在其中你可以显式定位由相对于坐标的子元素<xref:System.Windows.Controls.Canvas>区域。|  
|<xref:System.Windows.Controls.DockPanel>|是|定义一个区域，可在其中使子元素相互水平或垂直排列。|  
|<xref:System.Windows.Controls.Grid>|是|定义一个由列和行组成的灵活网格区域。 子元素的<xref:System.Windows.Controls.Grid>可以精确地使用定位<xref:System.Windows.FrameworkElement.Margin%2A>属性。|  
|<xref:System.Windows.Controls.StackPanel>|是|将子元素排列成水平或垂直的一行。|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|处理选项卡中的按钮布局<xref:System.Windows.Controls.TabControl>。|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|排列中的内容<xref:System.Windows.Controls.ToolBar>控件。|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid>用于与所有相等的单元格大小排列在网格中的子级。|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|为可以“虚拟化”其子级集合的面板提供基类。|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|是|在水平或垂直方向上将内容排列为一行并使其虚拟化。|  
|<xref:System.Windows.Controls.WrapPanel>|是|<xref:System.Windows.Controls.WrapPanel>在从左到右，换行到下一行包含框的边缘上的内容的顺序位置定位子元素。 后续排序按照按顺序从顶部到底部或从右到左，具体取决于值<xref:System.Windows.Controls.WrapPanel.Orientation%2A>属性。|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>用户界面 Panel  
 有六个面板类中可用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]进行优化的以支持[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]方案： <xref:System.Windows.Controls.Canvas>， <xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.Grid>， <xref:System.Windows.Controls.StackPanel>， <xref:System.Windows.Controls.VirtualizingStackPanel>，和<xref:System.Windows.Controls.WrapPanel>。 这些面板元素易于使用、功能齐全并且可扩展，足以适用于大多数应用程序。  
  
 每个派生<xref:System.Windows.Controls.Panel>元素对待大小调整约束的方式不同。 了解如何<xref:System.Windows.Controls.Panel>中水平或垂直方向的句柄约束可以使更可预测的布局。  
  
|**Panel 名称**|**x 维度**|**y 维度**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|按内容约束|按内容约束|  
|<xref:System.Windows.Controls.DockPanel>|约束|约束|  
|<xref:System.Windows.Controls.StackPanel>（垂直方向）|约束|按内容约束|  
|<xref:System.Windows.Controls.StackPanel>（水平方向）|按内容约束|约束|  
|<xref:System.Windows.Controls.Grid>|约束|约束，除非情况下在其中<xref:System.Windows.GridUnitType.Auto>将应用于行和列|  
|<xref:System.Windows.Controls.WrapPanel>|按内容约束|按内容约束|  
  
 可在下方找到其中每种元素的更多详细说明和使用示例。  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 <xref:System.Windows.Controls.Canvas>元素启用的内容根据绝对定位*x-*和*y-*坐标。 元素可以在唯一位置绘制；或者，如果元素占用了相同坐标，则这些元素在标记中显示的顺序决定它们的绘制顺序。  
  
 <xref:System.Windows.Controls.Canvas>提供的任何最灵活的布局支持<xref:System.Windows.Controls.Panel>。 高度和宽度属性用于定义的区域的画布上，以及内的元素分配相对于父区域的绝对坐标<xref:System.Windows.Controls.Canvas>。 四个附加的属性， <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType>和<xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>，允许对中的对象放置进行精细控制<xref:System.Windows.Controls.Canvas>，开发人员可以放置和排列在屏幕上精确的元素。  
  
#### <a name="cliptobounds-within-a-canvas"></a>Canvas 内 ClipToBounds  
 <xref:System.Windows.Controls.Canvas>可以在屏幕上，甚至在坐标之外自己定义的任何位置定位子元素<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>。 此外，<xref:System.Windows.Controls.Canvas>不受及其所有子级的大小。 因此，很可能要过度绘制外的父级的绑定矩形其他元素的子元素<xref:System.Windows.Controls.Canvas>。 默认行为<xref:System.Windows.Controls.Canvas>是允许子级的父级边界之外绘制<xref:System.Windows.Controls.Canvas>。 如果不需要，此行为<xref:System.Windows.UIElement.ClipToBounds%2A>属性可以设置为`true`。 这将导致<xref:System.Windows.Controls.Canvas>裁剪到其自身的大小。 <xref:System.Windows.Controls.Canvas>是允许要绘制超出界限的子级的唯一布局元素。  
  
 [宽度属性比较示例](http://go.microsoft.com/fwlink/?LinkID=160050)中以图形方式展示了此行为。  
  
#### <a name="defining-and-using-a-canvas"></a>定义和使用 Canvas  
 A<xref:System.Windows.Controls.Canvas>可以实例化只需通过使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]或代码。 下面的示例演示如何使用<xref:System.Windows.Controls.Canvas>以绝对方式定位内容。 此代码生成三个 100 像素正方形。 第一个正方形为红色，其左上角的 (*x, y*) 位置指定为 (0, 0)。 第二个正方形为绿色，其左上角位置为 (100, 100)，在第一个正方形的右下方。 第三个正方形为蓝色，其左上角为 (50, 50)，因此包含了第一个正方形的右下四分之一部分和第二个正方形的左上四分之一部分。 由于第三个正方形最后布置，因此它看起来在另外两个正方形上方，即，重叠部分采用第三个正方形的颜色。  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 Canvas 元素。](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 <xref:System.Windows.Controls.DockPanel>元素使用<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>中子内容元素，以将沿容器的边缘的内容设置附加属性。 当<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>设置为<xref:System.Windows.Controls.Dock.Top>或<xref:System.Windows.Controls.Dock.Bottom>，它定位子元素的上方或下方彼此。 当<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>设置为<xref:System.Windows.Controls.Dock.Left>或<xref:System.Windows.Controls.Dock.Right>，它定位到左侧或右侧的每个其他子元素。 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A>属性确定添加作为子项的最后一个元素的位置<xref:System.Windows.Controls.DockPanel>。  
  
 你可以使用<xref:System.Windows.Controls.DockPanel>定位一组相关控件，如一组按钮。 或者，可以使用它创建“平移”的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，类似于 [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)] 中的 UI。  
  
#### <a name="sizing-to-content"></a>按内容调整大小  
 如果其<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>未指定属性，<xref:System.Windows.Controls.DockPanel>对其内容的大小。 大小可以增大或减小以容纳其子元素的大小。 但是，当指定了这些属性，并且不再为下一步指定的子元素，留出空间<xref:System.Windows.Controls.DockPanel>不显示该子元素或其后的子元素和不衡量后续的子元素。  
  
#### <a name="lastchildfill"></a>LastChildFill  
 默认情况下的最后一个子级<xref:System.Windows.Controls.DockPanel>元素将"填充"剩余未分配的空间。 如果不需要此行为，设置<xref:System.Windows.Controls.DockPanel.LastChildFill%2A>属性`false`。  
  
#### <a name="defining-and-using-a-dockpanel"></a>定义和使用 DockPanel  
 下面的示例演示如何进行分区空间使用<xref:System.Windows.Controls.DockPanel>。 五个<xref:System.Windows.Controls.Border>元素添加为父级的子级<xref:System.Windows.Controls.DockPanel>。 每个使用不同的定位属性<xref:System.Windows.Controls.DockPanel>到分区空间。 最后一个元素"填充"剩余的未分配空间。  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 DockPanel 方案。](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Grid  
 <xref:System.Windows.Controls.Grid>元素合并绝对定位和表格数据控件的功能。 A<xref:System.Windows.Controls.Grid>使您能够轻松地位置和样式的元素。 <xref:System.Windows.Controls.Grid>允许你定义灵活的行和列分组，并甚至还提供了一种机制来共享之间多个大小调整信息<xref:System.Windows.Controls.Grid>元素。  
  
#### <a name="how-is-grid-different-from-table"></a>网格与表格有何不同？  
 <xref:System.Windows.Documents.Table>和<xref:System.Windows.Controls.Grid>共享一些常见的功能，但每个最适合于不同的方案。 A<xref:System.Windows.Documents.Table>旨在用于在流内容中 (请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)有关流内容的详细信息)。 网格最适合在表单内（主要在流内容以外的任意位置）使用。 在<xref:System.Windows.Documents.FlowDocument>，<xref:System.Windows.Documents.Table>支持流分页、 列回流等内容时选择的内容行为<xref:System.Windows.Controls.Grid>却没有。 A<xref:System.Windows.Controls.Grid>另一方面最佳使用外部<xref:System.Windows.Documents.FlowDocument>包括的原因有很多<xref:System.Windows.Controls.Grid>添加基于一个行和列的索引，元素<xref:System.Windows.Documents.Table>却没有。 <xref:System.Windows.Controls.Grid>元素允许的子内容，允许多个元素中的单个"单元格。"存在分层 <xref:System.Windows.Documents.Table>不支持分层。 子元素的<xref:System.Windows.Controls.Grid>进行绝对定位相对于其"单元格"边界的区域。 <xref:System.Windows.Documents.Table>不支持此功能。 最后，<xref:System.Windows.Controls.Grid>是比种更轻量<xref:System.Windows.Documents.Table>。  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>列和行的大小调整行为  
 在中定义的行和列<xref:System.Windows.Controls.Grid>可以充分利用<xref:System.Windows.GridUnitType.Star>以便分发剩余的空间按比例调整大小。 当<xref:System.Windows.GridUnitType.Star>被选为的高度或宽度的行或列，列或行接收剩余的可用空间的加权的比例。 这是与此相反<xref:System.Windows.GridUnitType.Auto>，这会将分发均匀地根据中的列或行的内容的大小的空间。 在使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 时，此值以 `*` 或 `2*` 的形式表示。 在第一种情况下，行或列将得到一倍的可用空间，在第二种情况下，将得到两倍的可用空间，依此类推。 通过将此项可按比例分配空间的技术结合起来<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>值`Stretch`可以按百分比的屏幕空间的分区布局空间。 <xref:System.Windows.Controls.Grid>是唯一的布局面板可以分发以这种方式的空间。  
  
#### <a name="defining-and-using-a-grid"></a>定义和使用 Grid  
 以下示例演示如何生成 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，该 UI 类似于 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]“开始”菜单上提供的“运行”对话框上的 UI。  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 Grid 元素。] (../../../../docs/framework/wpf/controls/media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 A<xref:System.Windows.Controls.StackPanel>使您能够"堆叠"在不分配的方向的元素。 默认堆叠方向为垂直方向。 <xref:System.Windows.Controls.StackPanel.Orientation%2A>属性可以用于控制内容的流。  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel 与 DockPanel  
 尽管<xref:System.Windows.Controls.DockPanel>可以还"堆叠"在子元素<xref:System.Windows.Controls.DockPanel>和<xref:System.Windows.Controls.StackPanel>不会产生一些使用方案中的类似结果。 例如，子元素的顺序可能会影响其大小以<xref:System.Windows.Controls.DockPanel>但未显示在<xref:System.Windows.Controls.StackPanel>。 这是因为<xref:System.Windows.Controls.StackPanel>度量值的方向堆叠在<xref:System.Double.PositiveInfinity>，而<xref:System.Windows.Controls.DockPanel>测量仅的可用大小。  
  
 以下示例演示此主要区别。  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 通过此图像可以看到呈现行为的区别。  
  
 ![屏幕截图：StackPanel 与 DockPanel 屏幕截图](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>定义和使用 StackPanel  
 下面的示例演示如何使用<xref:System.Windows.Controls.StackPanel>创建一组垂直定位按钮。 对于水平定位设置<xref:System.Windows.Controls.StackPanel.Orientation%2A>属性<xref:System.Windows.Controls.Orientation.Horizontal>。  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型的 StackPanel 元素。](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]此外提供了一种变体<xref:System.Windows.Controls.StackPanel>自动"显示"数据绑定子内容的元素。 在此上下文中，“虚拟化”一词指的是一种技术：通过此技术根据屏幕上哪些项可见，从较多的数据项中生成一个元素子集。 如果在指定时刻只有少量 UI 元素位于屏幕上，则此时生成大量 UI 元素需要占用大量内存和处理器。 <xref:System.Windows.Controls.VirtualizingStackPanel>(由提供的功能通过<xref:System.Windows.Controls.VirtualizingPanel>) 计算可见的项，并处理<xref:System.Windows.Controls.ItemContainerGenerator>从<xref:System.Windows.Controls.ItemsControl>(如<xref:System.Windows.Controls.ListBox>或<xref:System.Windows.Controls.ListView>) 仅创建为可见项的元素。  
  
 <xref:System.Windows.Controls.VirtualizingStackPanel>元素会自动设置为项主机控件的如<xref:System.Windows.Controls.ListBox>。 当承载数据绑定集合时，内容被自动虚拟化，只要内容的边界内<xref:System.Windows.Controls.ScrollViewer>。 在承载许多子项时，这将大幅提高性能。  
  
 以下代码演示如何使用<xref:System.Windows.Controls.VirtualizingStackPanel>作为项主机。 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty%2A?displayProperty=nameWithType>附加的属性必须设置为`true`（默认） 才能进行虚拟化。  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>用于按顺序从左到右，换行到下一步的行在到达其父容器的边缘时的内容的位置来定位子元素。 内容可以设置为水平或垂直方向。 <xref:System.Windows.Controls.WrapPanel>可用于简单流动[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]方案。 它还可以用来将统一大小调整应用于其所有子元素。  
  
 下面的示例演示如何创建<xref:System.Windows.Controls.WrapPanel>以显示<xref:System.Windows.Controls.Button>换行时到达其容器的边缘的控件。  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![典型 WrapPanel 元素。](../../../../docs/framework/wpf/controls/media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>嵌套 Panel 元素  
 <xref:System.Windows.Controls.Panel>可以相互嵌套元素，以便生成复杂布局。 这可以证明非常有用的其中一个<xref:System.Windows.Controls.Panel>非常适合的一部分[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，但可能会不符合的不同部分的需求[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 对于应用程序可以支持的嵌套数量，并没有实际限制，但通常最好限制应用程序仅使用预期布局实际所需的面板。 在许多情况下，<xref:System.Windows.Controls.Grid>元素可而不是嵌套面板，因为它作为一个布局容器的灵活性。 这可以通过将不必要的元素排除在树以外来提高应用程序的性能。  
  
 下面的示例演示如何创建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]利用嵌套<xref:System.Windows.Controls.Panel>以便实现特定布局的元素。 在此特定情况下，<xref:System.Windows.Controls.DockPanel>元素用于提供[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]结构，而嵌套<xref:System.Windows.Controls.StackPanel>元素， <xref:System.Windows.Controls.Grid>，和一个<xref:System.Windows.Controls.Canvas>用于定位精确父项中的子元素<xref:System.Windows.Controls.DockPanel>。  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 经编译的应用程序产生新的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，外观如下。  
  
 ![充分利用嵌套面板的 UI。](../../../../docs/framework/wpf/controls/media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>自定义 Panel 元素  
 虽然[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供灵活的布局控件，也可以通过重写实现行为的自定义布局的一系列<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。 可以通过在这些重写方法内定义新的位置行为来实现自定义大小调整和位置。  
  
 同样，自定义布局行为基于派生类 (如<xref:System.Windows.Controls.Canvas>或<xref:System.Windows.Controls.Grid>) 可以通过重写定义其<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。  
  
 以下代码演示如何创建自定义<xref:System.Windows.Controls.Panel>元素。 此新<xref:System.Windows.Controls.Panel>，定义如下`PlotPanel`，支持通过使用硬编码的子元素的位置*x-*和*y-*坐标。 在此示例中， <xref:System.Windows.Shapes.Rectangle> （未显示） 的元素都位于绘图点 50 (*x*)，到 50 (*y*)。  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 若要查看更复杂的自定义面板实现，请参阅[创建自定义内容换行面板示例](http://go.microsoft.com/fwlink/?LinkID=159979)。  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>本地化/全球化支持  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 支持多种有助于创建可本地化的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的功能。  
  
 面板的所有元素以本机方式都支持<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性，可用于动态重新流动基于用户的区域设置或语言设置的内容。 有关更多信息，请参见<xref:System.Windows.FrameworkElement.FlowDirection%2A>。  
  
 <xref:System.Windows.Window.SizeToContent%2A>属性提供一种机制，使应用程序开发人员可以预计的需要本地化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 使用<xref:System.Windows.SizeToContent.WidthAndHeight>此属性值，该值父<xref:System.Windows.Window>始终动态调整大小以适应内容并不受人工高度或宽度的限制。  
  
 <xref:System.Windows.Controls.DockPanel><xref:System.Windows.Controls.Grid>，和<xref:System.Windows.Controls.StackPanel>是为所有不错的选择可本地化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 <xref:System.Windows.Controls.Canvas>但是，是不错的选择，因为它将定位内容绝对支持，从而使得难以本地化。  
  
 有关创建带有可本地化 [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] 的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序的其他信息，请参阅[使用自动布局概述](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)。  
  
## <a name="see-also"></a>另请参阅  
 [演练：我的第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [WPF 布局库示例](http://go.microsoft.com/fwlink/?LinkID=160054)  
 [布局](../../../../docs/framework/wpf/advanced/layout.md)  
 [WPF 控件库示例](http://go.microsoft.com/fwlink/?LinkID=160053)  
 [对齐、边距和填充概述](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [创建自定义的内容换行面板示例](http://go.microsoft.com/fwlink/?LinkID=159979)  
 [附加属性概述](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [使用自动布局概述](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [布局和示例](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
