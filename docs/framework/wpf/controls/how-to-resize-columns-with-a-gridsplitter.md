---
title: 如何：使用 GridSplitter 调整列的大小
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: b4652c06cfe6f048f6c75a11b9447d70d6820e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556145"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="4cefb-102">如何：使用 GridSplitter 调整列的大小</span><span class="sxs-lookup"><span data-stu-id="4cefb-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="4cefb-103">此示例演示如何创建垂直<xref:System.Windows.Controls.GridSplitter>以便重新分发中的两列之间的空间<xref:System.Windows.Controls.Grid>而无需更改的维度<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="4cefb-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cefb-104">示例</span><span class="sxs-lookup"><span data-stu-id="4cefb-104">Example</span></span>  
 <span data-ttu-id="4cefb-105">**如何创建覆盖列边缘的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="4cefb-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="4cefb-106">若要指定<xref:System.Windows.Controls.GridSplitter>中的相邻列的大小进行调整<xref:System.Windows.Controls.Grid>，将其设置<xref:System.Windows.Controls.Grid.Column%2A>附加到一个要调整大小的列的属性。</span><span class="sxs-lookup"><span data-stu-id="4cefb-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="4cefb-107">如果你<xref:System.Windows.Controls.Grid>有多个对应的一行，设置<xref:System.Windows.Controls.Grid.RowSpan%2A>附加属性写入的行数。</span><span class="sxs-lookup"><span data-stu-id="4cefb-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="4cefb-108">然后设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性<xref:System.Windows.HorizontalAlignment.Left>或<xref:System.Windows.HorizontalAlignment.Right>（你设置的对齐方式取决于你想要调整大小的两个列）。</span><span class="sxs-lookup"><span data-stu-id="4cefb-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="4cefb-109">最后，设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性<xref:System.Windows.VerticalAlignment.Stretch>。</span><span class="sxs-lookup"><span data-stu-id="4cefb-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="4cefb-110">A<xref:System.Windows.Controls.GridSplitter>不具有其各自的列中的其他控件可能被遮盖<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="4cefb-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="4cefb-111">有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md)。</span><span class="sxs-lookup"><span data-stu-id="4cefb-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="4cefb-112">**如何创建占据一列的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="4cefb-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="4cefb-113">若要指定<xref:System.Windows.Controls.GridSplitter>占用中的列<xref:System.Windows.Controls.Grid>，将其设置<xref:System.Windows.Controls.Grid.Column%2A>附加到一个要调整大小的列的属性。</span><span class="sxs-lookup"><span data-stu-id="4cefb-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="4cefb-114">如果你网格包含多个行，请设置<xref:System.Windows.Controls.Grid.RowSpan%2A>附加属性写入的行数。</span><span class="sxs-lookup"><span data-stu-id="4cefb-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="4cefb-115">然后设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>到<xref:System.Windows.HorizontalAlignment.Center>，将其设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性<xref:System.Windows.VerticalAlignment.Stretch>，并设置<xref:System.Windows.Controls.ColumnDefinition.Width%2A>包含的列的<xref:System.Windows.Controls.GridSplitter>到<xref:System.Windows.GridLength.Auto%2A>。</span><span class="sxs-lookup"><span data-stu-id="4cefb-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="4cefb-116">下面的示例演示如何定义垂直<xref:System.Windows.Controls.GridSplitter>，中占据一列和调整它的任何一侧列的大小。</span><span class="sxs-lookup"><span data-stu-id="4cefb-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="4cefb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cefb-117">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="4cefb-118">帮助主题</span><span class="sxs-lookup"><span data-stu-id="4cefb-118">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
