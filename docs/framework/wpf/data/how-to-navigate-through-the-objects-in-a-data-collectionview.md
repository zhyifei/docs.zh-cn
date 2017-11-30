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
ms.openlocfilehash: f20881ed452f1ec78381d17a32b4cc2c77305e0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>如何：在数据集合视图中的对象之间导航
视图允许相同的数据集合，以查看不同的方式，具体取决于排序、 筛选或分组。 视图还提供一个当前记录指针概念，以及启用移动指针。 此示例演示如何获取当前对象，以及在使用中提供的功能数据集合中的对象中导航<xref:System.Windows.Data.CollectionView>类。  
  
## <a name="example"></a>示例  
 在此示例中，`myCollectionView`是<xref:System.Windows.Data.CollectionView>通过绑定的集合是一个视图的对象。  
  
 在下面的示例中，`OnButton`是事件处理程序`Previous`和`Next`应用程序，这两个允许用户导航数据收集的按钮的按钮。 请注意，<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>和<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>属性报告是否当前记录指针是否到达的开头和列表的末尾分别因此，<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A>和<xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>可以相应地调用。  
  
 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>在视图的属性被强制转换为`Order`集合中返回当前的顺序项。  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>另请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [在视图中对数据进行排序](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [在视图中筛选数据](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [在 XAML 中使用视图对数据进行排序和分组](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
