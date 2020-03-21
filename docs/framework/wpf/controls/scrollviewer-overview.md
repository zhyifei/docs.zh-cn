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
ms.openlocfilehash: 2ff0f134ea3174f7f034d47446aab782e2141916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186987"
---
# <a name="scrollviewer-overview"></a>ScrollViewer 概述
用户界面中的内容通常比计算机屏幕的显示区域大。 该<xref:System.Windows.Controls.ScrollViewer>控件提供了一种在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中启用内容滚动的便捷方法。 本主题介绍该<xref:System.Windows.Controls.ScrollViewer>元素，并提供几个使用示例。  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>ScrollViewer 控件  
 有两个预定义元素在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中启用滚动：<xref:System.Windows.Controls.Primitives.ScrollBar>和<xref:System.Windows.Controls.ScrollViewer>。 控件<xref:System.Windows.Controls.ScrollViewer>封装水平和垂直<xref:System.Windows.Controls.Primitives.ScrollBar>元素以及内容容器（如<xref:System.Windows.Controls.Panel>元素），以便在可滚动区域中显示其他可见元素。 您必须生成自定义对象才能将<xref:System.Windows.Controls.Primitives.ScrollBar>元素用于内容滚动。 但是，您可以自行使用该<xref:System.Windows.Controls.ScrollViewer>元素，因为它是封装<xref:System.Windows.Controls.Primitives.ScrollBar>功能的复合控件。  
  
 该<xref:System.Windows.Controls.ScrollViewer>控件同时响应鼠标和键盘命令，并定义许多以预定增量滚动内容的方法。 可以使用 事件<xref:System.Windows.Controls.ScrollViewer.ScrollChanged>检测<xref:System.Windows.Controls.ScrollViewer>状态中的更改。  
  
 只能<xref:System.Windows.Controls.ScrollViewer>有一个子级，通常是可以<xref:System.Windows.Controls.Panel>承载元素<xref:System.Windows.Controls.Panel.Children%2A>集合的元素。 属性<xref:System.Windows.Controls.ContentPresenter.Content%2A>定义 的唯<xref:System.Windows.Controls.ScrollViewer>一子项。  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>物理与逻辑滚动  
 物理滚动用于按预设的物理增量（通常按以像素为单位声明的值）滚动内容。 逻辑滚动用于滚动到逻辑树中的下一项。 物理滚动是大多数<xref:System.Windows.Controls.Panel>元素的默认滚动行为。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 同时支持这两种类型的滚动。  
  
#### <a name="the-iscrollinfo-interface"></a>IScrollInfo 接口  
 接口<xref:System.Windows.Controls.Primitives.IScrollInfo>表示<xref:System.Windows.Controls.ScrollViewer>或 派生控件中的主滚动区域。 该接口定义滚动属性和方法，这些属性和方法可以由<xref:System.Windows.Controls.Panel>需要按逻辑单元滚动的元素实现，而不是物理增量。 将 的<xref:System.Windows.Controls.Primitives.IScrollInfo>实例强制转换到<xref:System.Windows.Controls.Panel>派生的实例，然后使用其滚动方法提供了一种将滚动到子集合中的下一个逻辑单元的有用方法，而不是按像素增量滚动。 默认情况下，<xref:System.Windows.Controls.ScrollViewer>控件支持按物理单位滚动。  
  
 <xref:System.Windows.Controls.StackPanel>和<xref:System.Windows.Controls.VirtualizingStackPanel>实现<xref:System.Windows.Controls.Primitives.IScrollInfo>和本机支持逻辑滚动。 对于本机支持逻辑滚动的布局控件，您仍可以通过在 中包装<xref:System.Windows.Controls.Panel>宿主元素<xref:System.Windows.Controls.ScrollViewer>并将<xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A>属性设置为`false`来实现物理滚动。  
  
 以下代码示例演示如何<xref:System.Windows.Controls.Primitives.IScrollInfo>将 实例转换为 ，<xref:System.Windows.Controls.StackPanel>并使用由接口定义的内容滚动方法 （<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A>和<xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>） 。  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>定义和使用 ScrollViewer 元素  
 下面的示例在包含某些<xref:System.Windows.Controls.ScrollViewer>文本和矩形的窗口中创建 。 <xref:System.Windows.Controls.Primitives.ScrollBar>元素仅在必要时才出现。 调整窗口大小时，由于 和<xref:System.Windows.Controls.Primitives.ScrollBar><xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A><xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>属性的更新值，元素将显示并消失。  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>设置 ScrollViewer 的样式  
 与 Windows 演示文稿基础中的所有控件一<xref:System.Windows.Controls.ScrollViewer>样，可以设置 样式，以便更改控件的默认呈现行为。 有关控件样式设置的其他信息，请参阅[样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)。  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>对文档进行分页  
 对于文档内容，一种替代滚动的方法是选择支持分页的文档容器。 <xref:System.Windows.Documents.FlowDocument>用于设计为托管在查看控件中的文档，例如<xref:System.Windows.Controls.FlowDocumentPageViewer>，支持跨多个页面对内容进行分页，从而防止需要滚动。 <xref:System.Windows.Controls.DocumentViewer>提供了用于查看<xref:System.Windows.Documents.FixedDocument>内容的解决方案，该解决方案使用传统滚动在显示区域之外显示内容。  
  
 有关文档格式和演示选项的其他信息，请参阅 [WPF 中的文档](../advanced/documents-in-wpf.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [如何：创建滚动查看器](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [WPF 中的文档](../advanced/documents-in-wpf.md)
- [ScrollBar 样式和模板](scrollbar-styles-and-templates.md)
- [控制](../advanced/optimizing-performance-controls.md)
