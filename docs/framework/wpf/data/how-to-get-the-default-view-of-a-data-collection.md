---
title: 如何：获取数据集合的默认视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e8e6928391a98a132f1dbb39edfda0d73d2eebdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557168"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>如何：获取数据集合的默认视图
视图允许以不同的方式查看同一数据集合，基于排序、筛选或分组规则。 每个集合都有一个共享的默认视图中，作为（指定该集合为其绑定源的）绑定的实际绑定源。 此示例演示如何获取集合的默认视图。  
  
## <a name="example"></a>示例  
 若要创建视图，你需要一个引用了该集合的对象。 可以通过引用代码隐藏对象、获取数据上下文、获取数据源属性、获取绑定属性的方式来获得该对象。此示例演示如何获取数据对象的 <xref:System.Windows.FrameworkElement.DataContext%2A> 并使用它来直接获取该集合的默认集合视图。  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 在此示例中，根元素是 <xref:System.Windows.Controls.StackPanel>。 <xref:System.Windows.FrameworkElement.DataContext%2A> 设置为*myDataSource*，它引用了一个数据提供者（一个*Order*对象的 <xref:System.Collections.ObjectModel.ObservableCollection%601>）。  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 或者，你可以用 <xref:System.Windows.Data.CollectionViewSource> 类实例化你自己的集合视图并绑定到它。 此集合视图仅由直接绑定到它的控件共享。 有关示例，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)中的如何创建视图主题。  
  
 集合视图提供的功能的示例，请参阅[在视图中对数据进行排序](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)，[在视图中筛选数据](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)，和[在数据集合视图中的对象之间导航](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>请参阅  
 [在 XAML 中使用视图对数据进行排序和分组](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
