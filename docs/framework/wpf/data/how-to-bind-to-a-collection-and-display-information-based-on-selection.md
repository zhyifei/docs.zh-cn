---
title: "如何：绑定到集合并基于选择显示信息"
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
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a751025470b566ef1e735e4ddd192cfd8fc354ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>如何：绑定到集合并基于选择显示信息
在简单的主 / 从方案中，具有数据绑定<xref:System.Windows.Controls.ItemsControl>如<xref:System.Windows.Controls.ListBox>。 基于用户选择，显示有关选定项的详细信息。 此示例演示如何实现这种情况。  
  
## <a name="example"></a>示例  
 在此示例中，`People`是<xref:System.Collections.ObjectModel.ObservableCollection%601>的`Person`类。 这`Person`类包含三个属性： `FirstName`， `LastName`，和`HomeTown`，所有类型`string`。  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl>使用以下<xref:System.Windows.DataTemplate>，它定义如何的信息`Person`显示：  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 以下是该示例生成的屏幕快照。 <xref:System.Windows.Controls.ContentControl>显示选择的人员的其他属性。  
  
 ![绑定到集合](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 需要注意，在此示例中，两个的事项为：  
  
1.  <xref:System.Windows.Controls.ListBox>和<xref:System.Windows.Controls.ContentControl>将绑定到相同的源。 <xref:System.Windows.Data.Binding.Path%2A>不指定这两种绑定的属性，因为这两个控件绑定到整个集合对象。  
  
2.  必须设置<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>属性`true`为使工作。 将设置此属性可确保所选的项始终设置为<xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。 或者，如果<xref:System.Windows.Controls.ListBox>获取它从数据<xref:System.Windows.Data.CollectionViewSource>，它自动同步所选内容和货币。  
  
 请注意，`Person`类重写`ToString`方法按以下方式。 默认情况下，<xref:System.Windows.Controls.ListBox>调用`ToString`并在与绑定集合中显示的字符串表示形式的每个对象。 这就是为什么每个`Person`显示中的第一个名为<xref:System.Windows.Controls.ListBox>。  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>请参阅  
 [将主-详细模式与分层数据结合使用](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [将主-详细模式与分层 XML 数据结合使用](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [数据模板化概述](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
