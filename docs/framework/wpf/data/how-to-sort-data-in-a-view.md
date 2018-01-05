---
title: "如何：在视图中对数据进行排序"
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
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7467913f867ea0990ae85b0ad933c11f2fd271b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-data-in-a-view"></a>如何：在视图中对数据进行排序
本示例介绍了如何在视图中的数据进行排序。  
  
## <a name="example"></a>示例  
 下面的示例创建一个简单<xref:System.Windows.Controls.ListBox>和<xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>按钮事件处理程序包含中的项进行排序的逻辑<xref:System.Windows.Controls.ListBox>按降序排序。 你可以这样做是因为将项添加到<xref:System.Windows.Controls.ListBox>这种方式将它们添加到<xref:System.Windows.Controls.ItemCollection>的<xref:System.Windows.Controls.ListBox>，和<xref:System.Windows.Controls.ItemCollection>派生自<xref:System.Windows.Data.CollectionView>类。 如果你正在绑定你<xref:System.Windows.Controls.ListBox>集合使用<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性，您可以使用相同的技术进行排序。  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 只要你有对视图对象的引用，可以使用相同的技术的其他集合视图的内容进行排序。 有关如何获取视图的示例，请参阅[获取数据收集的默认视图](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)。 另一个示例，请参阅[排序 GridView 时单击标题对列](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)。 有关视图的详细信息，请参阅到集合中的绑定[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 有关如何应用中的排序逻辑的示例[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，请参阅[排序和组数据使用 XAML 中的一个视图](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [在标题获得单击时对 GridView 列进行排序](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [在视图中筛选数据](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
