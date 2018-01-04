---
title: "如何：更改 ListView 中列的水平对齐方式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="b9993-102">如何：更改 ListView 中列的水平对齐方式</span><span class="sxs-lookup"><span data-stu-id="b9993-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="b9993-103">默认情况下，每个列中的内容<xref:System.Windows.Controls.ListViewItem>是左对齐。</span><span class="sxs-lookup"><span data-stu-id="b9993-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="b9993-104">你可以通过提供更改每个列的对齐方式<xref:System.Windows.DataTemplate>和设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>中元素的属性上<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="b9993-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="b9993-105">本主题说明如何<xref:System.Windows.Controls.ListView>对齐其内容默认情况下和如何更改中的一列的对齐方式<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="b9993-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9993-106">示例</span><span class="sxs-lookup"><span data-stu-id="b9993-106">Example</span></span>  
 <span data-ttu-id="b9993-107">在下面的示例中中的数据`Title`和`ISBN`列是左对齐。</span><span class="sxs-lookup"><span data-stu-id="b9993-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="b9993-108">若要更改的对齐方式`ISBN`列中，你需要指定<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>每个属性<xref:System.Windows.Controls.ListViewItem>是<xref:System.Windows.HorizontalAlignment.Stretch>，以便在每个元素<xref:System.Windows.Controls.ListViewItem>可以跨或沿每一列的整个宽度放置。</span><span class="sxs-lookup"><span data-stu-id="b9993-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="b9993-109">因为<xref:System.Windows.Controls.ListView>绑定到数据源，你需要创建设置样式<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>。</span><span class="sxs-lookup"><span data-stu-id="b9993-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="b9993-110">接下来，你需要使用<xref:System.Windows.DataTemplate>以显示内容而不是使用<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="b9993-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="b9993-111">若要显示`ISBN`的每个模板，<xref:System.Windows.DataTemplate>只能包含<xref:System.Windows.Controls.TextBlock>具有其<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性设置为<xref:System.Windows.HorizontalAlignment.Right>。</span><span class="sxs-lookup"><span data-stu-id="b9993-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="b9993-112">下面的示例定义的样式和<xref:System.Windows.DataTemplate>使所需`ISBN`右对齐的列和更改<xref:System.Windows.Controls.GridViewColumn>引用<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="b9993-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b9993-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9993-113">See Also</span></span>  
 [<span data-ttu-id="b9993-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="b9993-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b9993-115">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="b9993-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="b9993-116">使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="b9993-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="b9993-117">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="b9993-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
