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
ms.openlocfilehash: ec78b7350d23364cfb0eaa9a0611be8449073cd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556999"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>如何：在数据集合视图中的对象之间导航
可以通过视图以不同的方式查看同一数据集合，具体取决于排序、 筛选或分组。 视图还提供一个当前记录指针的概念，并且允许移动指针。 此示例演示如何获取当前对象，以及使用 <xref:System.Windows.Data.CollectionView> 类提供的功能在数据集合的对象之间导航。  
  
## <a name="example"></a>示例  
 在此示例中，`myCollectionView`（一个<xref:System.Windows.Data.CollectionView>对象） 是被绑定集合的一个视图。  
  
 在下面的示例中，`OnButton` 是应用程序中 `Previous` 按钮和 `Next` 按钮的事件处理程序，这两个按钮允许用户在数据集合中导航。 请注意，<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 和 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 属性分别报告当前记录指针是否位于列表的开头和末尾，因此可以相应地调用 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 和 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>。  
  
 视图中的 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 属性被强制转换为 `Order`，用于返回集合中当前的order对象。  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [在视图中对数据进行排序](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [在视图中筛选数据](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [在 XAML 中使用视图对数据进行排序和分组](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
