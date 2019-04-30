---
title: 如何：在视图中对数据进行排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 32f73d3c3ba213778654f0d1ee7bbae16b9d845b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020720"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="b311f-102">如何：在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="b311f-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="b311f-103">本示例介绍如何在视图中对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="b311f-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b311f-104">示例</span><span class="sxs-lookup"><span data-stu-id="b311f-104">Example</span></span>  
 <span data-ttu-id="b311f-105">下面的示例创建了一个简单的 <xref:System.Windows.Controls.ListBox> 和一个 <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="b311f-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="b311f-106">按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序包含对 <xref:System.Windows.Controls.ListBox> 中的项进行降序排序的逻辑。</span><span class="sxs-lookup"><span data-stu-id="b311f-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="b311f-107">之所以可以这样做是因为以这种方式将对象添加到 <xref:System.Windows.Controls.ListBox> 实际是将它们添加到了 <xref:System.Windows.Controls.ListBox> 的 <xref:System.Windows.Controls.ItemCollection>，而 <xref:System.Windows.Controls.ItemCollection> 派生自 <xref:System.Windows.Data.CollectionView> 类。</span><span class="sxs-lookup"><span data-stu-id="b311f-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="b311f-108">如果用 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性将<xref:System.Windows.Controls.ListBox> 绑定到一个集合，也可以使用相同的技术进行排序。</span><span class="sxs-lookup"><span data-stu-id="b311f-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="b311f-109">只要有视图对象的引用，就可以使用相同的技术对其他集合视图的内容进行排序。</span><span class="sxs-lookup"><span data-stu-id="b311f-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="b311f-110">有关如何获取视图的示例，请参阅[获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="b311f-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="b311f-111">另一个示例请参阅[在单击标题时对 GridView 列进行排序](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)。</span><span class="sxs-lookup"><span data-stu-id="b311f-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="b311f-112">有关视图的详细信息，请参阅 [数据绑定概述](data-binding-overview.md)中的“绑定到集合”。</span><span class="sxs-lookup"><span data-stu-id="b311f-112">For more information about views, see Binding to Collections in [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="b311f-113">有关如何在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中应用排序逻辑的示例，请参阅[在 XAML 中使用视图对数据进行排序和分组](how-to-sort-and-group-data-using-a-view-in-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="b311f-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b311f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b311f-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="b311f-115">在单击标题时对 GridView 列进行排序</span><span class="sxs-lookup"><span data-stu-id="b311f-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="b311f-116">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="b311f-116">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="b311f-117">在视图中筛选数据</span><span class="sxs-lookup"><span data-stu-id="b311f-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="b311f-118">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b311f-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
