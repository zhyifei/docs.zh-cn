---
title: 如何：更改 ListView 中列的水平对齐方式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458604"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="39ca6-102">如何：更改 ListView 中列的水平对齐方式</span><span class="sxs-lookup"><span data-stu-id="39ca6-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="39ca6-103">默认情况下，<xref:System.Windows.Controls.ListViewItem> 中每一列的内容都为左对齐。</span><span class="sxs-lookup"><span data-stu-id="39ca6-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="39ca6-104">您可以通过提供 <xref:System.Windows.DataTemplate> 并在 <xref:System.Windows.DataTemplate>内的元素上设置 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性，来更改每个列的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="39ca6-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="39ca6-105">本主题演示 <xref:System.Windows.Controls.ListView> 如何默认对齐其内容，以及如何更改 <xref:System.Windows.Controls.ListView>中一列的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="39ca6-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39ca6-106">示例</span><span class="sxs-lookup"><span data-stu-id="39ca6-106">Example</span></span>  
 <span data-ttu-id="39ca6-107">在下面的示例中，"`Title`" 和 "`ISBN`" 列中的数据保持左对齐。</span><span class="sxs-lookup"><span data-stu-id="39ca6-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="39ca6-108">若要更改 `ISBN` 列的对齐方式，需指定 <xref:System.Windows.Controls.ListViewItem> 每个 <xref:System.Windows.HorizontalAlignment.Stretch>的 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 属性，以便每个 <xref:System.Windows.Controls.ListViewItem> 中的元素可以跨每个列的整个宽度。</span><span class="sxs-lookup"><span data-stu-id="39ca6-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="39ca6-109">由于 <xref:System.Windows.Controls.ListView> 绑定到数据源，因此需要创建设置 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>的样式。</span><span class="sxs-lookup"><span data-stu-id="39ca6-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="39ca6-110">接下来，需要使用 <xref:System.Windows.DataTemplate> 显示内容，而不使用 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="39ca6-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="39ca6-111">若要显示每个模板的 `ISBN`，<xref:System.Windows.DataTemplate> 可以只包含其 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Right>的 <xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="39ca6-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="39ca6-112">下面的示例定义使 `ISBN` 列右对齐所需的样式和 <xref:System.Windows.DataTemplate>，并更改 <xref:System.Windows.Controls.GridViewColumn> 以引用该 <xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="39ca6-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="39ca6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="39ca6-113">See also</span></span>

- [<span data-ttu-id="39ca6-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="39ca6-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="39ca6-115">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="39ca6-115">Data Templating Overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="39ca6-116">使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="39ca6-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="39ca6-117">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="39ca6-117">ListView Overview</span></span>](listview-overview.md)
