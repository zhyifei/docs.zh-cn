---
title: ScrollViewer 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1797f956ec41ba085dee7e1cb11a3129004552b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="scrollviewer-overview"></a>ScrollViewer 概述
用户界面中的内容通常比计算机屏幕的显示区域大。 <xref:System.Windows.Controls.ScrollViewer>控件提供能够滚动内容的一种简便方式[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序。 本主题介绍<xref:System.Windows.Controls.ScrollViewer>元素，并提供了几个用法示例。  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>ScrollViewer 控件  
 启用滚动中的两个预定义元素[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序：<xref:System.Windows.Controls.Primitives.ScrollBar>和<xref:System.Windows.Controls.ScrollViewer>。 <xref:System.Windows.Controls.ScrollViewer>控件封装水平和垂直<xref:System.Windows.Controls.Primitives.ScrollBar>元素和内容的容器 (如<xref:System.Windows.Controls.Panel>元素) 以便在可滚动区域中显示其他可视元素。 你必须生成自定义对象才能使用<xref:System.Windows.Controls.Primitives.ScrollBar>元素内容滚动。 但是，你可以使用<xref:System.Windows.Controls.ScrollViewer>本身的元素，因为它是复合控制封装<xref:System.Windows.Controls.Primitives.ScrollBar>功能。  
  
 <xref:System.Windows.Controls.ScrollViewer>控件响应鼠标和键盘命令，并定义用以按预先确定的增量滚动内容的很多方法。 你可以使用<xref:System.Windows.Controls.ScrollViewer.ScrollChanged>事件来检测在更改<xref:System.Windows.Controls.ScrollViewer>状态。  
  
 A<xref:System.Windows.Controls.ScrollViewer>通常只能有一个子级，<xref:System.Windows.Controls.Panel>元素可以承载<xref:System.Windows.Controls.Panel.Children%2A>元素的集合。 <xref:System.Windows.Controls.ContentPresenter.Content%2A>属性定义的唯一子级<xref:System.Windows.Controls.ScrollViewer>。  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>物理滚动与逻辑滚动  
 物理滚动用于按预设的物理增量（通常按以像素为单位声明的值）滚动内容。 逻辑滚动用于滚动到逻辑树中的下一项。 物理滚动，则大多数默认滚动行为<xref:System.Windows.Controls.Panel>元素。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 同时支持这两种类型的滚动。  
  
#### <a name="the-iscrollinfo-interface"></a>IScrollInfo 接口  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>接口表示内的主滚动区域<xref:System.Windows.Controls.ScrollViewer>或派生的控件。 滚动属性和方法可以实现该接口所定义<xref:System.Windows.Controls.Panel>需要滚动按逻辑单元，而不一个物理增量的元素。 实例强制转换为<xref:System.Windows.Controls.Primitives.IScrollInfo>到派生<xref:System.Windows.Controls.Panel>，然后使用其滚动方法提供了一种有用的方法，以滚动到下一步的逻辑单元在子集合，而不是像素的增量。 默认情况下，<xref:System.Windows.Controls.ScrollViewer>控件支持按物理单位滚动。  
  
 <xref:System.Windows.Controls.StackPanel> 和<xref:System.Windows.Controls.VirtualizingStackPanel>两者都实现<xref:System.Windows.Controls.Primitives.IScrollInfo>和以本机方式支持逻辑滚动。 对于布局控件该本机支持逻辑滚动，你仍可以实现通过包装主机的物理滚动<xref:System.Windows.Controls.Panel>中的元素<xref:System.Windows.Controls.ScrollViewer>和设置<xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A>属性`false`。  
  
 下面的代码示例演示如何强制转换的实例<xref:System.Windows.Controls.Primitives.IScrollInfo>到<xref:System.Windows.Controls.StackPanel>和使用内容滚动方法 (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A>和<xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) 由接口定义。  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>定义和使用 ScrollViewer 元素  
 下面的示例创建<xref:System.Windows.Controls.ScrollViewer>包含一些文本和一个矩形的窗口中。 <xref:System.Windows.Controls.Primitives.ScrollBar> 元素出现仅何时需要它们。 当您调整窗口中，<xref:System.Windows.Controls.Primitives.ScrollBar>元素将出现然后消失，由于更新后的值的<xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A>和<xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>属性。  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>设置 ScrollViewer 的样式  
 Windows Presentation Foundation 中的所有控件都一样<xref:System.Windows.Controls.ScrollViewer>可以样式以更改控件的默认呈现行为。 有关控件样式设置的其他信息，请参阅[样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>对文档进行分页  
 对于文档内容，一种替代滚动的方法是选择支持分页的文档容器。 <xref:System.Windows.Documents.FlowDocument> 是的旨在在查看控件中，如托管的文档<xref:System.Windows.Controls.FlowDocumentPageViewer>，跨多个页，从而无需进行滚动支持分页的内容。 <xref:System.Windows.Controls.DocumentViewer> 提供了一个解决方案，以便于查看<xref:System.Windows.Documents.FixedDocument>的内容，它使用传统滚动显示之外的显示区域的领域的内容。  
  
 有关文档格式和演示选项的其他信息，请参阅 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.ScrollBar>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 [创建滚动查看器](http://msdn.microsoft.com/library/c8e46af7-b417-441b-aa30-791cbdbd43ef)  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [ScrollBar 样式和模板](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)  
 [控件](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
