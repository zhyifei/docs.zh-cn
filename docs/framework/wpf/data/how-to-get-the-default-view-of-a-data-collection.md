---
title: "如何：获取数据集合的默认视图"
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
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>如何：获取数据集合的默认视图
视图允许相同的数据集合，以查看不同的方式，具体取决于排序、 筛选或分组条件。 每个集合具有一个共享的默认视图中，它作为实际绑定源用来在绑定指定为其源集合。 此示例演示如何获取集合的默认视图。  
  
## <a name="example"></a>示例  
 若要创建视图，你需要对集合的对象引用。 可以通过按获取数据上下文中，通过获取数据源的属性或获取绑定的属性引用你自己的代码隐藏对象，获取此数据对象。 此示例演示如何获取<xref:System.Windows.FrameworkElement.DataContext%2A>数据对象并使用它来直接获取默认集合查看为此集合。  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 在此示例中，根元素是<xref:System.Windows.Controls.StackPanel>。 <xref:System.Windows.FrameworkElement.DataContext%2A>设置为*myDataSource*，它是指的数据提供程序是<xref:System.Collections.ObjectModel.ObservableCollection%601>的*顺序*对象。  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 或者，你可以实例化，并将绑定到你自己的集合视图使用<xref:System.Windows.Data.CollectionViewSource>类。 此集合视图仅由控件直接绑定到它的共享。 有关示例，请参阅如何创建视图主题中[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 集合视图提供的功能的示例，请参阅[的视图中排序数据](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)，[的视图中的筛选器数据](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)，和[导航通过中的对象数据导航](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>另请参阅  
 [在 XAML 中使用视图对数据进行排序和分组](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
