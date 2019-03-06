---
title: 如何：在数据集合视图中的对象之间导航
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 9272a2f635a62abdac2746f2c8cce515812706f6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355774"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="74851-102">如何：在数据集合视图中的对象之间导航</span><span class="sxs-lookup"><span data-stu-id="74851-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="74851-103">利用视图，可以通过不同方式查看同一数据集合，具体取决于排序、筛选或分组。</span><span class="sxs-lookup"><span data-stu-id="74851-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="74851-104">视图还提供了当前记录指针的概念，并允许移动指针。</span><span class="sxs-lookup"><span data-stu-id="74851-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="74851-105">此示例演示如何获取当前对象，以及使用 <xref:System.Windows.Data.CollectionView> 类提供的功能在数据集合的对象之间导航。</span><span class="sxs-lookup"><span data-stu-id="74851-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74851-106">示例</span><span class="sxs-lookup"><span data-stu-id="74851-106">Example</span></span>  
 <span data-ttu-id="74851-107">在此示例中，`myCollectionView`（<xref:System.Windows.Data.CollectionView> 对象） 是已绑定集合的视图。</span><span class="sxs-lookup"><span data-stu-id="74851-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="74851-108">在以下示例中，`OnButton` 是应用程序中 `Previous` 按钮和 `Next` 按钮的事件处理程序，这两个按钮允许用户在数据集合中导航。</span><span class="sxs-lookup"><span data-stu-id="74851-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="74851-109">请注意，<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 和 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 属性分别报告当前记录指针是否位于列表的开头和末尾，因此可以视情况调用 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 和 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>。</span><span class="sxs-lookup"><span data-stu-id="74851-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="74851-110">视图的 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 属性会强制转换为 `Order`，用于返回集合中当前的顺序项。</span><span class="sxs-lookup"><span data-stu-id="74851-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="74851-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="74851-111">See also</span></span>
- [<span data-ttu-id="74851-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="74851-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="74851-113">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="74851-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="74851-114">在视图中筛选数据</span><span class="sxs-lookup"><span data-stu-id="74851-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="74851-115">在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="74851-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="74851-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="74851-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
