---
title: 如何：对实现 GridView 的 ListView 中的项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 1570eab70dae690f508975162b7553de92be6f12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664351"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="70b37-102">如何：对实现 GridView 的 ListView 中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="70b37-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="70b37-103">此示例演示如何显示组中的项数<xref:System.Windows.Controls.GridView>视图模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="70b37-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70b37-104">示例</span><span class="sxs-lookup"><span data-stu-id="70b37-104">Example</span></span>  
 <span data-ttu-id="70b37-105">若要显示组中的项数<xref:System.Windows.Controls.ListView>，定义<xref:System.Windows.Data.CollectionViewSource>。</span><span class="sxs-lookup"><span data-stu-id="70b37-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="70b37-106">下面的示例演示<xref:System.Windows.Data.CollectionViewSource>分组数据项的值根据`Catalog`数据字段。</span><span class="sxs-lookup"><span data-stu-id="70b37-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="70b37-107">下面的示例设置<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>有关<xref:System.Windows.Controls.ListView>到<xref:System.Windows.Data.CollectionViewSource>前面的示例定义。</span><span class="sxs-lookup"><span data-stu-id="70b37-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="70b37-108">该示例还定义了<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>实现<xref:System.Windows.Controls.Expander>控件。</span><span class="sxs-lookup"><span data-stu-id="70b37-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="70b37-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="70b37-109">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="70b37-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="70b37-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [<span data-ttu-id="70b37-111">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="70b37-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
- [<span data-ttu-id="70b37-112">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="70b37-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
