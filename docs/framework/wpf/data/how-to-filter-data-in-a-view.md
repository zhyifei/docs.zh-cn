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
ms.openlocfilehash: a31c07e6be26f67cc29813a14745ecf4a83ab98a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147467"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="30bb5-102">如何：筛选视图中的数据</span><span class="sxs-lookup"><span data-stu-id="30bb5-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="30bb5-103">此示例演示如何对视图中的数据进行筛选。</span><span class="sxs-lookup"><span data-stu-id="30bb5-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30bb5-104">示例</span><span class="sxs-lookup"><span data-stu-id="30bb5-104">Example</span></span>  
 <span data-ttu-id="30bb5-105">若要创建筛选器，需要定义提供筛选逻辑的方法。</span><span class="sxs-lookup"><span data-stu-id="30bb5-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="30bb5-106">该方法用作回调，接受 `object` 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="30bb5-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="30bb5-107">以下方法将返回所有 `filled` 属性设置为"No"的 `Order` 对象，同时过滤掉其他的对象。</span><span class="sxs-lookup"><span data-stu-id="30bb5-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="30bb5-108">然后可以应用筛选器，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="30bb5-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="30bb5-109">在此示例中，`myCollectionView`是 <xref:System.Windows.Data.ListCollectionView> 对象。</span><span class="sxs-lookup"><span data-stu-id="30bb5-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="30bb5-110">若要撤销筛选，可以将 <xref:System.Windows.Data.CollectionView.Filter%2A> 属性设置为 `null`：</span><span class="sxs-lookup"><span data-stu-id="30bb5-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="30bb5-111">有关如何创建或获取视图的信息，请参阅[获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="30bb5-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="30bb5-112">有关完整示例，请参阅[对视图中的项目进行排序和筛选的示例](https://go.microsoft.com/fwlink/?LinkID=160040)。</span><span class="sxs-lookup"><span data-stu-id="30bb5-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="30bb5-113">如果视图对象是一个 <xref:System.Windows.Data.CollectionViewSource> 对象，可以通过设置 <xref:System.Windows.Data.CollectionViewSource.Filter> 事件的事件处理程序来应用筛选逻辑。</span><span class="sxs-lookup"><span data-stu-id="30bb5-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="30bb5-114">在以下示例中，`listingDataView` 是 <xref:System.Windows.Data.CollectionViewSource> 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="30bb5-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="30bb5-115">下面展示了如何实现示例筛选器 `ShowOnlyBargainsFilter` 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="30bb5-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="30bb5-116">此事件处理程序使用 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 属性来过滤掉 `CurrentPrice` 至少为 25 美元的 `AuctionItem` 对象。</span><span class="sxs-lookup"><span data-stu-id="30bb5-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="30bb5-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="30bb5-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="30bb5-118">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="30bb5-118">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="30bb5-119">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="30bb5-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="30bb5-120">帮助主题</span><span class="sxs-lookup"><span data-stu-id="30bb5-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
