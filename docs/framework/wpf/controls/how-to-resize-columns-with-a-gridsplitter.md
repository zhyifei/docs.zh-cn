---
title: 如何：使用 GridSplitter 调整列的大小
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: 6bf09c41145aca8690fe3e80fd76a7a859713ad6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562136"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="dfcfb-102">如何：使用 GridSplitter 调整列的大小</span><span class="sxs-lookup"><span data-stu-id="dfcfb-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="dfcfb-103">此示例演示如何创建垂直<xref:System.Windows.Controls.GridSplitter>若要重新分发中的两个列之间的间距<xref:System.Windows.Controls.Grid>而无需更改的维度<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfcfb-104">示例</span><span class="sxs-lookup"><span data-stu-id="dfcfb-104">Example</span></span>  
 <span data-ttu-id="dfcfb-105">**如何创建覆盖列边缘的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="dfcfb-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="dfcfb-106">若要指定<xref:System.Windows.Controls.GridSplitter>中的相邻列的大小进行调整<xref:System.Windows.Controls.Grid>，将<xref:System.Windows.Controls.Grid.Column%2A>附加属性设置为要重设大小的列之一。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="dfcfb-107">如果你<xref:System.Windows.Controls.Grid>具有多个行，设置<xref:System.Windows.Controls.Grid.RowSpan%2A>附加属性设置为行数。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="dfcfb-108">然后设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性设置为<xref:System.Windows.HorizontalAlignment.Left>或<xref:System.Windows.HorizontalAlignment.Right>（设置的对齐方式取决于你想要调整大小的两个列）。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="dfcfb-109">最后，设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性设置为<xref:System.Windows.VerticalAlignment.Stretch>。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="dfcfb-110">一个<xref:System.Windows.Controls.GridSplitter>不具有其各自的列中的其他控件可能会被遮盖<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="dfcfb-111">有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md)。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="dfcfb-112">**如何创建占据一列的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="dfcfb-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="dfcfb-113">若要指定<xref:System.Windows.Controls.GridSplitter>占据一列中的<xref:System.Windows.Controls.Grid>，将<xref:System.Windows.Controls.Grid.Column%2A>附加属性设置为要重设大小的列之一。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="dfcfb-114">如果您的网格包含多个行，请设置<xref:System.Windows.Controls.Grid.RowSpan%2A>附加属性设置为行数。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="dfcfb-115">然后设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>到<xref:System.Windows.HorizontalAlignment.Center>，请设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性设置为<xref:System.Windows.VerticalAlignment.Stretch>，并设置<xref:System.Windows.Controls.ColumnDefinition.Width%2A>包含的列的<xref:System.Windows.Controls.GridSplitter>到<xref:System.Windows.GridLength.Auto%2A>。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="dfcfb-116">下面的示例演示如何定义垂直<xref:System.Windows.Controls.GridSplitter>的占据一列和调整任意一侧列的大小。</span><span class="sxs-lookup"><span data-stu-id="dfcfb-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="dfcfb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfcfb-117">See also</span></span>
- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="dfcfb-118">帮助主题</span><span class="sxs-lookup"><span data-stu-id="dfcfb-118">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
