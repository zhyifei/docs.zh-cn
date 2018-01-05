---
title: "如何：在数据集合视图中的对象之间导航"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215e3583d50567a2bfec8226e006bc7398628299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="70839-102">如何：在数据集合视图中的对象之间导航</span><span class="sxs-lookup"><span data-stu-id="70839-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="70839-103">视图允许相同的数据集合，以查看不同的方式，具体取决于排序、 筛选或分组。</span><span class="sxs-lookup"><span data-stu-id="70839-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="70839-104">视图还提供一个当前记录指针概念，以及启用移动指针。</span><span class="sxs-lookup"><span data-stu-id="70839-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="70839-105">此示例演示如何获取当前对象，以及在使用中提供的功能数据集合中的对象中导航<xref:System.Windows.Data.CollectionView>类。</span><span class="sxs-lookup"><span data-stu-id="70839-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70839-106">示例</span><span class="sxs-lookup"><span data-stu-id="70839-106">Example</span></span>  
 <span data-ttu-id="70839-107">在此示例中，`myCollectionView`是<xref:System.Windows.Data.CollectionView>通过绑定的集合是一个视图的对象。</span><span class="sxs-lookup"><span data-stu-id="70839-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="70839-108">在下面的示例中，`OnButton`是事件处理程序`Previous`和`Next`应用程序，这两个允许用户导航数据收集的按钮的按钮。</span><span class="sxs-lookup"><span data-stu-id="70839-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="70839-109">请注意，<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>和<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>属性报告是否当前记录指针是否到达的开头和列表的末尾分别因此，<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A>和<xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>可以相应地调用。</span><span class="sxs-lookup"><span data-stu-id="70839-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="70839-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A>在视图的属性被强制转换为`Order`集合中返回当前的顺序项。</span><span class="sxs-lookup"><span data-stu-id="70839-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="70839-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="70839-111">See Also</span></span>  
 [<span data-ttu-id="70839-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="70839-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="70839-113">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="70839-113">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="70839-114">在视图中筛选数据</span><span class="sxs-lookup"><span data-stu-id="70839-114">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="70839-115">在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="70839-115">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="70839-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="70839-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
