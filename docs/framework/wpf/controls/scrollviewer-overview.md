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
ms.openlocfilehash: 993f3c861cbead88df3503eb01f18e5d1f69e2d8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458433"
---
# <a name="scrollviewer-overview"></a>ScrollViewer 概述
用户界面中的内容通常比计算机屏幕的显示区域大。 <xref:System.Windows.Controls.ScrollViewer> 控件提供了一种方便的方法，可用于在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中滚动内容。 本主题介绍 <xref:System.Windows.Controls.ScrollViewer> 元素并提供多个用法示例。  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>ScrollViewer 控件  
 有两个预定义元素可用于在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中进行滚动： <xref:System.Windows.Controls.Primitives.ScrollBar> 和 <xref:System.Windows.Controls.ScrollViewer>。 <xref:System.Windows.Controls.ScrollViewer> 控件封装水平和垂直 <xref:System.Windows.Controls.Primitives.ScrollBar> 元素和内容容器（如 <xref:System.Windows.Controls.Panel> 元素），以便在可滚动区域中显示其他可见元素。 必须生成自定义对象，才能使用 <xref:System.Windows.Controls.Primitives.ScrollBar> 元素进行内容滚动。 但是，您可以单独使用 <xref:System.Windows.Controls.ScrollViewer> 元素，因为它是封装 <xref:System.Windows.Controls.Primitives.ScrollBar> 功能的复合控件。  
  
 <xref:System.Windows.Controls.ScrollViewer> 控件对鼠标和键盘命令做出响应，并定义了许多方法，通过预先确定的增量来滚动内容。 您可以使用 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 事件来检测 <xref:System.Windows.Controls.ScrollViewer> 状态的更改。  
  
 一个 <xref:System.Windows.Controls.ScrollViewer> 只能有一个子元素，通常是一个可承载 <xref:System.Windows.Controls.Panel.Children%2A> 元素集合的 <xref:System.Windows.Controls.Panel> 元素。 <xref:System.Windows.Controls.ContentPresenter.Content%2A> 属性定义 <xref:System.Windows.Controls.ScrollViewer>的唯一子级。  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>物理滚动与逻辑滚动  
 物理滚动用于按预设的物理增量（通常按以像素为单位声明的值）滚动内容。 逻辑滚动用于滚动到逻辑树中的下一项。 物理滚动是大多数 <xref:System.Windows.Controls.Panel> 元素的默认滚动行为。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 同时支持这两种类型的滚动。  
  
#### <a name="the-iscrollinfo-interface"></a>IScrollInfo 接口  
 <xref:System.Windows.Controls.Primitives.IScrollInfo> 接口表示 <xref:System.Windows.Controls.ScrollViewer> 或派生控件内的主滚动区域。 接口定义滚动属性和方法，这些属性和方法可由需要按逻辑单元（而不是物理增量）滚动的 <xref:System.Windows.Controls.Panel> 元素实现。 将 <xref:System.Windows.Controls.Primitives.IScrollInfo> 的实例强制转换为派生 <xref:System.Windows.Controls.Panel>，然后使用其滚动方法，可提供一种向子集合中的下一个逻辑单元（而不是像素增量）滚动的有用方法。 默认情况下，<xref:System.Windows.Controls.ScrollViewer> 控件支持按物理单位滚动。  
  
 <xref:System.Windows.Controls.StackPanel> 和 <xref:System.Windows.Controls.VirtualizingStackPanel> 实现 <xref:System.Windows.Controls.Primitives.IScrollInfo>，并且本机支持逻辑滚动。 对于本机支持逻辑滚动的布局控件，你仍可以通过将宿主 <xref:System.Windows.Controls.Panel> 元素包装在 <xref:System.Windows.Controls.ScrollViewer> 中，并将 <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> 属性设置为 `false`来实现物理滚动。  
  
 下面的代码示例演示如何将 <xref:System.Windows.Controls.Primitives.IScrollInfo> 的实例强制转换为 <xref:System.Windows.Controls.StackPanel> 并使用由接口定义的内容滚动方法（<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 和 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>）。  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>定义和使用 ScrollViewer 元素  
 下面的示例在包含一些文本和一个矩形的窗口中创建 <xref:System.Windows.Controls.ScrollViewer>。 <xref:System.Windows.Controls.Primitives.ScrollBar> 元素仅在必要时才会出现。 当调整窗口大小时，由于 <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> 和 <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> 属性的更新的值，<xref:System.Windows.Controls.Primitives.ScrollBar> 元素会出现并消失。  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>设置 ScrollViewer 的样式  
 与 Windows Presentation Foundation 中的所有控件一样，<xref:System.Windows.Controls.ScrollViewer> 可以设置样式以便更改控件的默认呈现行为。 有关控件样式设置的其他信息，请参阅[样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)。  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>对文档进行分页  
 对于文档内容，一种替代滚动的方法是选择支持分页的文档容器。 <xref:System.Windows.Documents.FlowDocument> 用于在查看控件（如 <xref:System.Windows.Controls.FlowDocumentPageViewer>）中承载的文档，该文档支持跨多个页面对内容进行分页，从而不需要进行滚动。 <xref:System.Windows.Controls.DocumentViewer> 提供了一种用于查看 <xref:System.Windows.Documents.FixedDocument> 内容的解决方案，该解决方案使用传统滚动来显示显示区域外的内容。  
  
 有关文档格式和演示选项的其他信息，请参阅 [WPF 中的文档](../advanced/documents-in-wpf.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [如何：创建滚动查看器](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [WPF 中的文档](../advanced/documents-in-wpf.md)
- [ScrollBar 样式和模板](scrollbar-styles-and-templates.md)
- [控件](../advanced/optimizing-performance-controls.md)
