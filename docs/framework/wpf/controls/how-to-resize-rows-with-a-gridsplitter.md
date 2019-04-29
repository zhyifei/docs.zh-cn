---
title: 如何：使用 GridSplitter 重设行大小
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770703"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="e68bb-102">如何：使用 GridSplitter 重设行大小</span><span class="sxs-lookup"><span data-stu-id="e68bb-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="e68bb-103">此示例演示如何使用水平<xref:System.Windows.Controls.GridSplitter>若要重新分发中的两个行之间的间距<xref:System.Windows.Controls.Grid>而无需更改的维度<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="e68bb-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e68bb-104">示例</span><span class="sxs-lookup"><span data-stu-id="e68bb-104">Example</span></span>  
 <span data-ttu-id="e68bb-105">**如何创建覆盖行边缘的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="e68bb-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="e68bb-106">若要指定<xref:System.Windows.Controls.GridSplitter>相邻行中的大小进行调整<xref:System.Windows.Controls.Grid>，将<xref:System.Windows.Controls.Grid.Row%2A>附加属性设置为要重设大小的行之一。</span><span class="sxs-lookup"><span data-stu-id="e68bb-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="e68bb-107">如果你<xref:System.Windows.Controls.Grid>具有多个列，设置<xref:System.Windows.Controls.Grid.ColumnSpan%2A>附加属性指定的列数。</span><span class="sxs-lookup"><span data-stu-id="e68bb-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="e68bb-108">然后设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>到<xref:System.Windows.VerticalAlignment.Top>或<xref:System.Windows.VerticalAlignment.Bottom>（设置的对齐方式取决于你想要调整大小的两个行）。</span><span class="sxs-lookup"><span data-stu-id="e68bb-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="e68bb-109">最后，设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性设置为<xref:System.Windows.HorizontalAlignment.Stretch>。</span><span class="sxs-lookup"><span data-stu-id="e68bb-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="e68bb-110">下面的示例演示如何定义水平<xref:System.Windows.Controls.GridSplitter>相邻的行的大小进行调整。</span><span class="sxs-lookup"><span data-stu-id="e68bb-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="e68bb-111">一个<xref:System.Windows.Controls.GridSplitter>未占据其自己的行可能会被中的其他控件遮盖<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="e68bb-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="e68bb-112">有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](how-to-make-sure-that-a-gridsplitter-is-visible.md)。</span><span class="sxs-lookup"><span data-stu-id="e68bb-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="e68bb-113">**如何创建占据一行的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="e68bb-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="e68bb-114">若要指定<xref:System.Windows.Controls.GridSplitter>占据一行<xref:System.Windows.Controls.Grid>，将<xref:System.Windows.Controls.Grid.Row%2A>附加属性设置为要重设大小的行之一。</span><span class="sxs-lookup"><span data-stu-id="e68bb-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="e68bb-115">如果你<xref:System.Windows.Controls.Grid>具有多个列，设置<xref:System.Windows.Controls.Grid.ColumnSpan%2A>附加属性设置为的列数。</span><span class="sxs-lookup"><span data-stu-id="e68bb-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="e68bb-116">然后设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>到<xref:System.Windows.VerticalAlignment.Center>，请设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性设置为<xref:System.Windows.HorizontalAlignment.Stretch>，并设置<xref:System.Windows.Controls.RowDefinition.Height%2A>包含的行的<xref:System.Windows.Controls.GridSplitter>到<xref:System.Windows.GridLength.Auto%2A>。</span><span class="sxs-lookup"><span data-stu-id="e68bb-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="e68bb-117">下面的示例演示如何定义水平<xref:System.Windows.Controls.GridSplitter>的占据一行并调整其大小的任意一侧的行。</span><span class="sxs-lookup"><span data-stu-id="e68bb-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="e68bb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e68bb-118">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="e68bb-119">帮助主题</span><span class="sxs-lookup"><span data-stu-id="e68bb-119">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
