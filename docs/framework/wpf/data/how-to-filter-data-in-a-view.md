---
title: 如何：筛选视图中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: 33af517c086f8f89cc06a1de7a2979c5b1624109
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689307"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="cb281-102">如何：筛选视图中的数据</span><span class="sxs-lookup"><span data-stu-id="cb281-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="cb281-103">此示例演示如何在视图中的数据进行筛选。</span><span class="sxs-lookup"><span data-stu-id="cb281-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb281-104">示例</span><span class="sxs-lookup"><span data-stu-id="cb281-104">Example</span></span>  
 <span data-ttu-id="cb281-105">若要创建筛选器，定义的方法，提供筛选逻辑。</span><span class="sxs-lookup"><span data-stu-id="cb281-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="cb281-106">该方法用作回调并接受类型参数的`object`。</span><span class="sxs-lookup"><span data-stu-id="cb281-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="cb281-107">以下方法将返回所有`Order`对象与`filled`属性设置为"否"，筛选出的对象的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cb281-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="cb281-108">然后可以应用筛选器，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cb281-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="cb281-109">在此示例中，`myCollectionView`是<xref:System.Windows.Data.ListCollectionView>对象。</span><span class="sxs-lookup"><span data-stu-id="cb281-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="cb281-110">若要撤销筛选，可以设置<xref:System.Windows.Data.CollectionView.Filter%2A>属性设置为`null`:</span><span class="sxs-lookup"><span data-stu-id="cb281-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="cb281-111">有关如何创建或获取视图的信息，请参阅[获取数据集合的默认视图](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="cb281-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="cb281-112">有关完整示例，请参阅[进行排序和筛选视图示例中的项目](https://go.microsoft.com/fwlink/?LinkID=160040)。</span><span class="sxs-lookup"><span data-stu-id="cb281-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="cb281-113">如果您的视图对象来自<xref:System.Windows.Data.CollectionViewSource>对象，你的设置的事件处理程序来应用筛选逻辑<xref:System.Windows.Data.CollectionViewSource.Filter>事件。</span><span class="sxs-lookup"><span data-stu-id="cb281-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="cb281-114">在以下示例中，`listingDataView`的一个实例<xref:System.Windows.Data.CollectionViewSource>。</span><span class="sxs-lookup"><span data-stu-id="cb281-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="cb281-115">下面显示了示例的实现`ShowOnlyBargainsFilter`筛选器事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cb281-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="cb281-116">此事件处理程序使用<xref:System.Windows.Data.FilterEventArgs.Accepted%2A>属性来筛选出`AuctionItem`具有对象`CurrentPrice`25 美元或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cb281-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="cb281-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb281-117">See also</span></span>
- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="cb281-118">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="cb281-118">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cb281-119">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="cb281-119">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="cb281-120">帮助主题</span><span class="sxs-lookup"><span data-stu-id="cb281-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
