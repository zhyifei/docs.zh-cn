---
title: 如何：使用 ScrollViewer 的内容滚动方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: b4da666934be7dd182838d870e54e496b2646901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="45d82-102">如何：使用 ScrollViewer 的内容滚动方法</span><span class="sxs-lookup"><span data-stu-id="45d82-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="45d82-103">此示例演示如何使用的滚动方法<xref:System.Windows.Controls.ScrollViewer>元素。</span><span class="sxs-lookup"><span data-stu-id="45d82-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="45d82-104">这些方法提供了增量滚动的内容，行或页上，在<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="45d82-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45d82-105">示例</span><span class="sxs-lookup"><span data-stu-id="45d82-105">Example</span></span>  
 <span data-ttu-id="45d82-106">下面的示例创建<xref:System.Windows.Controls.ScrollViewer>名为`sv1`，它承载子<xref:System.Windows.Controls.TextBlock>元素。</span><span class="sxs-lookup"><span data-stu-id="45d82-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="45d82-107">因为<xref:System.Windows.Controls.TextBlock>大于父级<xref:System.Windows.Controls.ScrollViewer>，为了能够滚动显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="45d82-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="45d82-108"><xref:System.Windows.Controls.Button> 其元素表示各种滚动方法停靠在单独的左侧<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="45d82-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="45d82-109">每个<xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件调用控制滚动行为中的相关自定义方法<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="45d82-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="45d82-110">下面的示例使用<xref:System.Windows.Controls.ScrollViewer.LineUp%2A>和<xref:System.Windows.Controls.ScrollViewer.LineDown%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="45d82-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="45d82-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="45d82-111">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
