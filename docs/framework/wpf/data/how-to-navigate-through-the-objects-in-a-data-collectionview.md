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
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459706"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>如何：在数据集合视图中的对象之间导航
视图允许以不同的方式查看相同的数据集合，具体取决于排序、筛选或分组。 视图还提供当前记录指针概念并启用移动指针。 此示例演示如何获取当前对象，以及如何使用 <xref:System.Windows.Data.CollectionView> 类中提供的功能在数据集合中浏览对象。  
  
## <a name="example"></a>示例  
 在此示例中，`myCollectionView` 是一个 <xref:System.Windows.Data.CollectionView> 对象，该对象是绑定集合上的一个视图。  
  
 在下面的示例中，`OnButton` 是应用程序中 "`Previous`" 和 "`Next`" 按钮的事件处理程序，这是允许用户导航数据集合的按钮。 请注意，"<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>" 和 "<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>" 属性报告当前记录指针是否分别到达列表的开头和末尾，以便可以适当地调用 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 和 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>。  
  
 视图的 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 属性将转换为 `Order` 以返回集合中的当前订单项。  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [在视图中对数据进行排序](how-to-sort-data-in-a-view.md)
- [在视图中筛选数据](how-to-filter-data-in-a-view.md)
- [在 XAML 中使用视图对数据进行排序和分组](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [帮助主题](data-binding-how-to-topics.md)
