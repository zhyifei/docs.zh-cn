---
title: "如何：使用 GridSplitter 调整行的大小"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d4cf06a86a1da7bb34074623f8f19f4bda7a724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="74313-102">如何：使用 GridSplitter 调整行的大小</span><span class="sxs-lookup"><span data-stu-id="74313-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="74313-103">此示例演示如何使用水平<xref:System.Windows.Controls.GridSplitter>重新分发中的两个行之间的空间<xref:System.Windows.Controls.Grid>而无需更改的维度<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="74313-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74313-104">示例</span><span class="sxs-lookup"><span data-stu-id="74313-104">Example</span></span>  
 <span data-ttu-id="74313-105">**如何创建覆盖行边缘的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="74313-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="74313-106">若要指定<xref:System.Windows.Controls.GridSplitter>相邻行中的大小进行调整<xref:System.Windows.Controls.Grid>，将其设置<xref:System.Windows.Controls.Grid.Row%2A>属性附加到一个要调整大小的行。</span><span class="sxs-lookup"><span data-stu-id="74313-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="74313-107">如果你<xref:System.Windows.Controls.Grid>有多个列，请设置<xref:System.Windows.Controls.Grid.ColumnSpan%2A>附加属性指定的列数。</span><span class="sxs-lookup"><span data-stu-id="74313-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="74313-108">然后设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>到<xref:System.Windows.VerticalAlignment.Top>或<xref:System.Windows.VerticalAlignment.Bottom>（你设置的对齐方式取决于你想要调整大小的两个行上）。</span><span class="sxs-lookup"><span data-stu-id="74313-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="74313-109">最后，设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性<xref:System.Windows.HorizontalAlignment.Stretch>。</span><span class="sxs-lookup"><span data-stu-id="74313-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="74313-110">下面的示例演示如何定义水平<xref:System.Windows.Controls.GridSplitter>相邻的行的大小进行调整。</span><span class="sxs-lookup"><span data-stu-id="74313-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="74313-111">A <xref:System.Windows.Controls.GridSplitter> ，不会占用自己的行中的其他控件可能被遮盖<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="74313-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="74313-112">有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md)。</span><span class="sxs-lookup"><span data-stu-id="74313-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="74313-113">**如何创建占据一行的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="74313-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="74313-114">若要指定<xref:System.Windows.Controls.GridSplitter>占用中的行<xref:System.Windows.Controls.Grid>，将其设置<xref:System.Windows.Controls.Grid.Row%2A>属性附加到一个要调整大小的行。</span><span class="sxs-lookup"><span data-stu-id="74313-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="74313-115">如果你<xref:System.Windows.Controls.Grid>有多个列，请设置<xref:System.Windows.Controls.Grid.ColumnSpan%2A>附加到的列数的属性。</span><span class="sxs-lookup"><span data-stu-id="74313-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="74313-116">然后设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>到<xref:System.Windows.VerticalAlignment.Center>，将其设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性<xref:System.Windows.HorizontalAlignment.Stretch>，并设置<xref:System.Windows.Controls.RowDefinition.Height%2A>包含的行的<xref:System.Windows.Controls.GridSplitter>到<xref:System.Windows.GridLength.Auto%2A>。</span><span class="sxs-lookup"><span data-stu-id="74313-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="74313-117">下面的示例演示如何定义水平<xref:System.Windows.Controls.GridSplitter>，占据一行并调整其大小在它的任意一侧的行。</span><span class="sxs-lookup"><span data-stu-id="74313-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="74313-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="74313-118">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="74313-119">帮助主题</span><span class="sxs-lookup"><span data-stu-id="74313-119">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
