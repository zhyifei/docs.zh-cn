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
ms.openlocfilehash: c7de491a76ba6f8d5164c91f8c20bea4a8fa56d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688397"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>如何：在数据集合视图中的对象之间导航
视图允许相同的数据收集，以便在不同的方式，具体取决于排序、 筛选或分组中查看。 视图还提供一个当前记录指针概念，并启用移动指针。 此示例演示如何获取当前对象，以及在使用中提供的功能的数据集合的对象之间导航<xref:System.Windows.Data.CollectionView>类。  
  
## <a name="example"></a>示例  
 在此示例中，`myCollectionView`是<xref:System.Windows.Data.CollectionView>对绑定集合是一个视图的对象。  
  
 在以下示例中，`OnButton`是事件处理程序`Previous`和`Next`应用程序，这两个允许用户导航数据收集的按钮的按钮。 请注意，<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>并<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>是否当前记录指针是否到达的开头和列表的末尾分别因此的属性报告<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A>和<xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>可以相应地调用。  
  
 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>视图的属性强制转换为`Order`要在集合中返回当前的订单项。  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>请参阅
- [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [在视图中对数据进行排序](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [在视图中筛选数据](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [在 XAML 中使用视图对数据进行排序和分组](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
