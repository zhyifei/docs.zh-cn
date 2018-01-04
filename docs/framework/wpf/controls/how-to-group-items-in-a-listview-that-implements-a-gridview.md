---
title: "如何：对实现 GridView 的 ListView 中的项进行分组"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a97a6c85036a6daf4e8c908186953f9a75f952a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="96c4f-102">如何：对实现 GridView 的 ListView 中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="96c4f-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="96c4f-103">此示例演示如何显示组中的项数<xref:System.Windows.Controls.GridView>的查看模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="96c4f-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96c4f-104">示例</span><span class="sxs-lookup"><span data-stu-id="96c4f-104">Example</span></span>  
 <span data-ttu-id="96c4f-105">用于显示组中的项数<xref:System.Windows.Controls.ListView>，定义<xref:System.Windows.Data.CollectionViewSource>。</span><span class="sxs-lookup"><span data-stu-id="96c4f-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="96c4f-106">下面的示例演示<xref:System.Windows.Data.CollectionViewSource>数据项根据的值进行分组`Catalog`数据字段。</span><span class="sxs-lookup"><span data-stu-id="96c4f-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="96c4f-107">下面的示例设置<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>为<xref:System.Windows.Controls.ListView>到<xref:System.Windows.Data.CollectionViewSource>前面的示例定义。</span><span class="sxs-lookup"><span data-stu-id="96c4f-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="96c4f-108">该示例还定义<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>实现<xref:System.Windows.Controls.Expander>控件。</span><span class="sxs-lookup"><span data-stu-id="96c4f-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="96c4f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="96c4f-109">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="96c4f-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="96c4f-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="96c4f-111">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="96c4f-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="96c4f-112">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="96c4f-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
